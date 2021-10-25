Configuring different options for Plex Meta Manager can be done in the Settings. These include enabling a cache to store each Plex GUID and its accompanying IDs to vastly speed up the execution of the script, defining the Image Asset Directory for local assets, setting a global Sync Mode, and many other display features.

A `settings` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `settings` mapping individually per library. Some settings can be individually set per collection using [Collection Details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Details).

Below is a `settings` mapping example and the full set of attributes:
```yaml
settings:
  cache: true
  cache_expiration: 60
  asset_directory: config/assets
  asset_folders: true
  assets_for_all: false
  sync_mode: append
  run_again_delay: 0
  show_unmanaged: true
  show_filtered: false
  show_missing: true
  save_missing: true
```

| Name | Attribute | Allowed Values | Default | Global Level | Library Level | Collection Level |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: |
| Cache | `cache` | Create a cache database for faster processing. The cache file is created in the same location as your config file.<br>**boolean:** true or false | true | :heavy_check_mark: | :x: | :x: |
| Cache Expiration | `cache_expiration` | Number of days before each cache mapping expires and has to be reloaded | 60 | :heavy_check_mark: | :x: | :x: |
| [Image Asset Directory](#image-asset-directory) | `asset_directory` | System Locations For Image Assets | [Directory containing YAML config]/assets | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Image Asset Folders | `asset_folders` | Search in assets for named folders vs named files<br>i.e. `assets/Star Wars.png` vs `assets/Star Wars/poster.png` | true | :heavy_check_mark: | :heavy_check_mark: | :x: |
| Image Assets For All* | `assets_for_all` | Search in assets for images for every item in your library | false | :heavy_check_mark: | :heavy_check_mark: | :x: |
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

## Image Asset Directory
The Image Asset Directories can be used to update the posters and backgrounds of collections, movies, shows, seasons, and episodes. 

To use multiple Image Asset Directories you have to use a list. Comma-separated values will not work. By default, the program will look in the same folder as you config.yml for a folder called assets.

There are two different options when it comes to how the program looks at the files inside you Asset Directories. These can be toggled between by using `asset_folders`.

| Image Type | Image Path With Folders<br>`asset_folders: true` | Image Path Without Folder<br>`asset_folders: false` |
| :--- | :--- | :--- |
| Collection/Movie/Show poster | `assets/ASSET_NAME/poster.ext` | `assets/ASSET_NAME.ext` |
| Collection/Movie/Show background | `assets/ASSET_NAME/background.ext` | `assets/ASSET_NAME_background.ext` |
| Season poster | `assets/ASSET_NAME/Season##.ext` | `assets/ASSET_NAME_Season##.ext` |
| Episode poster | `assets/ASSET_NAME/S##E##.ext` | `assets/ASSET_NAME_S##E##.ext` |

* For **Collections** replace `ASSET_NAME` with the mapping name used with the collection unless `system_name` is specified, which you would then use what's specified in `system_name`.

* For **Movies** replace `ASSET_NAME` with the exact name of the folder the video file is stored in.

* For **Shows**, **Seasons**, and **Episodes** replace `ASSET_NAME` with the exact name of the folder for the show as a whole.

* For **Seasons** replace `##` with the zero padded season number (00 for specials)

* For **Episodes** replacing the first `##` with the zero padded season number (00 for specials), the second `##` with the zero padded episode number

* Replace `.ext` with the image extension

By default, the program will only look inside the Image Asset Directories for Images when it runs a collection from a Metadata File. When it does this by default it will only look for the collection images, but you can have it look for images of every item in the collection if you add `item_assets: true` to the collection config.

If you're using `asset_folders` set to true you can also nest movie/show folders inside an Image Assets Collection Folder that contains that movie/show.

You can set `assets_for_all` to true to have the program, after your run, check the Image Asset Directories for Images of every item in your library. 

Here's an example config folder structure with an assets directory with `asset_folders` set to true and false.

### `asset_folders: true` without nesting

```
config
├── config.yml
├── Movies.yml
├── TV Shows.yml
├── assets
│   ├── The Lord of the Rings
│       ├── poster.png
│       ├── background.png
│   ├── The Lord of the Rings The Fellowship of the Ring (2001)
│       ├── poster.png
│       ├── background.png
│   ├── The Lord of the Rings The Two Towers (2002)
│       ├── poster.png
│       ├── background.png
│   ├── The Lord of the Rings The Return of the King (2003)
│       ├── poster.png
│       ├── background.png
│   ├── Star Wars (Animated)
│       ├── poster.png
│       ├── background.png
│   ├── Star Wars The Clone Wars
│       ├── poster.png
│       ├── background.png
│       ├── Season00.png
│       ├── Season01.png
│       ├── Season02.png
│       ├── Season03.png
│       ├── Season04.png
│       ├── Season05.png
│       ├── Season06.png
│       ├── Season07.png
│       ├── S07E01.png
│       ├── S07E02.png
│       ├── S07E03.png
│       ├── S07E04.png
│       ├── S07E05.png
│   ├── Star Wars Rebels
│       ├── poster.png
│       ├── background.png
│       ├── Season01.png
│       ├── Season02.png
│       ├── Season03.png
│       ├── Season04.png
```

### `asset_folders: true` with nesting

```
config
├── config.yml
├── Movies.yml
├── TV Shows.yml
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
│   ├── Star Wars (Animated)
│       ├── poster.png
│       ├── background.png
│       ├── Star Wars The Clone Wars
│           ├── poster.png
│           ├── background.png
│           ├── Season00.png
│           ├── Season01.png
│           ├── Season02.png
│           ├── Season03.png
│           ├── Season04.png
│           ├── Season05.png
│           ├── Season06.png
│           ├── Season07.png
│           ├── S07E01.png
│           ├── S07E02.png
│           ├── S07E03.png
│           ├── S07E04.png
│           ├── S07E05.png
│       ├── Star Wars Rebels
│           ├── poster.png
│           ├── background.png
│           ├── Season01.png
│           ├── Season02.png
│           ├── Season03.png
│           ├── Season04.png
```

### `asset_folders: false`

```
config
├── config.yml
├── Movies.yml
├── TV Shows.yml
├── assets
│   ├── The Lord of the Rings.png
│   ├── The Lord of the Rings_background.png
│   ├── The Lord of the Rings The Fellowship of the Ring (2001).png
│   ├── The Lord of the Rings The Fellowship of the Ring (2001)_background.png
│   ├── The Lord of the Rings The Two Towers (2002).png
│   ├── The Lord of the Rings The Two Towers (2002)_background.png
│   ├── The Lord of the Rings The Return of the King (2003).png
│   ├── The Lord of the Rings The Return of the King (2003)_background.png
│   ├── Star Wars (Animated).png
│   ├── Star Wars (Animated)_background.png
│   ├── Star Wars The Clone Wars.png
│   ├── Star Wars The Clone Wars_background.png
│   ├── Star Wars The Clone Wars_Season00.png
│   ├── Star Wars The Clone Wars_Season01.png
│   ├── Star Wars The Clone Wars_Season02.png
│   ├── Star Wars The Clone Wars_Season03.png
│   ├── Star Wars The Clone Wars_Season04.png
│   ├── Star Wars The Clone Wars_Season05.png
│   ├── Star Wars The Clone Wars_Season06.png
│   ├── Star Wars The Clone Wars_Season07.png
│   ├── Star Wars The Clone Wars_S07E01.png
│   ├── Star Wars The Clone Wars_S07E02.png
│   ├── Star Wars The Clone Wars_S07E03.png
│   ├── Star Wars The Clone Wars_S07E04.png
│   ├── Star Wars The Clone Wars_S07E05.png
│   ├── Star Wars Rebels.png
│   ├── Star Wars Rebels_background.png
│   ├── Star Wars Rebels_Season01.png
│   ├── Star Wars Rebels_Season02.png
│   ├── Star Wars Rebels_Season03.png
│   ├── Star Wars Rebels_Season04.png
```