One of the two required configuration mappings is `libraries` which is where you set up a configuration for each Plex Library you want the program to interact with. 

Each library is defined by the mapping name which must be the same as the library name unless a different `library_name` is specified. You can either set attributes individually per library or you can let them be inherited from the global value. 

A simple example of multiple libraries all using the global values is below:
```yaml
libraries:
  Movies:
    library_type: movie
  TV Shows:
    library_type: show
  Anime:
    library_type: show
plex:
  url: http://192.168.1.12:32400
  token: ####################
```

The available attributes for each library are as follows
| Name | Attribute | Allowed Values | Default | Required |
| :-- | :-- | :-- | :--: | :--: |
| Library Type | `library_type` | `movie` (For Movie Libraries)<br>`show` (For Show Libraries) | N/A | :heavy_check_mark: |
| Library Name | `library_name` | Library name (Only needed when trying to use multiple libraries with the same name) | Base Attribute Name | :x: |
| Metadata Path | `metadata_path` | System Location for the Metadata YAML file | Same directory as config YAML file | :x: |
| Plex Mapping | `plex` | [`plex` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Attributes) | global | :heavy_check_mark: Either here or globally |
| Radarr Mapping | `radarr` | [`radarr` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) | global | :x: |
| Sonarr Mapping | `sonarr` | [`sonarr` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) | global | :x: |
| Tautulli Mapping | `tautulli` | [`tautulli` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Tautulli-Attributes) | global | :x: |

* Each library must have a different name. If you want to use multiple libraries with the same name you can use the `library_name` attribute to specify the real Library Name and just have a place holder in the library map. A simple example is below:

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

    Movies01, TV Shows, and Anime will all use the global plex server http://192.168.1.12:32400, defined using the global `plex` mapping. While the library, Movies02, will use the plex server http://192.168.1.35:32400 which is defined under its `plex` mapping over the global mapping.