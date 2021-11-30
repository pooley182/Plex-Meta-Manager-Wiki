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

* When using `radarr_add_all` or `sonarr_add_all` the existing paths in plex will be used as the root folder of each item.
* If the paths in Plex are not the same as your Radarr/Sonarr paths you can use the `plex_path` and `radarr_path`/`sonarr_path` [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes)/[Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) details to convert the paths
