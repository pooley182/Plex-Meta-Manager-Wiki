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

The only required attribute is `libraries` which is where you set up a configuration for each Plex Library you want the program to interact with. Using the library name as the base attribute you can set many different attributes individually per library or you can let them be inherited from the global value. A simple example of multiple libraries all using the global values is below:

```yaml
libraries:
  Movies:
    library_type: movie
  TV Shows:
    library_type: show
  Anime:
    library_type: show
```
**Note:** For this example to work, you would need to have the global `plex` attribute set up.

The available attributes for each library are as follows
| Name | Attribute | Allowed Values| Default | Required |
| :-- | :-- | :-- | :-- | :--: |
| Library Type | `library_type` | `movie` (For Movie Libraries)<br>`show` (For Show Libraries) | N/A | :heavy_check_mark: |
| Library Name | `library_name` | Library name (Only needed when trying to use multiple libraries with the same name) | Base Attribute Name | :x: |
| Metadata Path | `metadata_path` | System Location for the Metadata YAML file | Same directory as config YAML file | :x: |
| Plex Config | `plex` | [`plex` attribute details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Attributes) | global | :heavy_check_mark: Either here or globally |
| Radarr Config | `radarr` | [`radarr` attribute details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) | global | :x: |
| Sonarr Config | `sonarr` | [`sonarr` attribute details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) | global | :x: |
| Tautulli Config | `tautulli` | [`tautulli` attribute details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Tautulli-Attributes) | global | :x: |

**Note:** Each library must have a different name. If you want to use multiple libraries with the same name you can use the `library_name` attribute to specify the real Library Name and just have a place holder in the normal name. A simple example is below:

```yaml
libraries:
  Movies01:
    library_name: Movies
    library_type: movie
  Movies02:
    library_name: Movies
    library_type: movie
    plex:
      url: http://192.168.1.35:32400
      token: ####################
  TV Shows:
    library_type: show
  Anime:
    library_type: show
plex:
  url: http://192.168.1.12:32400
  token: ####################
```

Movies01, TV Shows, and Anime will all use the global plex server http://192.168.1.12:32400 while the library Movies02 will use the plex server http://192.168.1.35:32400 that is defined under its `plex` attribute over the global attribute.

You can find a template config file in [config/config.yml.template](config/config.yml.template)