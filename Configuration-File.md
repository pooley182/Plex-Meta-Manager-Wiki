The script utilizes a YAML config file to load information to connect to the various APIs you can connect with. 

The YAML mappings that can be set in the configuration file's root:
| Name | YAML Attribute | Required |
| :-- | :-- | :-- |
| [Libraries](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Libraries-Attributes) | `libraries` | :heavy_check_mark: |
| [Cache](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Cache-Attributes) | `cache` | :x: |
| [Plex](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Attributes) | `plex` | :x: |
| [TMDb](https://github.com/meisnate12/Plex-Meta-Manager/wiki/TMDb-Attributes) | `tmdb` | :x: |
| [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) | `radarr` | :x: |
| [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) | `sonarr` | :x: |
| [Tautulli](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Tautulli-Attributes) | `tautulli` | :x: |
| [Trakt](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Trakt-Attributes) | `trakt` | :x: |
| [MyAnimeList](https://github.com/meisnate12/Plex-Meta-Manager/wiki/MyAnimeList-Attributes) | `mal` | :x: |

* You can find a template config file in [config/config.yml.template](config/config.yml.template)