In order to edit the metadata of Movies or Shows in a library, you have to add it to the metadata mapping of that library.

The location of the metadata file is defined by the `metadata_path` attribute of the library in the config or when not specified it will look in the same directory as the YAML config file for a YAML metadata file named the same as the library.

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

The available attributes for each movie/show are as follows
| Name | Attribute | Allowed Values | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| Alternative Title | `alt_title` |  | :heavy_check_mark: | :heavy_check_mark: |
| Original Title | `original_title` |  | :heavy_check_mark: | :heavy_check_mark: |
| Sort Title | `sort_title` |  | :heavy_check_mark: | :heavy_check_mark: |
| Year | `year` |  | :heavy_check_mark: | :heavy_check_mark: |
| Originally Available | `originally_available` |  | :heavy_check_mark: | :heavy_check_mark: |
| Rating | `rating` |  | :heavy_check_mark:| :heavy_check_mark: |
| Content Rating | `content_rating` |  | :heavy_check_mark: | :heavy_check_mark: |
| Studio | `studio` | | :heavy_check_mark: | :heavy_check_mark: |
| Tagline | `tagline` |  | :heavy_check_mark:| :heavy_check_mark: |
| Summary | `summary` |  | :heavy_check_mark: | :heavy_check_mark: |
| Genre | `genre` |  | :heavy_check_mark: | :heavy_check_mark: |
| Genre Sync | `genre_sync` |  | :heavy_check_mark: | :heavy_check_mark: |
| Label | `label` |  | :heavy_check_mark: | :heavy_check_mark: |
| Label Sync | `label_sync` |  | :heavy_check_mark: | :heavy_check_mark: |
| Seasons | `seasons` |  | :x: | :heavy_check_mark: |
| Episodes | `episodes` |  | :x: | :heavy_check_mark: |

