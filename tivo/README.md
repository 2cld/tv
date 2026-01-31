# Tivo network bridge

ME: I am a network engineer working with zerotier and would like to join my 2 remote work-sites site1 and site2 with a LAN.  Some devices like a printer, I can set the IP and subnet, but they cannot run zerotier.  What do I need to do to let a workstation from site1 print to the printer on site2?

---

To bridge your two sites so that non-ZeroTier devices (like your printer) can communicate across the network, you need to set up **Site-to-Site Routing**. This essentially makes one ZeroTier-enabled device at each site act as a **gateway** for the rest of the local hardware.

Here is the high-level workflow to get that printer online for site1:

### 1. Designate a Gateway at Each Site

You need one device at **Site1** and one at **Site2** that is always on and runs ZeroTier (typically a Linux box, Raspberry Pi, or a compatible router like Teltonika or Mikrotik).

### 2. Enable IP Forwarding

On both gateway devices, you must allow them to pass traffic between the ZeroTier interface and the physical LAN interface. On a Linux gateway, you would typically run:
`sudo sysctl -w net.ipv4.ip_forward=1`

### 3. Configure Managed Routes in ZeroTier Central

You must tell the ZeroTier controller how to find the physical subnets at each site. Log into your [ZeroTier Central](https://my.zerotier.com/) dashboard and add **Managed Routes**:

| Target (LAN Subnet) | Via (Gateway's ZeroTier IP) |
| --- | --- |
| **Site1 LAN** (e.g., `192.168.1.0/24`) | ZeroTier IP of Site1 Gateway |
| **Site2 LAN** (e.g., `192.168.2.0/24`) | ZeroTier IP of Site2 Gateway |

### 4. Set Up Static Routes on Your Local Routers

This is the step most people miss. Since the printer doesn't know what "ZeroTier" is, when it receives a print job from Site1, it will try to send the reply to its **Default Gateway** (your local office router).

You have two choices to fix this:

* **The Pro Way:** Add a **Static Route** on your physical office routers. Tell the Site2 router: *"To reach the Site1 subnet (192.168.1.0/24), send traffic to the local IP of the Site2 Gateway."*
* **The "Easy" Way (MASQUERADE):** Configure `iptables` NAT (masquerading) on the Site2 Gateway. This makes the print job look like it's coming from the Gateway itself, so the printer knows exactly where to send the reply without needing a static route.

---

### Which approach would you prefer?

* **Would you like the specific iptables commands** to set up the NAT/Masquerade on a Linux gateway?
* **Would you like help calculating the Managed Routes** if you provide your specific IP ranges?

ME: In the masquerade way, does the workstation look like it's on the printer network (I assume yes for the session?)
---

Actually, no—it’s the other way around!

In the **Masquerade (NAT)** scenario, the printer won't think the workstation is on its local network. Instead, the **printer thinks the Site2 Gateway is the one doing the printing.**

Here is how the "identity" shifts during that session:

### The Packet's Journey

1. **Workstation (Site1):** Sends a print job to the Printer's IP (e.g., `192.168.2.50`).
2. **Site2 Gateway:** Receives this packet via the ZeroTier tunnel. Before handing it to the printer, it performs **Source NAT (SNAT)**.
3. **The Swap:** The gateway replaces the Workstation's IP address with its own **Local LAN IP** (e.g., `192.168.2.10`).
4. **The Printer:** Sees a print request coming from `192.168.2.10` (the gateway). Since that IP is on its own local subnet, the printer says, "I know how to talk back to that guy!" and sends the response directly to the gateway.
5. **The Hand-off:** The gateway receives the response, remembers it was actually for the workstation, and passes it back through the ZeroTier tunnel.

### Why this matters

* **The Benefit:** You don't have to touch the printer's gateway settings or add static routes to your main router. It "just works" because the printer thinks it's talking to a local neighbor.
* **The Catch:** On the printer's internal logs or web interface, **every single print job** will appear to come from the Site2 Gateway's IP address. You lose the ability to see which specific workstation sent which job based on the IP.

### The `iptables` Rule

If your Site2 Gateway is Linux, the command to make this happen looks like this (assuming `eth0` is your LAN interface):

`sudo iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE`

> [!TIP]
> **Printer Discovery:** Even with this set up, "Auto-Discovery" (AirPrint/Bonjour) usually won't work across the sites because those protocols rely on broadcasts that don't cross subnets. You'll likely need to add the printer on the workstation manually using its **fixed IP address**.

---
---

**Would you like me to help you write a persistence script so these rules stay active if your gateway reboots?**

---

ME: Yes, help me write a persistance script please!

---

To make your masquerade rules and IP forwarding persist through reboots on a Linux gateway, the most robust method is to use a combination of `sysctl.conf` and a dedicated `iptables` service.

Here is how to set it up:

### 1. Make IP Forwarding Permanent

Edit the system configuration file to ensure the kernel always allows packet forwarding.

* Open the file: `sudo nano /etc/sysctl.conf`
* Find the line `#net.ipv4.ip_forward=1` and **remove the `#**` (or add the line if it doesn't exist).
* Save and exit, then apply it immediately:
`sudo sysctl -p`

---

### 2. Create the Persistence Script

Since standard `iptables` commands clear out on reboot, we will create a simple script that triggers whenever the network interface comes up.

**Create the script file:**
`sudo nano /usr/local/bin/zt-nat-setup.sh`

**Paste the following content:** (Replace `eth0` with your gateway's actual physical LAN interface name, e.g., `enp1s0`)

```bash
#!/bin/bash
# Enable NAT Masquerade for ZeroTier traffic
# Replace eth0 with your physical LAN interface
ETH_IFACE="eth0"

# Flush existing rules to avoid duplicates
iptables -t nat -F

# Apply the Masquerade rule
iptables -t nat -A POSTROUTING -o $ETH_IFACE -j MASQUERADE

# Ensure forwarding is active
echo 1 > /proc/sys/net/ipv4/ip_forward

```

**Give it execution permissions:**
`sudo chmod +x /usr/local/bin/zt-nat-setup.sh`

---

### 3. Automate with a Systemd Service

This ensures the script runs automatically every time the machine boots up.

**Create the service unit:**
`sudo nano /etc/systemd/system/zt-nat.service`

**Paste this configuration:**

```ini
[Unit]
Description=ZeroTier Site-to-Site NAT Setup
After=network.target

[Service]
Type=oneshot
ExecStart=/usr/local/bin/zt-nat-setup.sh
RemainAfterExit=yes

[Install]
WantedBy=multi-user.target

```

**Enable and start the service:**
`sudo systemctl enable zt-nat.service`
`sudo systemctl start zt-nat.service`

---

### Verification

You can verify that the masquerade rule is active at any time by running:
`sudo iptables -t nat -L -v -n`

You should see a `MASQUERADE` entry under the `POSTROUTING` chain targeting your physical interface.

---
---

**Would you like me to show you how to test the connectivity from a Site1 workstation using `ping` or `traceroute` to confirm the path is working?**

---

ME: Yes, show me how to test connectivity!

---

To test your site-to-site connectivity and verify the Masquerade setup is working correctly, you will want to run tests from a **Workstation at Site1** targeting the **Printer at Site2**.

### 1. Basic Ping Test

From a command prompt or terminal at **Site1**, try to ping the printer's local Site2 IP address.

```bash
ping 192.168.2.50

```

* **Success:** If you get a reply, the routing and NAT are working! The printer thinks it's talking to your Gateway, and your Gateway is successfully handing the reply back to you.
* **Failure:** If it times out, the issue is likely the Gateway's firewall or the IP forwarding setting.

### 2. Trace the Path

Use `traceroute` (Linux/Mac) or `tracert` (Windows) to see exactly where the connection is going.

```bash
# Windows
tracert 192.168.2.50

# Linux/Mac
traceroute 192.168.2.50

```

**What to look for:**

1. **Hop 1:** Should be your local Site1 Gateway's ZeroTier IP.
2. **Hop 2:** Should be the Site2 Gateway's ZeroTier IP.
3. **Hop 3:** Should be the Printer's local IP (`192.168.2.50`).

If the trace stops at Hop 2, the Site2 Gateway is receiving the packet but isn't successfully pushing it out to the physical LAN or the printer isn't responding to that Gateway.

---

### 3. Verify the "Masquerade" on the Gateway

If the ping fails, log back into your **Site2 Gateway** and check the hit-count on your iptables rule. This will tell you if the traffic from Site1 is actually hitting the NAT rule.

Run this command:
`sudo iptables -t nat -L POSTROUTING -v -n`

Look for the `MASQUERADE` line you created. If the **"pkts" (packets)** count is increasing when you try to ping from Site1, then the Gateway **is** doing its job. If the count stays at `0`, the traffic from Site1 isn't reaching the Site2 Gateway's internal routing engine yet.

### 4. Port Test (The "Real World" Test)

Since some devices ignore pings (ICMP), try to see if you can "see" the printer's web interface or printing port (usually 9100).

* **Browser:** Open `http://192.168.2.50` in your browser at Site1.
* **Telnet/NC:** Run `nc -zv 192.168.2.50 9100`.

---
---

**Would you like me to help you troubleshoot a specific hop if the traceroute shows a break in the chain?**

---

ME: Yes, show me how to troubleshoot a break.

---

To troubleshoot a break in your Site-to-Site connection, we need to isolate whether the issue is **routing** (the packet doesn't know where to go), **firewalling** (the packet is being blocked), or **NAT** (the return trip is failing).

Based on the `traceroute` or `tracert` results from your previous step, here is how to fix the break at each specific hop:

### Case 1: The trace dies at Hop 1 (Your Site1 Gateway)

If you can't even get past the first gateway, the workstation doesn't know that the Site2 subnet should go through ZeroTier.

* **The Fix:** Check the **Managed Routes** in your ZeroTier Central dashboard.
* **Verification:** On the Site1 Workstation, run `route print` (Windows) or `netstat -rn` (Linux/Mac). You should see an entry for the Site2 subnet (e.g., `192.168.2.0/24`) pointing to the ZeroTier interface.

---

### Case 2: The trace dies at Hop 2 (Site2 Gateway)

This is the most common failure point. It means the packet reached the remote site, but the Site2 Gateway dropped it or didn't know what to do with it.

* **Check IP Forwarding:** Ensure forwarding is actually active on the Site2 Gateway:
`cat /proc/sys/net/ipv4/ip_forward` (Should return `1`).
* **Check IPTables Filter:** Even if NAT is set up, the `FORWARD` chain might be blocking the traffic. Try temporarily allowing all forwarded traffic to test:
`sudo iptables -P FORWARD ACCEPT`
* **ZeroTier Interface Settings:** Ensure "Allow Managed IPs" is checked for that member in the ZeroTier Central console.

---

### Case 3: The trace reaches the Printer, but Ping fails

If the traceroute finishes but you can't get a standard "Reply," the packet reached the printer, but the printer's response got lost.

* **Check the Masquerade Rule:** If you aren't using the NAT/Masquerade rule we wrote, the printer is likely trying to send the response to its own local default gateway (your ISP router) instead of back to the ZeroTier Gateway.
* **Run a Packet Sniff:** On the Site2 Gateway, see if the traffic is actually leaving the physical interface:
`sudo tcpdump -i eth0 host 192.168.2.50`
*If you see the "Request" going out but no "Reply" coming back, the printer is ignoring the packet or sending the reply to the wrong place.*

---

### Summary Checklist for Site2 Gateway

If you are stuck, run these three commands on the **Site2 Gateway** and check the output:

1. **Is Forwarding on?** `sysctl net.ipv4.ip_forward`
2. **Is NAT active?** `sudo iptables -t nat -L -n -v` (Look for hits on the MASQUERADE rule).
3. **Is the Firewall open?** `sudo iptables -L FORWARD -n -v` (Look for "REJECT" or "DROP" rules).

---
---

**Would you like me to provide a `tcpdump` command you can run to watch the handshake happen in real-time?**

---

ME: Yes, show me the tcpdump command!

---

To see exactly what's happening at the packet level on your **Site2 Gateway**, you can use `tcpdump`. This will show you if the "print" packets are arriving from Site1, if they are being correctly translated (NAT), and if the printer is actually responding.

Run this command on the **Site2 Gateway** (Linux):

```bash
sudo tcpdump -i any -n host 192.168.2.50

```

### What to Look For (The "Healthy" Handshake)

When you try to print or ping from **Site1**, you should see a sequence of packets like this:

1. **Inbound from Site1:** A packet arriving on your `zt...` interface from the Workstation IP (or your Site1 Gateway IP) addressed to `192.168.2.50`.
2. **Outbound to Printer:** A packet leaving your physical interface (`eth0`) addressed to `192.168.2.50`, but the **Source IP** should now be the **Gateway's own local IP** (because of your Masquerade rule).
3. **Inbound from Printer:** A packet coming back from `192.168.2.50` addressed to your Gateway's local IP.
4. **Outbound to Site1:** The Gateway translating that response back and sending it back into the ZeroTier tunnel.

---

### Red Flags in the Dump

* **Seeing "ARP Request" but no "Reply":** The gateway is asking "Who has 192.168.2.50?", but the printer isn't answering. Check if the printer is actually on and at that exact IP.
* **Seeing "Request" but no "Reply" (and IP is correct):** The printer is receiving the packet but is ignoring it. This often happens if the Masquerade failed and the printer sees a "foreign" IP (Site1) and doesn't know how to route the response.
* **Total Silence:** If you run the command and see nothing while trying to print, the traffic isn't reaching the Site2 Gateway at all. You need to look back at the Site1 routing table or ZeroTier Central Managed Routes.

### Pro-Tip: Filter by Port

If there is too much noise, you can filter specifically for the printing protocol (JetDirect/AppSocket):
`sudo tcpdump -i any -n host 192.168.2.50 and port 9100`

**Would you like me to help you interpret a specific snippet of the tcpdump output if you paste it here?**
