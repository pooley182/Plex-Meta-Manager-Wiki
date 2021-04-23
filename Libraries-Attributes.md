One of the two required configuration mappings is `libraries` which is where you set up a configuration for each Plex Library you want the program to interact with. 

Each library is defined by the mapping name which must be the same as the library name unless a different `library_name` is specified. You can either set attributes individually per library or you can let them be inherited from the global value. 

A simple example of multiple libraries all using the global values is below:
```yaml
libraries:
  Movies:
  TV Shows:
  Anime:
plex:
  url: http://192.168.1.12:32400
  token: ####################
```

The available attributes for each library are as follows

| Name | Attribute | Allowed Values | Default | Required |
| :--- | :--- | :--- | :---: | :---: |
| Library Name | `library_name` | Library name (Only needed when trying to use multiple libraries with the same name) | Base Attribute Name | :x: |
| Metadata Path | `metadata_path` | System Location for the Metadata YAML file | Same directory as config YAML file | :x: |
| Mass Genre Update | `mass_genre_update` | Updates every movie/show in the library to the chosen site's genres<br>`tmdb`: Use TMDb for Genres<br>`omdb`: Use IMDb through OMDb for Genres | No Update | :x: |
| Settings Mapping | `settings` | [`settings` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | global | :x: |
| Plex Mapping | `plex` | [`plex` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Attributes) | global | :heavy_check_mark: Either here or globally |
| Radarr Mapping | `radarr` | [`radarr` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) | global | :x: |
| Sonarr Mapping | `sonarr` | [`sonarr` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) | global | :x: |
| Tautulli Mapping | `tautulli` | [`tautulli` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Tautulli-Attributes) | global | :x: |

* Library mappings must have a colon (:) placed after them
* Each library must have a different name. If you want to use multiple libraries with the same name you can use the `library_name` attribute to specify the real Library Name and just have a placeholder as the library mapping name. A simple example is below:

    ```yaml
    libraries:
      Movies01:
        library_name: Movies
      Movies02:
        library_name: Movies
        plex:
          url: http://192.168.1.35:32400
          token: ####################
      TV Shows:
      Anime:
    plex:
      url: http://192.168.1.12:32400
      token: ####################
    ```

    Movies01, TV Shows, and Anime will all use the global plex server http://192.168.1.12:32400, defined using the global `plex` mapping. While the library, Movies02, will use the plex server http://192.168.1.35:32400 which is defined under its `plex` mapping over the global mapping.