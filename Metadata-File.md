The main goal of the script is to allow a complete recreation of your library just from the Metadata File and to dynamically build and maintain collections.

To do that you have to specify the metadata and collections in the Metadata File, which is required per Library and is defined in the Configuration File.

The location of the Metadata File is defined by either the `metadata_path` attribute of the library in the Configuration File or when not specified it will look in the same directory as the YAML config file for a YAML metadata file named the same as the library.


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

Then alongside the config.yml it would expect to find the Metadata Files:

```bash
config.yml
Movies.yml
TV Shows.yml
Anime.yml
```

There are three mappings allowed in the Metadata File's root:

| Name | Attribute | Description |
| :--- | :--- | :--- |
| [Metadata](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Metadata-Attributes) | `metadata` | mapping where metadata changes go |
| [Templates](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Template-Attributes) | `templates` | mapping where templates for automatic collections go |
| [Collections](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Attributes) | `collections` | mapping where automatic collections and collection metadata go |

* Either `metadata` or `collections` is required in order to run.
* You can find a template metadata file in [config/Movies.yml.template](https://github.com/meisnate12/Plex-Meta-Manager/blob/master/config/Movies.yml.template)