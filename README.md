[edit](https://github.com/2cld/tv/edit/main/README.md)

# christrees plex
[plex.tv --- ghwin11.test.christrees 32800](http://test.christrees.com:32800/) cf->32800->6.103pf->2.99 ghwin11
  - ghwin11 ghadmin windows 11
  - i5 Intel
  - Nividia GTX 660
  - Primary plex server

| ghwin11 Lib | local mnt | netpath |
|-------------|------------------|---|
| gusMovies | P:\gusMovies | pshare \\192.168.2.105 |
| gusShows | P:\gusShows | pshare \\192.168.2.105 |
| HorrorClassic100 | P:\HorrorClassics100 | pshare \\192.168.2.105 |
| bs01DVR | P:\bs01DVR | pshare \\192.168.2.105 |
| bs01Movie | P:\bs01Movie | pshare \\192.168.2.105 |
| catNew | P:\catNew | pshare \\192.168.2.105 |
| catRip | P:\catRip | pshare \\192.168.2.105 |
| tvANew | P:\tvANew | pshare \\192.168.2.105 |
| tvAOld | P:\tvAOld | pshare \\192.168.2.105 |
| tvNew | P:\tvNew | pshare \\192.168.2.105 |
| tvOld | P:\tvOld | pshare \\192.168.2.105 |

# bs01ds411 plex
[plex.tv - bs01ds411.test.christrees 32700](http://test.christrees.com:32700/) cf->32700->6.103pf->2.105 bs01ds411
  - bs01ds411 Synology DS411 NAS
  - pshare \\192.168.2.105
  - storage and DVR for cf
  - Used as plexDVR

| bs01ds411 Lib | Storage location |
|-------------|------------------|     
| pshareMovies | /volume1/pshare/bs01Movie |
| pshareDVR | /volume1/pshare/bs01DVR |

# tnasplex plex
[plex.tv ---- docker.test.christrees 32500](http://test.christrees.com:32500/) cf->32500->6.103pf->2.2 tnasplex
  - truenas docker app
  - trink DVR currently
 
| tnasplex Lib | Storage location |
|-------------|------------------|     
| catdvr | /media/catdvr |
| trinkdvr | /media/trinkdvr |

# gusHPlex plex
[plex.tv --- gusHPlex]() sl->32400->?? gusHPlex on gusHPlaptop
  - ghHPlaptop in sl
  - gusRips and sl DVR.

| gusHPlex Lib | Storage location |
|-------------|------------------|     
| gusMovies | ? |
| gusShows | ? |
| HorrorClassic100 | ? |
| gusRip | ? |
| gusVCRProject | ? |

# ghadmin plex (none right now)

# steveedwards808 plex
experimental plex running in proxmox on coreduo macmini. only good for sldvr

[plex.tv --- slPlex]() - vm on old macmini

## tri484 plex
Trink local plex in hmb running on truenas

[plex.tv --- tri484]()

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

# Notes
- [plex.tv --- ghwin11.test.christrees 32800](http://test.christrees.com:32800/) cf->32800->6.103pf->2.99 ghwin11
- [plex.tv - bs01ds411.test.christrees 32700](http://test.christrees.com:32700/) cf->32700->6.103pf->2.105 bs01ds411 (DVR)
- [plex.tv ---- docker.test.christrees 32600](http://test.christrees.com:32600/) cf->32600->6.103pf->2.103 (docker)
- [plex.tv ---- docker.test.christrees 32500](http://test.christrees.com:32500/) cf->32500->6.103pf->2.2 tnasplex (DVR)
- [plex.tv  cattvwin10.test.christrees 32400](http://test.christrees.com:32400/) cf->32400->6.180 cattvwin10~~ (removed)
- [plex.tv  gusHPlex 32400]() sl->32400->?? gusHPlex on gusHPlaptop (DVR)

