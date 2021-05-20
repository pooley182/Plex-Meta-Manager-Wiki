One of the two required configuration mappings is `libraries` which is where you set up a configuration for each Plex Library you want the program to interact with. 

Each library is defined by the mapping name which must be the same as the library name unless a different `library_name` is specified. You can either set attributes individually per library or you can let them be inherited from the global value. 

A simple example of multiple libraries all using the global values is below:
```yaml
libraries:
  Movies:
    metadata_path:
      - file: config/Movies.yml
      - git: meisnate12/MovieCharts
      - git: meisnate12/Studios
      - git: meisnate12/IMDBGenres
      - git: meisnate12/People
  TV Shows:
    metadata_path:
      - file: config/TV Shows.yml
      - git: meisnate12/ShowCharts
      - git: meisnate12/Networks
  Anime:
    metadata_path:
      - file: config/Anime.yml
      - git: meisnate12/AnimeCharts
plex:
  url: http://192.168.1.12:32400
  token: ####################
```

The available attributes for each library are as follows

| Name | Attribute | Allowed Values | Default | Required |
| :--- | :--- | :--- | :---: | :---: |
| [Library Name](#library-name) | `library_name` | Library name (Only needed when trying to use multiple libraries with the same name) | Base Attribute Name | :x: |
| [Metadata Path](#metadata-path) | `metadata_path` | Location for your Metadata YAML files | Same directory as config YAML file | :x: |
| Mass Genre Update | `mass_genre_update` | Updates every item's genres in the library to the chosen site's genres<br>`tmdb`: Use TMDb for Genres<br>`omdb`: Use IMDb through OMDb for Genres | No Update | :x: |
| Mass Audience Rating Update | `mass_audience_rating_update` | Updates every item's audience rating in the library to the chosen site's rating<br>`tmdb`: Use TMDb for Rating<br>`omdb`: Use IMDb through OMDb for Rating | No Update | :x: |
| Mass Critic Rating Update | `mass_critic_rating_update` | Updates every item's critic rating in the library to the chosen site's rating<br>`tmdb`: Use TMDb for Rating<br>`omdb`: Use IMDb through OMDb for Rating | No Update | :x: |
| Radarr Add All | `radarr_add_all` | Adds every item in the library to Radarr | No Adds | :x: |
| Sonarr Add All | `sonarr_add_all` | Adds every item in the library to Sonarr | No Adds | :x: |
| Settings Mapping | `settings` | [`settings` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | global | :x: |
| Plex Mapping | `plex` | [`plex` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Attributes) | global | :heavy_check_mark: Either here or globally |
| Radarr Mapping | `radarr` | [`radarr` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) | global | :x: |
| Sonarr Mapping | `sonarr` | [`sonarr` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) | global | :x: |
| Tautulli Mapping | `tautulli` | [`tautulli` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Tautulli-Attributes) | global | :x: |

* Library mappings must have a colon `:` placed after them

## Library Name

Each library must have a different name. If you want to use multiple libraries with the same name you can use the `library_name` attribute to specify the real Library Name and just have a placeholder as the library mapping name. A simple example is below:

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

* Movies01, TV Shows, and Anime will all use the global plex server http://192.168.1.12:32400, defined using the global `plex` mapping. While the library, Movies02, will use the plex server http://192.168.1.35:32400 which is defined under its `plex` mapping over the global mapping.

## Metadata Path
You can define Metadata Files by using `metadata_path`. They can either be on the local system, online at an url, or directly from the [Plex Meta Manager Configs](https://github.com/meisnate12/Plex-Meta-Manager-Configs) repository.

By default, when `metadata_path` is missing the script will look in your config directory for `<MAPPING_NAME>.yml` so `Movies.yml` in the example below.
```yaml
libraries:
  Movies:
```
To use a Metadata File online add `file` under metadata set to the system path of the yaml file.
```yaml
libraries:
  Movies:
    metadata_path: 
      file: /config/My Movies.yml
```
To use a Metadata File online add `url` under metadata set to the url of the yaml file.
```yaml
libraries:
  Movies:
    metadata_path:
      url: http://somesite.com/metadata_file.yml
```
To use a Metadata File from the [Plex Meta Manager Configs](https://github.com/meisnate12/Plex-Meta-Manager-Configs) repository add `git` under metadata set to the oath in the repository.
```yaml
libraries:
  Movies:
    metadata_path:
      git: meisnate12/Charts
```
You can specify multiple paths of any type using a list like below.
```yaml
libraries:
  Movies:
    metadata_path:
      - file: /config/My Movies.yml
      - url: http://somesite.com/people_collections.yml
      - git: meisnate12/Charts
      - git: meisnate12/Studios
```