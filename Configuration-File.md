The script utilizes a YAML config file to load information to connect to the various APIs you can connect with. 

The YAML mappings that can be set in the configuration file's root:
| Name | YAML Attribute | Required |
| :-- | :-- | :-- |
| Libraries | `libraries` | :heavy_check_mark: |
| Cache | `cache` | :x: |
| Plex | `plex` | :x: |
| TMDb | `tmdb` | :x: |
| Radarr | `radarr` | :x: |
| Sonarr | `sonarr` | :x: |
| Tautulli | `tautulli` | :x: |
| Trakt | `trakt` | :x: |
| MyAnimeList | `mal` | :x: |

* You can find a template config file in [config/config.yml.template](config/config.yml.template)