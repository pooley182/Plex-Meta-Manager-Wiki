Configuring different options for Plex Meta Manager can be done in the Settings. These include enabling a cache to store each Plex GUID and its accompanying IDs to vastly speed up the execution of the script, defining the Image Asset Directory for local assets, setting a global Sync Mode, and many other display features.

A `settings` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `settings` mapping individually per library. Some settings can be individually set per collection using [Collection Details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Details).

Below is a `settings` mapping example and the full set of attributes:
```yaml
settings:
  cache: true
  cache_expiration: 60
  asset_directory: config/assets
  asset_folders: true
  sync_mode: append
  show_unmanaged: true
  show_filtered: false
  show_missing: true
  save_missing: true
  run_again_delay: 2
  released_missing_only: false
  create_asset_folders: false
  missing_only_released: false
  collection_minimum: 1
  delete_below_minimum: true
  error_webhooks:
  run_start_webhooks:
  run_end_webhooks:
  collection_creation_webhooks: 
  collection_addition_webhooks:
  collection_removing_webhooks:
  tvdb_language: eng
```

| Name | Attribute | Allowed Values | Default | Global Level | Library Level | Collection Level |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: |
| Cache | `cache` | Create a cache database for faster processing. The cache file is created in the same location as your config file.<br>**boolean:** true or false | true | :heavy_check_mark: | :x: | :x: |
| Cache Expiration | `cache_expiration` | Number of days before each cache mapping expires and has to be reloaded | 60 | :heavy_check_mark: | :x: | :x: |
| [Image Asset Directory](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Image-Asset-Directory) | `asset_directory` | System Locations For Image Assets | [Directory containing YAML config]/assets | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Image Asset Folders | `asset_folders` | Search in assets for named folders vs named files<br>i.e. `assets/Star Wars.png` vs `assets/Star Wars/poster.png` | true | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Create Asset Folders | `create_asset_folders` | When using `assets_for_all` if this is set to true PMM will create the Movie/Shows Folder for assets to be placed in | false | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Sync Mode | `sync_mode` | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection | append | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Collection Minimum | `collection_minimum` | Minimum items that must be found to add to a collection. | 1 | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Delete Below Minimum | `delete_below_minimum` | Delete existing collection if below the minimum.<br>**boolean:** true or false | false | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| [Run Again Delay](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Details#setting-attributes) | `run_again_delay` | Number of minutes to run `run_again` collections after daily run is finished<br>**number:** 0 or greater | 0 | :heavy_check_mark: | :x: | :x: |
| Missing Only Released | `missing_only_released` | Library Level toggle to filter missing items from a collection that have yet to be released.<br>**boolean:** true or false | false | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Show Unmanaged Collections | `show_unmanaged` | Show collections not managed by Plex Meta Manager at the end of each run<br>**boolean:** true or false | true | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Show Filtered Collections | `show_filtered` | Library Level toggle to show filtered collections<br>**boolean:** true or false | false | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Show Missing | `show_missing` | Library Level toggle to show movies/shows missing from collections<br>**boolean:** true or false | true | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Save Missing | `save_missing` | Library Level toggle to save movies/shows missing from collections to a file next to you Metadata file<br>**boolean:** true or false | true | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |

\* The file/folder name in your assets directory must match the folder name the media is stored in. i.e. if you have `Movies/Star Wars (1977)/Star Wars (1977) [1080p].mp4` then your asset directory would look at `assets/Star Wars (1977)/poster.png` for the poster
