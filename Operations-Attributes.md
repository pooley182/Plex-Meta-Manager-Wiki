There are multiple different Library Operations you can have preformed on each of your libraries.

You can define which operations you want to run under the `operations` attribute you can define per library.

A simple example of using some operations is below:
```yaml
libraries:
  Movies:
    metadata_path:
      - git: meisnate12/MovieCharts
    operations:
      mass_critic_rating_update: tmdb
      split_duplicates: true
```

The available operations attributes for each library are as follows

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Image Assets For All | `assets_for_all` | Search in assets for images for every item in your library | `true` or `false` |
| Delete Collections With Less | `delete_collections_with_less` | Deletes every collection with less then the given number | number greater then 0 |
| Delete Unmanaged Collections | `delete_unmanaged_collections` | Deletes every unmanaged collection | `true` or `false` |
| Mass Genre Update | `mass_genre_update` | Updates every item's genres in the library to the chosen site's genres | `tmdb`: Use TMDb for Genres<br>`tvdb`: Use TVDb for Genres<br>`omdb`: Use IMDb through OMDb for Genres |
| Mass Audience Rating Update | `mass_audience_rating_update` | Updates every item's audience rating in the library to the chosen site's rating | `tmdb`: Use TMDb for Rating<br>`omdb`: Use IMDb through OMDb for Rating |
| Mass Critic Rating Update | `mass_critic_rating_update` | Updates every item's critic rating in the library to the chosen site's rating | `tmdb`: Use TMDb for Rating<br>`omdb`: Use IMDb through OMDb for Rating |
| Mass Trakt Rating Update | `mass_trakt_rating_update` | Updates every movie/show's user rating in the library to match your custom rating on Trakt if there is one | `true` or `false` |
| Split Duplicates | `split_duplicates` | Splits all duplicate movies/shows found in this library | `true` or `false` |
| Radarr Add All | `radarr_add_all` | Adds every item in the library to Radarr | `true` or `false` |
| Sonarr Add All | `sonarr_add_all` | Adds every item in the library to Sonarr | `true` or `false` |
| [TMDb Collections](#tmdb-collections) | `tmdb_collections` | Builds Collections for every movie in your library based on TMDb Collections | [`tmdb_collections` mapping details](#tmdb-collections) |
| [Genre Mapper](#genre-mapper) | `genre_mapper` |Will check every item in your library and changed mapped genres | [`genre_mapper` mapping details](#genre-mapper) |

* When using `radarr_add_all` or `sonarr_add_all` the existing paths in plex will be used as the root folder of each item.
* If the paths in Plex are not the same as your Radarr/Sonarr paths you can use the `plex_path` and `radarr_path`/`sonarr_path` [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes)/[Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) details to convert the paths

## TMDb Collections
This operation will scan every movie in your library and create collections based on a `template` for those collections.

To run the most basic way you can just leave `tmdb_collections` Blank like so:

```yaml
library:
  Movies:
    operations:
      tmdb_collections:
```

This will run all collections found with the template that simply has `tmdb_collection_details: <<collection_id>>` in it.

To change the template for more complex runs you can use the `template` attribute to define the template that is used for the operation like so:

```yaml
library:
  Movies:
    operations:
      tmdb_collections:
        template:
          tmdb_collection_details: <<collection_id>>
          collection_order: release
```

* Remember if you define your own template you need to use the `<<collection_id>>` still to make the collection

There are two other attributes that can be used under `tmdb_collections`

* `exclude_ids`: list or comma separate list of TMDb Collection IDs to ignore 
* `remove_suffix`: Removes the suffix given from the TMDb Collection names. i.e. `Star Wars Collection` -> `Star Wars`

```yaml
library:
  Movies:
    operations:
      tmdb_collections:
        exclude_ids:
          - 10
        remove_suffix: Collection
        template:
          tmdb_collection_details: <<collection_id>>
          collection_order: release
```

* If the Collection is defined in another Metadata file (i.e. you define your own `Star Wars` Collection) then it will not run under `tmdb_collections` as long as the collection names match.

## Genre Mapper
You can use the `genre_mapper` operation to map genres in your library.

Each attribute under `genre_mapper` is a separate mapping and has two parts. 
* The key (`Action` in the example below) is what the genres will end up as.
* The value( `Action/Adventure, Action & Adventure` in the example below) is what genres you want mapped to the key.

So this example will change go through every item in your library and change the genre `Action/Adventure` or `Action & Adventure` to `Action` and `Romantic Comedy` to `Comedy`.

```yaml
library:
  Movies:
    operations:
      genre_mapper:
        Action: Action/Adventure, Action & Adventure
        Comedy: Romantic Comedy
```

you can also use a list:

```yaml
library:
  Movies:
    operations:
      genre_mapper:
        Action: 
         - Action/Adventure
         - Action & Adventure
        Comedy: Romantic Comedy
```
