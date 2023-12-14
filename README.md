[edit](https://github.com/2cld/tv/edit/main/README.md)

## tv.2cld Media Guides

| Media Guide | Location | Type |
|---|---|---|
| [Gus media guide](../media/gus/README.md) | Movies, TV Shows, Music | [cfPlex - gus]() |
| [CAT media guide](../media/cat/README.md) | Movies, TV Shows, Music | [cfPlex - cat]() | 
| [cfPlex Live TV guide]() | Live TV | [cfPlex - LiveTV]() | 

## tv.2cld Services

|[plex.tv](https://app.plex.tv/desktop/#!/) service name | owner | purpose | status | route |
|---|---|---|---|--|
| [cfPlex](http://test.christrees.com:32400/) | christrees | [Plex](https://netstack.org/docs/portals/plex) on cfPlex [docs](https://cf.2cld.net/docs) win11 i5 | live in cf | cf->32400->6.3 [doc cfPlex](https://netstack.org/docs/portals/plex#cfPlex) |
| [cfDVR](http://test.christrees.com:32500/) | christrees | [Plex](https://netstack.org/docs/portals/plex) on cfDVR [docs](https://cf.2cld.net/docs) Synology ds411 | live in cf | cf->32500->6.6 [doc cfDVR](https://netstack.org/docs/portals/plex#cfDVR) |
| [gusHPlex](http://24.216.208.251:32400) remove | christrees | sl local | live in sl | sl->32400->?? [doc gusHPlex](#gusHPlex) on gusHPlaptop |
| [slPlex](http://24.216.208.251:32400) todo | christrees | [Plex](https://netstack.org/docs/portals/plex) ?? local [docs](https://cf.2cld.net/docs) | live in sl via cf | sl->32400->?? [doc slPlex](#slPlex) on ?? |
| [test 2020](http://test.christrees.com:2020/) | christrees | cf sg-cfPlex ssh | live in cf | cf->2020->6.2:21 sg cfPlex-trinkDVR |
| [test 2021](http://test.christrees.com:2021/) | christrees | cf sg-cfDVR  ssh | live in cf | cf->2020->6.6:2020 cfDVR-trinDVR |
| [moviesanywhere my movies](https://moviesanywhere.com/login) | christrees | cloud | live | cloud |
| [youtube my movies](https://www.youtube.com/feed/storefront?bp=EgCSAQMIyQSiBQIoBA%3D%3D)  | christrees | cloud | live | cloud |



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

# gusHPlex - REMOVE with gus

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

## Equipment Setup
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
