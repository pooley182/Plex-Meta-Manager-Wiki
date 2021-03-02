Configuring different options for Plex Meta Manager can be done in the Settings. These include enabling a cache to store each Plex GUID and its accompanying IDs to vastly speed up the execution of the script, defining the Image Asset Directory for local assets, setting a global Sync Mode, and many other display features.

A `settings` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `settings` mapping individually per library. Some settings can be individually set per collection using [Collection Details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Details).

Below is a `settings` mapping example and the full set of attributes:
```yaml
settings:
  cache: true
  cache_expiration: 60
  asset_directory: config/assets
  sync_mode: append
  run_again_delay: 0
  show_unmanaged: true
  show_filtered: false
  show_missing: true
  save_missing: true
```

| Name | Attribute | Allowed Values | Default | Global Level | Library Level | Collection Level |
| :-- | :-- | :-- | :--: | :--: | :--: | :--: |
| Cache | `cache` | Should the script store a cache<br><strong>boolean:</strong> true or false | true | :heavy_check_mark: | :x: | :x: |
| Cache Expiration | `cache_expiration` | Number of days before each cache mapping expires and has to be reloaded | 60 | :heavy_check_mark: | :x: | :x: |
| [Image Asset Directory](#image-asset-directory) | `asset_directory` | System Locations For Image Assets | [Directory containing YAML config]/assets | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Sync Mode | `sync_mode` | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection | append | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| [Run Again Delay](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Details#settings-attributes) | `run_again_delay` | Number of minutes to run `run_again` collections after daily run is finished<br>**number:** 0 or greater | 0 | :heavy_check_mark: | :x: | :x: |
| Show Unmanaged Collections | `show_unmanaged` | Show collections not managed by Plex Meta Manager at the end of each run<br>**boolean:** true or false | true | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Show Filtered Collections | `show_filtered` | Library Level toggle to show filtered collections<br>**boolean:** true or false | false | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Show Missing | `show_missing` | Library Level toggle to show movies/shows missing from collections<br>**boolean:** true or false | true | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| Save Missing | `save_missing` | Library Level toggle to save movies/shows missing from collections to a file next to you Metadata file<br>**boolean:** true or false | true | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |

* The cache database file is created in the same location as your config file.

## Image Asset Directory
The Image Asset Directory can be used to update the posters and backgrounds of collections and the movies and shows inside them. If you want to add multiple Image Asset Directories you have to use a list. Comma-separated values will not work.

By default, the program will look in the same folder as you config.yml for a folder called assets.

To specify a poster or background of a collection create a folder inside an assets folder called the same as the mapping name used with the collection unless `system_name` is specified, which you would then name the folder the same as specified in `system_name`.

After the folder has been created you can add a `poster.ext` or `background.ext` file to update the poster or background of a collection (replacing `.ext` with the image extension).

To edit the posters and backgrounds of the movies or shows inside a collection, you have to create a folder inside the collection asset folder called the same name as the folder the actual video file is stored in. 

After the folder has been created you can add a `poster.ext` or `background.ext` file to update the poster or background of a movie or show  (replacing `.ext` with the image extension).

Here's an example config folder structure with an assets directory.

```
config
├── config.yml
├── Movies.yml
├── assets
│   ├── The Lord of the Rings
│       ├── poster.png
│       ├── background.png
│       ├── The Lord of the Rings The Fellowship of the Ring (2001)
│           ├── poster.png
│           ├── background.png
│       ├── The Lord of the Rings The Two Towers (2002)
│           ├── poster.png
│           ├── background.png
│       ├── The Lord of the Rings The Return of the King (2003)
│           ├── poster.png
│           ├── background.png
```