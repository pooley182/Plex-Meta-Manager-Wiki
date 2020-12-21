The script utilizes a YAML config file to load information to connect to the various APIs you can connect with. 

The YAML mappings that can be set in the config:
| Name | YAML Attribute | Required |
| :-- | :-- | :-- |
| Libraries | `libraries` | :heavy_check_mark: |
| Cache | `cache` | :x: |
| Plex | `plex` | :x: |
| TheMovieDb.org | `tmdb` | :x: |
| Radarr | `radarr` | :x: |
| Sonarr | `sonarr` | :x: |
| Tautulli | `tautulli` | :x: |
| Trakt.tv | `trakt` | :x: |
| MyAnimeList.net | `mal` | :x: |

The only required attribute is libraries which is where you set up a configuration for each Plex Library you want the program to interact with. Attributes can be set individually per library or can be inherited from the global value. A simple example is below:

```yaml
libraries:
  Movies:
    library_type: movie
  TV Shows:
    library_type: show
  Anime:
    library_type: show
```

Each library must have a different name and must have the `library_type` attribute which must be set to either `show` or `movie`. If you want to use multiple libraries with the same name you can use the `library_name` attribute to specify the real Library Name and just have a place holder in the normal name. A simple example is below:

```yaml
libraries:
  Movies01:
    library_name: Movies
    library_type: movie
  Movies02:
    library_name: Movies
    library_type: movie
  TV Shows:
    library_type: show
  Anime:
    library_type: show
```

As was stated earlier you can set a number of global attributes 

You can find a template config file in [config/config.yml.template](config/config.yml.template)