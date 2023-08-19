[edit](https://github.com/2cld/tv/edit/main/README.md)

| [plex.tv](https://app.plex.tv/desktop/#!/) server name | owner | purpose | status | route |
|---|---|---|---|--|
| [cfPlex](http://test.christrees.com:32400/) | christrees | plex on cfPlex win11 i5 | live in cf | cf->32400->6.3 [doc cfPlex](#cfPlex) |
| [cfDVR](http://test.christrees.com:32500/) | christrees | plex on bu Synology ds411| live in cf | cf->32500->6.6 [doc cfDVR](#cfDVR) |
| [gusHPlex]() | christrees | sl local | live in sl | sl->32400->?? [doc gusHPlex](#gusHPlex) on gusHPlaptop |
| [test 2020](http://test.christrees.com:2020/) | christrees | cf sg-cfPlex ssh | live in cf | cf->2020->6.2:21 sg cfPlex-trinkDVR |
| [test 2021](http://test.christrees.com:2021/) | christrees | cf sg-cfDVR  ssh | live in cf | cf->2020->6.6:2020 cfDVR-trinDVR |

# Plex Document links
- Plex playback [setup and testing](#plex-playback)
- Plex dvr [setup and testing](#plex-dvr)
- Plex library [setup and updates](#plex-library) and [shared media library](https://docs.google.com/spreadsheets/d/1QtCblfwwH6PWYOKnIw2m4DKLni8KrVynXM6Xslb7mGg/edit#gid=0)
- Plex [server settings](#plex-server)
- Plex [client settings](#plex-client)
- Plex [remote ssh](#remote-ssh-management)

# cfPlex
<!--
[plex.tv --- ghwin11.test.christrees 32800](http://test.christrees.com:32800/) cf->32800->6.3 cfPlex
  - cfPlex ghadmin windows 11
  - i5 Intel
  - Nividia GTX 660
  - Primary plex server
-->

| cfPlex Lib | local mnt | netpath |
|-------------|------------------|---|
| catMovies | M:\CATMovies | MediaShare \\192.168.6.2\CATMovies |
| catNewMovies | P:\catNew | pshare \\192.168.6\catNew |
| pMediaMovie | M:\pMediaMovie | MediaShare \\192.168.6.2\pMediaMovie |
| pMediaMoviesAnimated | M:\pMediaMoviesAnimated | MediaShare \\192.168.6.2\pMediaMoviesAnimated |
| pMediaShortsAnimated | M:\pMediaShortsAnimated | MediaShare \\192.168.6.2\pMediaShortsAnimated |
| catScratch | C:\plexData | none |
| catTVShows | M:\CATTVShows | MediaShare \\192.168.6.2\CATTVShows |
| pMediaTVShows | M:\pMediaTVShows | MediaShare \\192.168.6.2\pMediaTVShows |
| pMediaTVShowsAnimated | M:\pMediaTVShowsAnimated | MediaShare \\192.168.6.2\pMediaTVShowsAnimated |
| StarTrek | O:\plexdvr\startrekDVR | plexnsds \\192.168.6.10\plexdvr\startrekDVR |
| gusTestRemote | G:\gusDVRStoogies |  gusHPlexSFEPart \\10.147.17.66\gusDVRStoogies |
| gusTestLocal | C:\plexData\The Three Stooges (1934) | none |

# cfDVR plex
<!--
[plex.tv - bs01ds411.test.christrees 32700](http://test.christrees.com:32700/) cf->32700->6.103pf->2.105 bs01ds411
  - bs01ds411 Synology DS411 NAS
  - pshare \\192.168.2.105
  - storage and DVR for cf
  - Used as plexDVR
-->

| cfDVR Lib | Storage location |
|-------------|------------------|     
| pshareMovies | /volume1/pshare/bs01Movie |
| pshareDVR | /volume1/pshare/bs01DVR |

# gusHPlex

| gusHPlex Lib | Storage location |
|-------------|------------------|     
| gusMovies | gusHPLaptop E:\gusHPlexSFEPart\gusMovies |
| gusShows | gusHPLaptop E:\gusHPlexSFEPart\gusShows |
| gusHorrorClassic100 | gusHPLaptop E:\gusHPlexSFEPart\gusHorrorClassic100 |
| gusMusic | gusHPLaptop E:\gusHPlexSFEPart\gusMusic |
| gusVHSProject | gusHPLaptop E:\gusHPlexSFEPart\gusVHSProject |
| gusDVR | gusHPLaptop E:\gusHPlexSFEPart\gusDVR |
| gusDVRStoogies | gusHPLaptop E:\gusHPlexSFEPart\gusDVRStoogies |
| gusDVRCartoons | gusHPLaptop E:\gusHPlexSFEPart\gusDVRCartoons |

# ghadmin plex (none right now)

# steveedwards808
experimental plex running in proxmox on coreduo macmini. only good for sldvr

# tri484
Trink local plex in hmb running on truenas
- [plex.tv --- tri484]()

## Plex playback
Setup and testing 

| Plex server | notes |
|--------|------|
| gusHPlex | mainly for sl-DVR |
| cfPlex | has cpu and gpu |
| cfDVR | ds411 for cf-DVR and storage |


## Plex dvr
- Login to [app.plex.tv](https://app.plex.tv/desktop/#!/) 
- goto wrench icon in upper right
- on left, select the server you want to manage
- select "Manage" -  "Live TV & DVR" near bottom of list
- add new tuners
- click on existing tuner channels "xx enabled" to access channel mapping function

## Plex library
- Update [shared media library](https://docs.google.com/spreadsheets/d/1QtCblfwwH6PWYOKnIw2m4DKLni8KrVynXM6Xslb7mGg/edit#gid=0) as you modify plex libs
- Login to [app.plex.tv](https://app.plex.tv/desktop/#!/) 
- goto wrench icon in upper right
- on left, select the server you want to manage
- select "Manage" -  "Library" near bottom of list
- add, delete or edit the library
- edit will allow you to add additional directories local to that plex server

## Plex client
- Login to [app.plex.tv](https://app.plex.tv/desktop/#!/) and client link [plex.tv/link](https://www.plex.tv/link/)
- use cfDVR for recordings
- use cfPlex for viewing and LiveTV
- Verify client settings location varies on each client
  - Quality MAX
  - Play at original quality
  - may want to mess with beta stuff as they are adjusting for various player updates

## Plex server
- see [https://github.com/2cld/netstack/tree/master/docs/portals/plex](https://github.com/2cld/netstack/tree/master/docs/portals/plex)

## Remote ssh management
ssh shell access for user data management
- [christrees.com/dns](https://domains.google.com/registrar/christrees.com/dns)
- cfPlex test.christrees.com -> 24.149.22.11:2020 -> 192.168.6.2:21
- cfDVR test.christrees.com -> 24.149.22.11:2021 -> 192.168.6.6:2020
- [port forward](http://192.168.6.1/#/html/advanced/security/advanced_security_advancedportforwarding.html)
- cfDVR ssh -p 2021 trink@test.christrees.com
- trink@cfDVR:~$ ls /volume1/pshare/trinkDVR/
- sg-cfPlex ssh -p 2020 trink@test.christrees.com
- trink@cf-sg2:~$ ls /mnt/catpool/trink/trinkDVR/

---
---
[pluto.tv - Stan Against Evil](https://pluto.tv/en/live-tv/5e82547b6b3df60007fec2b5) Weeknights 8-10pm CST Slightly off IF
  - [Season 1](https://www.imdb.com/title/tt5722214/episodes?season=1)
    - [ ] S1-E1 Dig Me Up, Dig Me Down
    - [ ] S1-E2 Know, Know, Know Your Goat
    - [ ] S1-E3 Let Your Love Groan
    - [ ] S1-E4 Life Orr Death
    - [x] S1-E5 Ouija Bored
    - [ ] S1-E6 I'm Gleaning My Coven
    - [ ] S1-E7 Spider Walk with Me
    - [ ] S1-E8 6Level Boss
  - [Season 2](https://www.imdb.com/title/tt5722214/episodes?season=2)
    - [x] S2-E1 The Black Hat Society Part 1
    - [x] S2-E2 The Black Hat Society Part 2
    - [x] S2-E3 Curse of the Werepony
    - [x] S2-E4 Girls' Night
    - [ ] S2-E5 The Eyes of Evie Barret
    - [ ] S2-E6 Hex Marks the Tot
    - [ ] S2-E7 Mirror Mirror
    - [ ] S2-E8 A Hard Day's Night
  - [Season 3](https://www.imdb.com/title/tt5722214/episodes?season=3)
    - [ ] S3-E1 Hell Is What You Make It
    - [ ] S3-E2 The Hex Files
    - [ ] S3-E3 Larva My Life
    - [ ] S3-E4 The Demon Who Came in from the Heat
    - [ ] S3-E5 Nubbin but Trouble
    - [ ] S3-E6 Vampire Creek
    - [ ] S3-E7 Intensive Scare Unit
    - [ ] S3-E8 Stan Against Evie

---
[What we do in the Shadows](https://www.imdb.com/title/tt7908628/episodes/?ref_=tt_ov_epl) 
  - [Season 1](https://www.imdb.com/title/tt7908628/episodes?season=1)
    - [ ] S1-E1 
    - [ ] S1-E2 

## Test
- [Cedar Falls Library Login](https://wcfpl.ent.sirsi.net/client/en_US/cfpl/?)
- [Young Sheldon](https://www.paramountplus.com/shows/video/KqG3_6fFfvcsMYkSXPvK58lCFtnykHxu/)
- [Wikipedia HDMI](https://en.wikipedia.org/wiki/High-bandwidth_Digital_Content_Protection)
- [hdfury](https://hdfury.com/shop/)

