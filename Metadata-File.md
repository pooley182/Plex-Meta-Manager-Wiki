The main goal of the script is to allow a complete recreation of your library just from the Metadata File and to dynamically build and maintain collections.

To do that you have to specify the metadata and collections in the Metadata File, which is required per Library and is defined in the Configuration File.

If the Metadata File location is not specified it will look in the same directory as the Configuration File for a YAML file whose name matches the mapped name of the library in the Configuration File. 

For Example if this is your config.yml:

```yaml
libraries:
  Movies:
    library_type: movie
  TV Shows:
    library_type: show
  Anime:
    library_type: show
```

Then along side the config.yml it would expect to find the Metadata Files:

```bash
config.yml
Movies.yml
TV Shows.yml
Anime.yml
```

There are only two mappings allowed in the Metadata File's root:
| Name | Attribute | Description |
| :-- | :-- | :-- |
| [Metadata](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Metadata-Attributes) | `metadata` | mapping where metadata changes go |
| [Collections](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Attributes) | `collections` | mapping where automatic collections and collection metdata go |

* Either `metadata` or `collections` is required in order to run.