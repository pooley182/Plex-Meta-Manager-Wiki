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

The available collection details for each collection are split into different sections

* [Settings Details](#setting-details)
* [Radarr Details](#radarr-details)
* [Sonarr Details](#sonarr-details)
* [Metadata Details](#metadata-details)
* [Item Metadata Details](#item-metadata-details)
* [Summary Details](#summary-details)
* [Poster Details](#poster-details)
* [Background Details](#background-details)

## Setting Details
All the following attributes serve various functions as how the collection functions inside of Plex Meta Manager.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Collection Name | `collection_name` | Used to specify the name off the collection in Plex as different then the mapping name. | Any String |
| Schedule | `schedule` | Used to schedule this collection | [`schedule` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Schedule-Detail) |
| Template | `template` | Used to specify a template and template variables to use for this collection | [`template` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Template-Attributes) |
| Run Again | `run_again` | Used to try and add all the items missing from the collection to the collection again after the daily run <br>**Default Mode:** `false`| **boolean:** `true` or `false` |
| Sync Mode | `sync_mode` | Used to change how collection builders sync with this collection<br>**Default Mode:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection |
| Collection Minimum | `collection_minimum` | Minimum items that must be found to add to a collection.<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | number greater then 0 |
| Delete Below Minimum | `delete_below_minimum` | Deletes the collection if below the minimum.<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Delete Not Scheduled | `delete_not_scheduled` | Deletes the collection if its skipped because its not scheduled.<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Validate Builders | `validate_builders` | When set to false the collection will not fail if one builder fails<br>**Default Mode:** `true` | **boolean:** `true` or `false` |
| Build Collection | `build_collection` | When set to false the collection won't be created but items can still be added to Radarr/Sonarr<br>**Default Mode:** `true` | **boolean:** `true` or `false` |
| Server Pre-Roll | `server_preroll` | Used to set the `Movie pre-roll video` Text box in Plex under Settings -> Extras | Any String |
| Missing Only Released | `missing_only_released` | Collection Level `missing_only_released` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Show Filtered Collections | `show_filtered` | Collection level `show_filtered` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Show Missing Collections | `show_missing` | Collection level `show_missing` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Save Missing Collections | `save_missing` | Collection level `save_missing` toggle<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | **boolean:** `true` or `false` |
| Ignore IDs | `ignore_ids` | Collection level `ignore_ids` which is combined with the library and global `ignore_ids`<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | List or comma-separated String of TMDb/TVDb IDs |
| Ignore IMDb IDs | `ignore_imdb_ids` | Collection level `ignore_imdb_ids` which is combined with the library and global `ignore_imdb_ids`<br>**Default:** [settings library value](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Settings-Attributes) | List or comma-separated String of IMDb IDs |
| Name Mapping | `name_mapping` | Used to specify the folder name in the [Image Assets Directory](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Image-Asset-Directory) | Folder Name In Assets Directory |
| Test Mode | `test` | When running in Test Mode (`--run-tests` [option](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Local-Installation#run-tests)) only collections with `test: true` will be run<br>**Default:** `false` | **boolean:** `true` or `false` |
| Collection Creation Webhooks | `collection_creation_webhooks` | Used to specify a collection creation webhook for just this collection | List of webhooks |
| Collection Addition Webhooks | `collection_addition_webhooks` | Used to specify a collection addition webhook for just this collection | List of webhooks |
| Collection Removal Webhooks | `collection_removal_webhooks` | Used to specify a collection removal webhook for just this collection | List of webhooks |

* **Name Mapping:** If your collection name contains characters that are not allowed in file paths (i.e. for windows `<`, `>`, `:`, `"`, `/`, `\`, `|`, `?`, `*` cannot be in the file path), but you want them in your collection name you can use the `name_mapping` attribute to specific this collection's name in the file system.
* **Server Pre-Roll:** You can run this with a [schedule](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Schedule-Detail) to change the pre-rolls automatically.

## Radarr Details
All the following attributes can override the global [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) attributes.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Radarr Add | `radarr_add` | Collection level `add` toggle for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |
| Radarr Add Existing | `radarr_add_existing` | Collection level `add_existing` toggle for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |
| Radarr Root Folder | `radarr_folder` | Collection level `root_folder_path` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | Folder Path |
| Radarr Monitor | `radarr_monitor` | Collection level `monitor` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |
| Radarr Availability | `radarr_availability` | Collection level `availability` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | `announced`, `cinemas`, `released`, `db` |
| Radarr Quality Profile | `radarr_quality` | Collection level `quality_profile` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | Radarr Quality Profile |
| Radarr Tag | `radarr_tag` | Collection level `tag` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | List or comma-separated string of tags |
| Radarr Search | `radarr_search` | Collection level `search` attribute override for Radarr<br>**Default:** [Radarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Radarr-Attributes) library value | **boolean:** `true` or `false` |
| Item Radarr Tag | `item_radarr_tag` | Used to append a tag in Radarr for every movie found by the builders that's in Radarr | List or comma-separated string of tags |
| Item Radarr Tag Remove | `item_radarr_tag.remove` | Used to remove existing tags in Radarr for every movie found by the builders that's in Radarr | List or comma-separated string of tags |
| Item Radarr Tag Sync | `item_radarr_tag.sync` | Matches the tags in Radarr for every movie found by the builders that's in Radarr with the provided tags | List or comma-separated string of tags |

## Sonarr Details
All the following attributes can override the global [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) attributes.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| Sonarr Add | `sonarr_add` | Collection level `add` toggle for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Add Existing | `sonarr_add_existing` | Collection level `add_existing` toggle for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Root Folder | `sonarr_folder` | Collection level `root_folder_path` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | Folder Path |
| Sonarr Monitor | `sonarr_monitor` | Collection level `monitor` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | `all`, `future`, `missing`, `existing`, `pilot`, `first`, `latest`, `none` |
| Sonarr Quality Profile | `sonarr_quality` | Collection level `quality_profile` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | Sonarr Quality Profile |
| Sonarr Language Profile | `sonarr_language` | Collection level `language_profile` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | Sonarr Language Profile |
| Sonarr Series Type | `sonarr_series` | Collection level `series_type` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | `standard`, `daily`, `anime` |
| Sonarr Season Folder | `sonarr_season` | Collection level `season_folder` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Tag | `sonarr_tag` | Collection level `tag` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | List or comma-separated string of tags |
| Sonarr Search | `sonarr_search` | Collection level `search` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Sonarr Cutoff Search | `sonarr_cutoff_search` | Collection level `cutoff_search` attribute override for Sonarr<br>**Default:** [Sonarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Sonarr-Attributes) library value | **boolean:** `true` or `false` |
| Item Sonarr Tag | `item_sonarr_tag` | Used to append a tag in Sonarr for every series found by the builders that's in Sonarr | List or comma-separated string of tags |
| Item Sonarr Tag Remove | `item_sonarr_tag.remove` | Used to remove existing tags in Sonarr for every series found by the builders that's in Sonarr | List or comma-separated string of tags |
| Item Sonarr Tag Sync | `item_sonarr_tag.sync` | Matches the tags in Sonarr for every series found by the builders that's in Sonarr with the provided tags | List or comma-separated string of tags |

## Metadata Details
All the following attributes update various details of the collection's Metadata.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| TMDb Person | `tmdb_person` | Used to change the collection's summary and poster to a TMDb Person's biography and profile as well as allow the people specified to be used in [Plex Searches](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Builders#plex-search) | TMDb Person ID (List or Comma-separated string) |
| Sort Title | `sort_title` | Used to change the collection's sort title | Text to change Sort Title |
| Content Rating | `content_rating` | Used to change the collection's content rating | Text to change Content Rating |
| Label | `label` | Used to append new labels to the collection | Comma-separated string of labels to append |
| Label Remove | `label.remove` | Used to remove existing labels from the collection | Comma-separated string of labels to remove |
| Label Sync | `label.sync` | Matches the labels of the collection to the labels provided (Leave blank to remove all labels) | Comma-separated string of labels to sync |
| Collection Mode | `collection_mode` | Used to change the Collection Mode | `default`: Library default<br>`hide`: Hide Collection<br>`hide_items`: Hide Items in this Collection<br>`show_items`: Show this Collection and its Items |
| Collection Order | `collection_order` | Used to change the Collection Order | `release`: Order Collection by Release Dates<br>`alpha`: Order Collection Alphabetically<br>`custom`: Order Collection Via the Builder Order | :heavy_check_mark: | :heavy_check_mark: |
| Collection Level | `collection_level` | Used to make episode or season collections from `plex_search` or `trakt_list` Builders | `season`: Collection contains seasons<br>`episode`: Collection contains episodes }
| Visible on Library | `visible_library` | Used to change collection visible on Library | `true`: Visible<br>`false`: Not Visible |
| Visible on Home | `visible_home` | Used to change collection visible on Home | `true`: Visible<br>`false`: Not Visible |
| Visible on Shared | `visible_shared` | Used to change collection visible on Shared Users' Home | `true`: Visible<br>`false`: Not Visible |

* **Sort Title:** You can use `sort_title` to "promote" certain collections to the top of a library by creating a sort title starting with a `+` or "demote" certain collections to the bottom of a library by creating a sort title starting with a `~`.
* **Custom Collection Order:** When using `collection_order: custom` you can only have a single builder in the collection.

## Item Metadata Details
All the following attributes update various details of the metadata for every item in the collection.

| Name | Attribute | Description | Allowed Values | Works with Movies | Works with Shows |
| :--- | :--- | :--- | :--- | :---: | :---: |
| Label | `item_label` | Used to append new labels to every movie/show in the collection | Comma-separated string of labels to append | :heavy_check_mark: | :heavy_check_mark: |
| Label Remove | `item_label.remove` | Used to remove existing labels from every movie/show in the collection | Comma-separated string of labels to remove | :heavy_check_mark: | :heavy_check_mark: |
| Label Sync | `item_label.sync` | Matches the labels of every movie/show in the collection to the labels provided (Leave blank to remove all labels) | Comma-separated string of labels to sync | :heavy_check_mark: | :heavy_check_mark: |
| Lock Posters | `item_lock_poster` | Locks the poster of every movie/show in the collection | `true` or `false`<br>**Default:** false | :heavy_check_mark: | :heavy_check_mark: |
| Lock Backgrounds | `item_lock_background` | Locks the background of every movie/show in the collection | `true` or `false`<br>**Default:** false | :heavy_check_mark: | :heavy_check_mark: |
| Lock Titles | `item_lock_title` | Locks the title of every movie/show in the collection | `true` or `false`<br>**Default:** false | :heavy_check_mark: | :heavy_check_mark: |
| Image Overlay | `item_overlay` | Adds and overlay image to the poster of every movie/show in the collection | [`item_overlay` details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Image-Overlay-Attribute) | :heavy_check_mark: | :heavy_check_mark: |
| Check For Assets | `item_assets` | Checks your assets folders for assets of every movie/show in the collection | `true` or `false`<br>**Default:** false | :heavy_check_mark: | :heavy_check_mark: |
| Refresh Item | `item_refresh` | Refreshes the metadata of every movie/show in the collection | `true` or `false`<br>**Default:** false | :heavy_check_mark: | :heavy_check_mark: |
| TMDb Season Titles | `item_tmdb_season_titles` | Changes the season titles of every show in the collection to match TMDb | `true` or `false`<br>**Default:** false | :x: | :heavy_check_mark: |
| Episode Sorting | `item_episode_sorting` | Changes the episode sorting of every show in the collection | `default`: Library default<br>`oldest`: Oldest first<br>`newest`: Newest first | :x: | :heavy_check_mark: |
| Keep Episodes | `item_keep_episodes` | Changes the keep episodes of every show in the collection | `all`: All episodes<br>`5_latest`: 5 latest episodes<br>`3_latest`: 3 latest episodes<br>`latest`: Latest episodes<br>`past_3`: Episodes added in the past 3 days<br>`past_7`: Episodes added in the past 7 days<br>`past_30`: Episodes added in the past 30 days | :x: | :heavy_check_mark: |
| Delete Episodes | `item_delete_episodes` | Changes the delete episodes of every show in the collection | `never`: Never<br>`day`: After a day<br>`week`: After a week<br>`refresh`: On next refresh | :x: | :heavy_check_mark: |
| Season Display | `item_season_display` | Changes the season display of every show in the collection | `default`: Library default<br>`show`: Show<br>`hide`: Hide | :x: | :heavy_check_mark: |
| Episode Ordering | `item_episode_ordering` | Changes the episode ordering of every show in the collection | `default`: Library default<br>`tmdb_aired`*: The Movie Database (Aired)<br>`tvdb_aired`: TheTVDB (Aired)<br>`tvdb_dvd`: TheTVDB (DVD)<br>`tvdb_absolute`: TheTVDB (Absolute) | :x: | :heavy_check_mark: |
| Metadata Language* | `item_metadata_language` | Changes the metadata language of every movie/show in the collection | `default`, `ar-SA`, `ca-ES`, `cs-CZ`, `da-DK`, `de-DE`, `el-GR`, `en-AU`, `en-CA`, `en-GB`, `en-US`, `es-ES`, `es-MX`, `et-EE`, `fa-IR`, `fi-FI`, `fr-CA`, `fr-FR`, `he-IL`, `hi-IN`, `hu-HU`, `id-ID`, `it-IT`, `ja-JP`, `ko-KR`, `lt-LT`, `lv-LV`, `nb-NO`, `nl-NL`, `pl-PL`, `pt-BR`, `pt-PT`, `ro-RO`, `ru-RU`, `sk-SK`, `sv-SE`, `th-TH`, `tr-TR`, `uk-UA`, `vi-VN`, `zh-CN`, `zh-HK`, `zh-TW` | :heavy_check_mark: | :heavy_check_mark: |
| Use Original Title* | `item_use_original_title` | Changes the use original title of every movie/show in the collection | `default`: Library default<br>`no`: No<br>`yes`: Yes | :heavy_check_mark: | :heavy_check_mark: |

\* Must be using the **New Plex Movie Agent** or the **New Plex TV Agent** 

## Summary Details
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

## Poster Details
All the following attributes update the poster of the collection from various sources.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| URL Poster<sup>2</sup> | `url_poster` | Used to change the collection's poster to the URL | URL of image publicly available on the internet |
| TMDb Poster<sup>2</sup> | `tmdb_poster` | Used to change the collection's poster to the TMDb Movie/Collection poster for a movie library or the TMDb Show poster for a show library | TMDb Movie/Show/Collection ID |
| TMDb List Poster<sup>2</sup> | `tmdb_list_poster` | Used to change the collection's poster to the TMDb List poster | TMDb List ID |
| TMDb Profile<sup>2</sup> | `tmdb_profile` | Used to change the collection's poster to the TMDb Person's profile | TMDb Person ID |
| TVDb Poster<sup>2</sup> | `tvdb_poster` | Used to change the collection's poster to the TVDb Movie poster for a movie library or the TVDb Show poster for a show library | TVDb Movie/Show ID or URL |
| File Poster<sup>2</sup> | `file_poster` | Used to change the collection's poster to the image in the file system | Path to image in the file system |

* If no poster is specified the script will look in the library's [Image Asset Directories](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Image-Asset-Directory) for a folder named either the collection name or the `name_mapping` if specified and look for a `poster.ext` file in that folder (replacing .ext with the image extension).

## Background Details
All the following attributes update the background of the collection from various sources.

| Name | Attribute | Description | Allowed Values |
| :--- | :--- | :--- | :--- |
| URL Background<sup>3</sup> | `url_background` | Use to change the collection's background to the URL | URL of image publicly available on the internet |
| TMDb Background<sup>3</sup> | `tmdb_background` | Used to change the collection's background to the TMDb Movie/Collection background for a movie library or the TMDb Show background for a show library | TMDb Movie/Show/Collection ID |
| TVDb Background<sup>3</sup> | `tvdb_background` | Used to change the collection's background to the TVDb Movie background for a movie library or the TVDb Show background for a show library | TVDb Movie/Show ID or URL |
| File Background<sup>3</sup> | `file_background` | Used to change the collection's background to the image in the file system | Path to image in the file system |

* If no background is specified the script will look in the library's [Image Asset Directories](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Image-Asset-Directory) for a folder named either the collection name or the `name_mapping` if specified and look for a `background.ext` file in that folder (replacing .ext with the image extension).
