
# Compose
docker-compose files for fast server deployment with docker containers
- can be used in (so far I've tested)
  - linux with docker
  - windows with docker desktop
  - macOS with docker desktop

## Getting Started
1. Copy this YAML to any directory in your system
https://github.com/djismgaming/compose/blob/main/docker-compose.yml
2. Run `docker-compose up -d` while in the directory where the YAML file resides

This will create and run containers of these apps:
- [linuxserver/plex](https://docs.linuxserver.io/images/docker-plex
) (media server)
- [linuxserver/lidarr](https://docs.linuxserver.io/images/docker-lidarr
) (music library enhancer)
- [linuxserver/radarr](https://docs.linuxserver.io/images/docker-radarr) (movie library enhancer)
- [linuxserver/sonarr](https://docs.linuxserver.io/images/docker-sonarr) (tv shows library enhancer)
- [linuxserver/transmission](https://docs.linuxserver.io/images/docker-transmission) (media downloader)
- [linuxserver/bazarr](https://docs.linuxserver.io/images/docker-bazarr) (subtitles downloader)
- [linuxserver/jackett](https://docs.linuxserver.io/images/docker-jackett) (downloader indexer)

This also takes into consideration that the directories to be used (which can be changed by you in the file) are
| Directory                     | Usage |
| ----------------------------- | ----- |
| `/mnt/user/appdata/<appname>` | for app configuration and data storage |
| `/mnt/user/media/tv`          | for tv shows media files |
| `/mnt/user/media/movies`      | for movies media files |
| `/mnt/user/media/music`       | for music media files |
| `/mnt/user/media/watch`       | for direct downloads from `jackett` to be added and downloaded by `transmission` |

Also takes into consideration that the environment variables (which can be changed by you in the file) to be passed on to the container are

| Directory                     | Usage |
| ----------------------------- | ----- |
| `PUID`                        | user to use for permissions in files created by the container |
| `PGID`                        | group to use for permissions in files created by the container |
| `TZ`                          | time-zone (optional, set to America/Puerto_Rico) |

## Optional - cleaning the yaml comments to leave a clean docker-compose file
(this is not required in order to use the YAML file with docker-compose)

These instructions are for use in Notepad++, my favorite editor in Windows :D

![cleaning the yaml file in notepad++](/assets/compose-clean-notepadd.png)