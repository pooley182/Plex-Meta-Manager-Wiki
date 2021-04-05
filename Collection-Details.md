Here is an example with multiple details being set:
```yaml
collections:
  IMDb Top 250:
    imdb_list: https://www.imdb.com/search/title/?groups=top_250&count=25
    sort_title: "+100"
    sync_mode: sync
    radarr_add: true
    show_filtered: true
    filters:
      original_language: en
  Reddit Top 250:
    trakt_list: https://trakt.tv/users/jay-greene/lists/reddit-top-250-2019-edition
    sort_title: "+101"
    sync_mode: sync
  Star Wars:
    tmdb_collection: 10
    tmdb_summary: 10
    tmdb_poster: 10
    tmdb_background: 10
  Pixar:
    studio: Pixar
    content_rating: PG
    url_poster: https://theposterdb.com/api/assets/29378/view?
    url_background: https://wallpaperaccess.com/full/331622.jpg
    summary: A collection of Pixar movies
    collection_order: alpha
  Robin Williams:
    actor: Robin Williams
    tmdb_biography: 2157
    tmdb_profile: 2157
    collection_mode: show_items
    collection_order: alpha
  Samuel L. Jackson:
    actor: tmdb
    tmdb_person: 2231
    collection_mode: show_items
    collection_order: alpha
  Marvel Cinematic Universe:
    tmdb_list: 7069903
    tmdb_description: 7069903
    tmdb_list_poster: 7069903
  28 Days/Weeks Later:
    tmdb_collection_details: 1565
    name_mapping: 28 Days-Weeks Later
```

The available collection details attributes for each collection are split into different sections

* [Settings Attributes](#setting-attributes)
* [Radarr Attributes](#radarr-attributes)
* [Sonarr Attributes](#sonarr-attributes)
* [Metadata Attributes](#metadata-attributes)
* [Summary Attributes](#summary-attributes)
* [Poster Attributes](#poster-attributes)
* [Background Attributes](#background-attributes)

## Setting Attributes
All the following attributes serve various functions as how the collection functions inside of Plex Meta Manager.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Schedule | `schedule` | Used to schedule this collection | [`schedule` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Schedule-Attribute) |
| Template | `template` | Used to specify a template and template variables to use for this collection | [`template` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Template-Attributes) |
| Run Again | `run_again` | Used to try and add all the items missing from the collection to the collection again after the daily run. | **boolean:** `true` or `false` |
| Sync Mode | `sync_mode` | Used to change how collection builders sync with this collection<br>**Default Mode:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection |
| Show Filtered Collections | `show_filtered` | Collection level `show_filtered` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Show Missing Collections | `show_missing` | Collection level `show_missing` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Save Missing Collections | `save_missing` | Collection level `save_missing` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Name Mapping | `name_mapping` | Used to specify the folder name in the [Image Assets Directory](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes#image-asset-directory) | Folder Name In Assets Directory |
| Test Mode | `test` | When running in Test Mode (`---run-tests` [option](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Local-Installation#run-tests)) only collections with `test: true` will be run<br>**Default:** false | **boolean:** `true` or `false` |

* **Name Mapping:** If your collection name contains characters that are not allowed in file paths (i.e. for windows `<`, `>`, `:`, `"`, `/`, `\`, `|`, `?`, `*` cannot be in the file path), but you want them in your collection name you can use the `name_mapping` attribute to specific this collection's name in the file system.

## Radarr Attributes
All the following attributes can override the global [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) attributes.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Radarr Add | `radarr_add` | Collection level `add` toggle for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |
| Radarr Root Folder | `radarr_folder` | Collection level `root_folder_path` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | Folder Path |
| Radarr Monitor | `radarr_monitor` | Collection level `monitor` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |
| Radarr Availability | `radarr_availability` | Collection level `availability` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | `announced`, `cinemas`, `released`, `db` |
| Radarr Quality Profile | `radarr_quality` | Collection level `quality_profile` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | Radarr Quality Profile |
| Radarr Tag | `radarr_tag` | Collection level `tag` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | List or comma-separated string of tags |
| Radarr Search | `radarr_search` | Collection level `search` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |

## Sonarr Attributes
All the following attributes can override the global [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) attributes.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Sonarr Add | `sonarr_add` | Collection level `add` toggle for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Root Folder | `sonarr_folder` | Collection level `root_folder_path` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | Folder Path |
| Sonarr Monitor | `sonarr_monitor` | Collection level `monitor` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | `all`, `future`, `missing`, `existing`, `pilot`, `first`, `latest`, `none` |
| Sonarr Quality Profile | `sonarr_quality` | Collection level `quality_profile` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | Sonarr Quality Profile |
| Sonarr Language Profile | `sonarr_language` | Collection level `language_profile` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | Sonarr Language Profile |
| Sonarr Series Type | `sonarr_series` | Collection level `series_type` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | `standard`, `daily`, `anime` |
| Sonarr Season Folder | `sonarr_season` | Collection level `season_folder` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Tag | `sonarr_tag` | Collection level `tag` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | List or comma-separated string of tags |
| Sonarr Search | `sonarr_search` | Collection level `search` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Cutoff Search | `sonarr_cutoff_search` | Collection level `cutoff_search` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |

## Metadata Attributes
All the following attributes update various details of the collection's Metadata.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| TMDb Person | `tmdb_person` | Used to change the collection's summary and poster to a TMDb Person's biography and profile as well as allow the people specified to be used in [Plex Searches](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Builders#plex-search) | TMDb Person ID (List or Comma-separated string) |
| Sort Title | `sort_title` | Used to change the collection's sort title | Text to change Sort Title |
| Content Rating | `content_rating` | Used to change the collection's content rating | Text to change Content Rating |
| Label | `label` | Used to change the collection's labels | Comma-separated string of labels to append or sync |
| Label Sync Mode | `label_sync_mode` | Used with `label` to change the label sync mode<br>**Default Mode:** `append` | `append`: Only Add Labels to the Item<br>`sync`: Add & Remove Labels from the Item |
| Collection Mode | `collection_mode` | Used to change the Collection Mode | `default`: Library default<br>`hide`: Hide Collection<br>`hide_items`: Hide Items in this Collection<br>`show_items`: Show this Collection and its Items |
| Collection Order | `collection_order` | Used to change the Collection Order | `release`: Order Collection by Release Dates<br>`alpha`: Order Collection Alphabetically | :heavy_check_mark: | :heavy_check_mark: |

* **Sort Title:** You can use `sort_title` to "promote" certain collections to the top of a library by creating a sort title starting with a `+` or "demote" certain collections to the bottom of a library by creating a sort title starting with a `~`.
* **Collection Order:** At this moment, Plex only allows filtering by alphabetical order or by release date, if you want Plex to allow a custom order please vote or post a comment on the Plex forum: [Topic - Plex Custom Collection Sorting](https://forums.plex.tv/t/custom-collection-sorting-machete-order/236226)

## Summary Attributes
All the following attributes update the summary of the collection from various sources.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Summary | `summary` | Used to change the collection's summary | Text to change Summary |
| TMDb Summary | `tmdb_summary` | Used to change the collection's summary to the TMDb Movie/Collection summary for a movie library or the TMDb Show summary for a show library  | TMDb Movie/Show/Collection ID |
| TMDb Description | `tmdb_description` | Used to change the collection's summary to the TMDb List Description | TMDb List ID |
| TMDb Biography | `tmdb_biography` | Used to change the collection's summary to the TMDb Person's biography | TMDb Person ID |
| TVDb Summary | `tvdb_summary` | Used to change the collection's summary to the TVDb Movie summary for a movie library or the TVDb Show summary for a show library  | TVDb Movie/Show ID or URL |
| TVDb Description | `tvdb_description` | Used to change the collection's summary to the TVDb List Description | TVDb List URL |
| Trakt Description | `trakt_description` | Used to change the collection's summary to the Trakt List Description | Trakt List URL |
| Letterboxd Description | `letterboxd_description` | Used to change the collection's summary to the Letterboxd List Description | Letterboxd List URL |

## Poster Attributes
All the following attributes update the poster of the collection from various sources.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| URL Poster<sup>2</sup> | `url_poster` | Used to change the collection's poster to the URL | URL of image publicly available on the internet |
| TMDb Poster<sup>2</sup> | `tmdb_poster` | Used to change the collection's poster to the TMDb Movie/Collection poster for a movie library or the TMDb Show poster for a show library | TMDb Movie/Show/Collection ID |
| TMDb List Poster<sup>2</sup> | `tmdb_list_poster` | Used to change the collection's poster to the TMDb List poster | TMDb List ID |
| TMDb Profile<sup>2</sup> | `tmdb_profile` | Used to change the collection's poster to the TMDb Person's profile | TMDb Person ID |
| TVDb Poster<sup>2</sup> | `tvdb_poster` | Used to change the collection's poster to the TVDb Movie poster for a movie library or the TVDb Show poster for a show library | TVDb Movie/Show ID or URL |
| File Poster<sup>2</sup> | `file_poster` | Used to change the collection's poster to the image in the file system | Path to image in the file system |

* If no poster is specified the script will look in the library's [Image Asset Directories](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes#image-asset-directory) for a folder named either the collection name or the `name_mapping` if specified and look for a `poster.ext` file in that folder (replacing .ext with the image extension).

## Background Attributes
All the following attributes update the background of the collection from various sources.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| URL Background<sup>3</sup> | `url_background` | Use to change the collection's background to the URL | URL of image publicly available on the internet |
| TMDb Background<sup>3</sup> | `tmdb_background` | Used to change the collection's background to the TMDb Movie/Collection background for a movie library or the TMDb Show background for a show library | TMDb Movie/Show/Collection ID |
| TVDb Background<sup>3</sup> | `tvdb_background` | Used to change the collection's background to the TVDb Movie background for a movie library or the TVDb Show background for a show library | TVDb Movie/Show ID or URL |
| File Background<sup>3</sup> | `file_background` | Used to change the collection's background to the image in the file system | Path to image in the file system |

* If no background is specified the script will look in the library's [Image Asset Directories](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes#image-asset-directory) for a folder named either the collection name or the `name_mapping` if specified and look for a `background.ext` file in that folder (replacing .ext with the image extension).
