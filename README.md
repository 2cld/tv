[edit](https://github.com/2cld/tv/edit/main/README.md)

# test
- [Floppy - Batman](https://sg.klopfenstein.org/?launchApp=SYNO.SDS.VideoPlayer2.Application&SynoToken=aImk6sSY9J75Y&launchParam=ieMode%3D9%26is_drive%3Dfalse%26path%3D%252Fdocker%252FcatMetube%252FThe%2520Floppy%2520Show%252FThe%2520Floppy%2520Show%2520with%2520guest%2520Adam%2520West%2520as%2520Batman%2520-%2520November%25205%25201977.webm%26file_id%3D%252Fdocker%252FcatMetube%252FThe%2520Floppy%2520Show%252FThe%2520Floppy%2520Show%2520with%2520guest%2520Adam%2520West%2520as%2520Batman%2520-%2520November%25205%25201977.webm&ieMode=9)
- Kiss [End of the Road](https://www.youtube.com/watch?v=w-WCGUunR94)
- tbd

# Plex fix wip
- sl [https://sl.2cld.net/](https://sl.2cld.net/)
- Verify Plex storage locations below
- HDHomeRun test (sl)
  - 8	HDHR-10802956	00-18-DD-08-02-95	[192.168.0.13](http://192.168.0.13)	Permanent
  - Test HDHomeRun app slwin11ops
  - Test HDHomeRun app gusHP
  - Test HDHomeRun app gusGram (probably will not work unless we enable old wifi)
  - Test HDHomeRun app iPhone (probably will not work unless we enable old wifi)
  - Test HDHomeRun app RoKu (wired)
- Plex Test (sl)
  - 9	slwin11ops	B0-83-FE-65-80-80	192.168.0.143	01:22:13
  - plex on port 32400	[192.168.0.143:32400](http://192.168.0.143:32400)	
  - Test Plex app slwin11ops
  - Test Plex app gusHP
  - Test Plex app gusGram 
  - Test Plex app iPhone 
  - Test Plex app RoKu (wired and wifi)
- Plex Test (wf)	
  - Test Plex app catsurface 
  - Test Plex app iPhone 
  - Test Plex app RoKu (wifi)
    - Channel 2.1 CBS (HD) "Playback Error" Live TV playback coud not be started
    - Channel 7.2 H&I works and records
  - tbd
- tbd


## tv.2cld Plex 
172.17.0.3 : 32400  Public 192.111.21.62 : 0 

| [plex.tv](https://app.plex.tv/desktop/#!/) service | plex-owner | purpose | status | route |
|---|---|---|---|--|
| [sl-0-9-slDVR](http://192.168.0.9:32400/) | christrees | [docs](https://netstack.org/docs/portals/plex) for [slDVR on slwin11 local](https://192.168.6.67:32400) win11 Dell 1U | live in sl | sl->24.216.218.112:32500->0.9 |
|---|---|---|---|--|
| [cf-6-30-cfTV](http://192.168.6.30:32400/) | christrees | [docs](https://netstack.org/docs/portals/plex) for [cfDVR on CyberTruck local](https://192.168.6.67:32400) win10 i7 CyberTruck | live in cf | cf->32500->6.30 |
| [cf-9-33-cfPlex](http://192.168.9.33:32400/) | christrees | [docs](https://netstack.org/docs/portals/plex) for [cfPlex local on cfPlex](https://192.168.9.33:32400) win11 i5 proxmox drive passthroug | live in cf | cf->cf2->32400->9.33 |
| [cf-6-67-cfDVR](http://192.168.6.67:32400/) | christrees| [docs](https://netstack.org/docs/portals/plex) for [cfDVR on cfDVR local](https://192.168.6.67:32400) Synology ds-411 | live in cf | cf->32500->6.6 |
|-old-|---|---|---|--|
| ~~[cf-6-67-cfDVR](http://192.168.6.67:32400/)~~ | tri484| [docs](https://netstack.org/docs/portals/plex) for [cfDVR on cfDVR local](https://192.168.6.67:32400) Synology ds-411 | live in cf | cf->32500->6.6 |
| ~~[cf-6-67-cfDVR](http://192.168.6.67:32400/)~~ | christrees| [docs](https://netstack.org/docs/portals/plex) for [cfDVR on cfDVR local](https://192.168.6.67:32400) Synology ds-411 | live in cf | cf->32500->6.6 |
| ~~[slPlex remote](http://24.216.208.251:32400/)~~ not stable | christrees | [docs](https://netstack.org/docs/portals/plex) for [slPlex on slsg2 local](http://192.168.0.6:32400/) qnap TS-431 | live in sl | sl->32400->0.6 |
| ~~[slDVR remote](http://24.216.208.251:32500/)~~ | christrees | [docs](https://netstack.org/docs/portals/plex) for [slDVR on slwin11 local](http://192.168.0.9:32400/) 1u Dell | live in sl | sl->32500->0.9 |
|---|---|---|---|--|
| ~~[test 2020](http://test.christrees.com:2020/)~~ | christrees | cf old tnas ssh | old in cf | cf->2020->6.2:21 |
| ~~[test 2021](http://test.christrees.com:2021/)~~ | christrees | cfDVR  ssh | live in cf | cf->2020->6.6:2020 |

## tv.2cld Media Guides

| Media Guide | Location | Type |
|---|---|---|
| [Gus media guide](../media/gus) | Movies, TV Shows, Music | web |
| [CAT media guide](../media/cat) | Movies, TV Shows, Music | web |
| [Media Inventory - google ss](https://docs.google.com/spreadsheets/d/1QtCblfwwH6PWYOKnIw2m4DKLni8KrVynXM6Xslb7mGg/edit#gid=0) | SJ,SE,CT Inventory | christrees |
| [cfPlex Live TV channel map - google ss](https://docs.google.com/spreadsheets/d/1wjN1_N5Vjji6NQgE3DXi4D-S76sAHppQrdXsqh5qX2E/edit#gid=0) | Live TV | [tbd cfPlex - LiveTV]() | 
| [moviesanywhere my movies](https://moviesanywhere.com/login) | cloud movies | christrees |
| [youtube my movies](https://www.youtube.com/feed/storefront?bp=EgCSAQMIyQSiBQIoBA%3D%3D)  | cloud movies | christrees |
| [Cedar Falls Library Login](https://wcfpl.ent.sirsi.net/client/en_US/cfpl/?) | public Library | christrees |
| [Cedar Falls Library Login](https://cedarfalls.aspendiscovery.org/MyAccount/Home) | public Lib login 2 | |
| [Libby Library Login](https://libbyapp.com/library/cfwpl) | public Lib Libby | |
| [Hoopla Library Login](https://www.hoopladigital.com/my/hoopla) | public Lib Hoopla | |
| [gutenberg.org](https://www.gutenberg.org/) | open Lib | |
| [openlibrary.org](https://openlibrary.org/) | open Lib | |

---

### tv services notes
- [naming-and-organizing-your-plextv-show-files](https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/)
- [tv.2cld.net](https://tv.2cld.net/)
- [cf.2cld.net/docs](https://cf.2cld.net/docs)
- [sl.2cld.net/docs](https://sl.2cld.net/docs)
- [netstack.org/docs](https://netstack.org/docs/)

#### VHS Archive projects
- [VHS Inventory Pictures](https://photos.app.goo.gl/a2mj4dqQTxGuZgBZ6)
- [VHS Inventory Google Sheet - Shared Google Sheet - Media Inventory](https://docs.google.com/spreadsheets/d/1QtCblfwwH6PWYOKnIw2m4DKLni8KrVynXM6Xslb7mGg/edit#gid=0)


---
# [cfTV](http://test.christrees.com:32600/) testing plex server
- [cfTV plex on CyberTruck local https://192.168.6.30:32600/](https://192.168.6.30:32600/) win11 i7-3820 16GB ghadmin CyberTruck-cf630 CyberTruck-zt198

| [cfTV](http://test.christrees.com:32600/) Plex lib | local mnt | netpath |
|-------------|------------------|---|
| cfTV-DVR | CyberTruck C:\cfTV-DVR |  none |
| cfTV-Test | pshare P:\cfTV-Test |  buadmin \\192.168.6.6\cfTV-Test |

| [cfTV](http://test.christrees.com:32600/) local | local mnt | netpath |
|-------------|------------------|---|
| CyberTruck | CyberTruck C: | local |
| pshare | pshare P:\cfTV-Test |  ghadmin \\192.168.6.6\cfTV-Test |

# [cfPlex](http://test.christrees.com:32400/)
- [cfPlex plex on cfPlex local https://192.168.6.3:32400/](https://192.168.6.3:32400/) win11 i7-3820 16GB ghadmin cfPlex-cf603 cfPlex-zt228

| [cfPlex](http://test.christrees.com:32400/) Plex lib | local mnt | netpath |
|-------------|------------------|---|
| catMovies | pshare P:\catMovies |  ghadmin \\192.168.6.6\catMovies |
| catDVR | cfPlex C:\catDVR |  local |
| catShows | pshare P:\catShows |  ghadmin \\192.168.6.6\catShows |
| StarTrek | plexnsds O:\plexdvr\startrekDVR |  ghadmin \\192.168.6.10\plexdvr\startrekDVR |

| [cfPlex](http://test.christrees.com:32400/) local | local mnt | netpath |
|-------------|------------------|---|
| cfplex | cfPlex C: | local |
| slwin11 | slShareD 10.147.19.198 D: | ghadmin \\10.147.19.198\slShareD |
| slwin11 | slShareE 10.147.19.198 E: | ghadmin \\10.147.19.198\slShareE |
| plexnsds | plexnsds 192.168.6.10 O: |  ghadmin \\192.168.6.10\ |
| pshare | pshare 192.168.6.6 P: |  ghadmin \\192.168.6.6\ |


# [cfDVR](http://test.christrees.com:32500/)
- maily for trink and older stuff
- [cfDVR plex on sg local](https://cf.2cld.net/docs) Synology ds411 
  
| [cfDVR](http://test.christrees.com:32500/) Lib |  local mnt | netpath |
|-------------|------------------|---|
| pshareMovies | /volume1/pshare/bs01Movie | ghadmin \\192.168.6\bs01Movie |
| pshareDVR | /volume1/pshare/bs01DVR | ghadmin \\192.168.6\bs01DVR |
| trinkDVR | /volume1/pshare/trinkDVR | ghadmin \\192.168.6\trinkDVR |


# [slDVR](http://24.216.208.251:32500/)
- [slDRV Plex backup server on slwin11 http://192.168.0.9:32400](http://192.168.0.9:32400/) Drive G: mount to ghadmin \\192.168.0.6\Plex
- win11 Xeon-E5462 32GB ghamdin slwin11-zt17.198

| [slDVR remote](http://24.216.208.251:32500/) Lib | local mnt | netpath |
|-------------|------------------|---|
| gusHorrorClassic100 | G:\gusHorrorClassic100 | ghadmin \\192.168.0.6\Plex\gusHorrorClassic100 |
| gusMovies | G:\gusMovies | ghadmin \\192.168.0.6\Plex\gusMovies |
| gusProjects | G:\gusProjects | ghadmin \\192.168.0.6\Plex\gusProjects |
| gusShows | G:\gusMovies | ghadmin \\192.168.0.6\Plex\gusMovies |
| gusMusic | G:\gusMusic | ghadmin \\192.168.0.6\Plex\gusMusic |
| slDVR | D:\slShareD | D:\slShareD |
| slDVR | E:\slShareE | E:\slShareE |
|-------------|------------------|---|
|  | slDVR C: | local |
|  | slShareD D: | local |
|  | slShareE E: | local |
|  | plex 192.168.0.6 G: |  ghadmin \\192.168.0.6\ |

# cattv Netowrk [ghadmin https://my.zerotier.com/](https://my.zerotier.com/)

| cattv device | zt-ip drive | loc-ip map | size TB | used TB | date |
| -------: |------------------|---|--|--|--|
| slwin11 --> plex [slDVR remote](http://24.216.208.251:32500/) | 10.147.19.198 | 192.168.0.9 | 9.2 | 0.8 |
|  | C: | slDVR C: | 0.25 | 0.05 | 2024.01.06 |
|  | D: | slDriveD D: | 1.81 | 0.19 | 2024.01.06 |
|  | E: | slDriveE E: | 1.81 | 0.04 | 2024.01.06 |
| slsg2 map | G: | plex 192.168.0.6 G: | 5.33 | 0.47 | 2024.01.06 |
| cfplex ---> plex [cfPlex remote](http://test.christrees.com:32400/) | 10.147.19.228 | 192.168.6.3 | 16.x | 9.x |
|  | C: | cfPlex C: | 0.93 | 0.16 | 2024.01.06 |
| slwin11 map | D: | slDriveD 10.147.19.198 D: | 1.81 | 0.19 | 2024.01.06 |
| slwin11 map | E: | slDriveE 10.147.19.198 E: | 1.81 | 0.04 | 2024.01.06 |
| bu map | O: | plensds 192.168.6.10 O: | 1.09 | 0.70 | 2024.01.06 |
| sg map | P: | pshare 192.168.6.6 P: | 10.80 | 3.94 | 2024.01.06 |

# tv WIP
- ~~Clean up gusHPlex with gus~~
- Remove slPlex server from slsg2
  - ~~remove from christrees plex servers~~
  - clear client caches via christrees plex servers
  - ~~remove application from slsg2~~ [nuke-plex-on-qnap netstack/docs/lan/storage/qnap](https://netstack.org/docs/lan/storage/qnap/#nuke-plex-on-qnap)
- Client help links for RoKu, Web, Portal, FireTV bobo proof docs
  - test local client ghusadmin for media and livetv / dvr
  - test plex cloud client steve edwards for media and livetv
  - reset and test portial clients
  - create booboo, corbin and madison clients (local only??)
  - create booboo, corbin and madison plex libraries
  - test remote watch-with-me setups for plex, portals and web 
- [naming-and-organizing-your-plextv-show-files](https://support.plex.tv/articles/naming-and-organizing-your-tv-show-files/)
- Update [Media Inventory - google ss](https://docs.google.com/spreadsheets/d/1QtCblfwwH6PWYOKnIw2m4DKLni8KrVynXM6Xslb7mGg/edit#gid=0)
  - Keep cleaningup catrips and catnew put into plex lib
  - Cross reference Plex Media Server lists with plex server lib and physical location server/path
  - Maybe tie in view list and m8u files for reference
  - make sheet viewable from tv.2cld.net
  - Create wip list of things we want to put up and archieve
- Direct links to watch an episode
  - vlc m8u [youtube tutorial m3u playlist](https://www.youtube.com/watch?v=_NgxHmHk_ao)
  - example vlcSilicondust_192_168_6_11.m3u
    ```
    #EXTM3U
    #EXTINF:-1 tvg-id="cattuner 2.1" tvg-name="Channel 2.1" group-title="cattv | tuner",cattv channel 2.1
    http://192.168.6.11:5004/auto/v2.1
    #EXTINF:-1 tvg-id="cattuner 7.1" tvg-name="Channel 7.1" group-title="cattv | tuner",cattv channel 7.1
    http://192.168.6.11:5004/auto/v7.1
    #EXTINF:-1 tvg-id="cattuner 9.1" tvg-name="Channel 9.1" group-title="cattv | tuner",cattv channel 9.1
    http://192.168.6.11:5004/auto/v9.1
    #EXTINF:-1 tvg-id="cattuner 28.1" tvg-name="Channel 28.1" group-title="cattv | tuner",cattv channel 28.1
    http://192.168.6.11:5004/auto/v28.1
    #EXTINF:-1 tvg-id="cattuner 32.1" tvg-name="Channel 32.1" group-title="cattv | tuner",cattv channel 32.1
    http://192.168.6.11:5004/auto/v32.1
    #EXTINF:-1 tvg-id="cattuner 48.1" tvg-name="Channel 48.1" group-title="cattv | tuner",cattv channel 48.1
    http://192.168.6.11:5004/auto/v48.1
    #EXTINF:-1 tvg-id="cattuner 48.3" tvg-name="Channel 48.3" group-title="cattv | tuner",cattv channel 48.3
    http://192.168.6.11:5004/auto/v48.3
    #EXTINF:-1 tvg-id="cattuner 48.4" tvg-name="Channel 48.4" group-title="cattv | tuner",cattv channel 48.4
    http://192.168.6.11:5004/auto/v48.4
    ```
- Capture indexes ?
- Storage monitoring freespace, availibity, smart disk
- [DVD to Plex docs on netstack](https://netstack.org/docs/portals/plex/#dvd-to-plex)
- [cfPlex DVR on netstack](https://netstack.org/docs/portals/plex/#cPlex)
- [Capture tools and workflow - github](https://github.com/2cld/netstack/blob/master/docs/portals/streamstudio/README.md)
- [Edit tools and workflow - github](https://github.com/2cld/netstack/blob/master/docs/portals/streamstudio/README.md)


### Equipment Notes
- [HDMI to VHF ch3-4](https://www.amazon.com/Modulator-Coaxial-Converter-Digital-Adapter/dp/B09SG62RPZ/ref=sr_1_4?hvadid=182675282387&hvdev=c&hvlocphy=9018109&hvnetw=g&hvqmt=e&hvrand=4345337346546498937&hvtargid=kwd-21678298758&hydadcr=18920_9699079&keywords=hdmi+to+coaxial+cable+adapter&qid=1702340085&sr=8-4)
- [Wikipedia HDMI](https://en.wikipedia.org/wiki/High-bandwidth_Digital_Content_Protection)
- [hdfury](https://hdfury.com/shop/)
- [HDMI Splitters - youtube](https://www.youtube.com/watch?v=TkMIET3eEcc)
  - [Top pick $90](https://www.amazon.com/dp/B079HN327D)
  - [2nd $78](https://www.amazon.com/dp/B08KZTWQPT)
  - [3rd $35](https://www.amazon.com/dp/B0891WY8SF)
  - [4th $15](https://www.amazon.com/dp/B078Z5KPBL)
- [Cloner Alliance 4K pro](https://www.amazon.com/ClonerAlliance-Standalone-Instantly-Recording-Commentary/dp/B08T1PT4P4/ref=sr_1_1_sspa?crid=34AUK1PFCEUYT&keywords=cloneralliance%2Buhd%2Bpro%2C%2B4k%2Bvideo%2Brecorder&qid=1702404125&s=electronics&sprefix=cloner%2Celectronics%2C145&sr=1-1-spons&ufe=app_do%3Aamzn1.fos.18630bbb-fcbb-42f8-9767-857e17e03685&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1)
- [tbd]()
- [tbd]()

# ~~[slPlex](http://24.216.208.251:32400/)~~ unstable
- slPlex running on qnap fails.  Notes are hidden comments below.
<!--
- slPlex plex [local Plex server IP http://192.168.0.6:32400 on sg2](http://192.168.0.6:32400/)
- sg2 web admin portal [sg2-buadmin](http://192.168.0.6:8080/)
- slDVR plex [slDRV Plex backup server IP http://192.168.0.9:32400](http://192.168.0.9:32400/) Drive G: mount to ghadmin \\192.168.0.6\Plex
- having issues keeping slplex app running on qnap TS-431 NAS mapped media to slDVR plex running on slwin11
  
| [slPlex remote](http://24.216.208.251:32400/) Lib | local mnt | netpath |
|-------------|------------------|---|
| gusHorrorClassic100 | /share/CACHEDEV2_DATA/plex/gusHorrorClassic100 | ghadmin \\192.168.0.6\Plex\gusHorrorClassic100 |
| gusMovies | /share/CACHEDEV2_DATA/plex/gusMovies | ghadmin \\192.168.0.6\Plex\gusMovies |
| gusProjects | /share/CACHEDEV2_DATA/plex/gusProjects | ghadmin \\192.168.0.6\Plex\gusProjects |
| gusShows | /share/CACHEDEV2_DATA/plex/gusMovies | ghadmin \\192.168.0.6\Plex\gusMovies |
| gusMusic | /share/CACHEDEV2_DATA/plex/gusMusic | ghadmin \\192.168.0.6\Plex\gusMusic |
-->
