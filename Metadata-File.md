The main goal of the script is to allow a complete recreation of your library just from the Metadata File and to dynamically build and maintain collections.

To do that you have to specify the metadata and collections in a Metadata File that is defined by the [Libraries attribute](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Libraries-Attributes) in the Configuration File.

You must have at least one Metadata file per Library.

There are three mappings allowed in the Metadata File's root:

| Name | Attribute | Description |
| :--- | :--- | :--- |
| [Metadata](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Metadata-Attributes) | `metadata` | mapping where metadata changes go |
| [Templates](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Template-Attributes) | `templates` | mapping where templates for automatic collections go |
| [Collections](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Attributes) | `collections` | mapping where automatic collections and collection metadata go |

* Either `metadata` or `collections` is required in order to run.
* You can find example Metadata Files in the [Plex Meta Manager Configs Repository](https://github.com/meisnate12/Plex-Meta-Manager-Configs)