The script utilizes a YAML config file to load information to connect to the various APIs you can connect with. 

The YAML mappings that can be set in the config:
| Name | YAML Attribute | Required |
| :-- | :-- | :-- |
| Plex | `plex` | :heavy_check_mark: |
| TheMovieDb.org | `tmdb` | :x:, but recommended |
| Radarr | `radarr` | :x: |
| Sonarr | `sonarr` | :x: |
| Tautulli | `tautulli` | :x: |
| Trakt.tv | `trakt` | :x: |
| MyAnimeList.net | `mal` | :x: |


You can find a template config file in [config/config.yml.template](config/config.yml.template)