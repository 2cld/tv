[edit](https://github.com/2cld/tv/edit/main/README.md)

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

## tv.2cld Services

|[plex.tv](https://app.plex.tv/desktop/#!/) service name | owner | purpose | status | route |
|---|---|---|---|--|
| [cfPlex remote](http://test.christrees.com:32400/) | christrees | [Plex docs](https://netstack.org/docs/portals/plex) for [cfPlex on ghwinll local](https://192.168.) i5 GPU | live in cf | cf->32400->6.3 |
| [cfDVR remote](http://test.christrees.com:32500/) | tri484| [Plex docs](https://netstack.org/docs/portals/plex) for [cfDVR on sg local](https://cf.2cld.net/docs) Synology ds411 | live in cf | cf->32500->6.6 |
|---|---|---|---|--|
| [slPlex remote](http://24.216.208.251:32400/) | christrees | [Plex docs](https://netstack.org/docs/portals/plex) for [slPlex on sg2 local](http://192.168.0.6:32400/) 1u Dell | live in sl | sl->32400->0.6 |
| [slDVR remote](http://24.216.208.251:32500/) | christrees | [Plex docs](https://netstack.org/docs/portals/plex) for [slDVR on slwin11 local](http://192.168.0.9:32400/) qnap TS-431 | live in sl | sl->32500->0.9 |
|---|---|---|---|--|
| ~~[test 2020](http://test.christrees.com:2020/)~~ | christrees | cf old tnas ssh | old in cf | cf->2020->6.2:21 |
| [test 2021](http://test.christrees.com:2021/) | christrees | cf sg-cfDVR  ssh | live in cf | cf->2020->6.6:2020 |


need to sort cfPlex out

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


| cfDVR Lib | Storage location |
|-------------|------------------|     
| pshareMovies | /volume1/pshare/bs01Movie |
| pshareDVR | /volume1/pshare/bs01DVR |
| trinkDVR | /volume1/pshare/trinkDVR |

# [slPlex](http://24.216.208.251:32400/)
- slPlex plex [local Plex server IP http://192.168.0.6:32400 on sg2](http://192.168.0.6:32400/)
- sg2 web admin portal [sg2-buadmin](http://192.168.0.6:8080/)
- slDVR plex [slDRV Plex backup server IP http://192.168.0.9:32400](http://192.168.0.9:32400/) Drive G: mount to ghadmin \\192.168.0.6\Plex
  
| [slPlex remote](http://24.216.208.251:32400/) Lib | local mnt | netpath |
|-------------|------------------|---|
| gusHorrorClassic100 | /share/CACHEDEV2_DATA/plex/gusHorrorClassic100 | ghadmin \\192.168.0.6\Plex\gusHorrorClassic100 |
| gusMovies | /share/CACHEDEV2_DATA/plex/gusMovies | ghadmin \\192.168.0.6\Plex\gusMovies |
| gusProjects | /share/CACHEDEV2_DATA/plex/gusProjects | ghadmin \\192.168.0.6\Plex\gusProjects |
| gusShows | /share/CACHEDEV2_DATA/plex/gusMovies | ghadmin \\192.168.0.6\Plex\gusMovies |
| gusMusic | /share/CACHEDEV2_DATA/plex/gusMusic | ghadmin \\192.168.0.6\Plex\gusMusic |

# [slDVR](http://24.216.208.251:32500/)
- slDVR plex [slDRV Plex backup server IP http://192.168.0.9:32400](http://192.168.0.9:32400/) Drive G: mount to ghadmin \\192.168.0.6\Plex

| [slDVR remote](http://24.216.208.251:32500/) Lib | local mnt | netpath |
|-------------|------------------|---|
| gusProjects | G:/plex/gusProjects | ghadmin \\192.168.0.6\Plex\gusProjects |
| slDVR | D:/slShareD | ghadmin \\192.168.0.9\slShareD |
| slDVR | E:/slShareE | ghadmin \\192.168.0.9\slShareE |

# cattv [https://my.zerotier.com/](https://my.zerotier.com/)

| slwin11 | 10.147.19.198 | 192.168.0.9 |
| | D: | slDriveD D: |
| | E: | slDriveE E: |
| | G: | plex \\192.168.0.6 G: |
| cfplex | 10.147.19.228 | 192.168.6.3 |
| | O: | plensds \\192.168.6.10 O: |
| | P: | pshare \\192.168.6.6 P: |
| catmini | 10.147.19.59 | 192.168.6.33 |

# tv WIP
- ~~Clean up gusHPlex with gus~~
- Client help links for RoKu, Web, Portal, FireTV bobo proof docs
- More detailed index or links to Media Inventory
- Direct links to watch an episode
- Capture indexes ?
- Capture tools and workflow
- Edit tools and workflow


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
