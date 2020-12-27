Adding a metadata backup was one of the main reasons for creating this script. I wanted to be able to run a script and have my entire library be recreated if I lost my plex database, so I created this.

In order to edit the metadata of Movies or Shows in a library, you have to add it to the metadata mapping of that library.

The location of the metadata file is defined by the `metadata_path` attribute of the library in the config or when not specified it will look in the same directory as the YAML config file for a YAML metadata file named the same as the library.

Each movie/show is defined by the mapping name which must be the same as the movie/show name in the library name unless an `alt_title` is specified.

A simple example of multiple libraries all using the global values is below:
```yaml
metadata:
  "Avatar: The Last Airbender":
    seasons:
      1:
        title: "Book One: Water"
      2:
        title: "Book Two: Earth"
      3:
        title: "Book Three: Fire"
  "Avatar: The Legend of Korra":
    alt_title: The Legend of Korra
    original_title: The Legend of Korra
    seasons:
      1:
        title: "Book One: Air"
      2:
        title: "Book Two: Spirits"
      3:
        title: "Book Three: Change"
      4:
        title: "Book Four: Balance"
```

The available attributes for each movie/show are as follows
| Name | Attribute | Allowed Values | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| Alternative Title | `alt_title` | Alternative title to look for | :heavy_check_mark: | :heavy_check_mark: |
| Year | `year` | Year of movie/show for better identification | :heavy_check_mark: | :heavy_check_mark: |
| Original Title | `original_title` | Text to change Original Title | :heavy_check_mark: | :heavy_check_mark: |
| Sort Title | `sort_title` | Text to change Sort Title | :heavy_check_mark: | :heavy_check_mark: |
| Originally Available | `originally_available` | Date to change Originally Available<br><strong>Format:</strong> YYYY-MM-DD  | :heavy_check_mark: | :heavy_check_mark: |
| Rating | `rating` | Number to change Rating | :heavy_check_mark:| :heavy_check_mark: |
| Content Rating | `content_rating` | Text to change Content Rating | :heavy_check_mark: | :heavy_check_mark: |
| Studio | `studio` | Text to change Studio | :heavy_check_mark: | :heavy_check_mark: |
| Tagline | `tagline` | Text to change Tagline | :heavy_check_mark:| :heavy_check_mark: |
| Summary | `summary` | Text to change Summary | :heavy_check_mark: | :heavy_check_mark: |
| Genre | `genre` | List or comma seprated text of each Genre | :heavy_check_mark: | :heavy_check_mark: |
| Genre Sync Mode | `genre_sync_mode` | `append`: Only Add Genres to the Item<br>`sync`: Add & Remove Genres from the Item<br><strong>Default Mode:</strong> `append` | :heavy_check_mark: | :heavy_check_mark: |
| Label | `label` | List or comma seprated text of each Label | :heavy_check_mark: | :heavy_check_mark: |
| Label Sync Mode | `label_sync_mode` | `append`: Only Add Labels to the Item<br>`sync`: Add & Remove Labels from the Item<br><strong>Default Mode:</strong> `append` | :heavy_check_mark: | :heavy_check_mark: |
| Seasons | `seasons` | [`seasons` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Seasons-Attributes) | :x: | :heavy_check_mark: |
| Episodes | `episodes` | [`episodes` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Episodes-Attributes) | :x: | :heavy_check_mark: |

* If you know of another Title your movie/show might exist under, but you want it titled differently you can use `alt_title` to specifiy another title to look under and then be changed to the mapping name. For Example tmdb uses the name `The Legend of Korra`, but I want it as `Avatar: The Legend of Korra` (Which must be surrounded by quotes since it uses the character `:`):
    ```yaml
    metadata:
      "Avatar: The Legend of Korra":
        alt_title: The Legend of Korra
    ```
    This would change the name of the tmdb default `The Legend of Korra` to `Avatar: The Legend of Korra` and would not mess up any subsequent runs.
* If you have two movies/shows with the same you can use the `year` attribute to specifiy which the choose.