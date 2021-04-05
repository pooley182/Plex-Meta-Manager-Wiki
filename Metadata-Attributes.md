Adding a metadata backup was one of the main reasons for creating this script. I wanted to be able to run a script and have my entire library be recreated if I lost my plex database, so I created this.

In order to edit the metadata of Movies or Shows in a library, you have to add it to the metadata mapping of that library.

Each movie/show is defined by the mapping name which must be the same as the movie/show name in the library name unless an `alt_title` is specified.

An example of multiple metadata edits in a show library is below:
```yaml
metadata:
  "Avatar: The Last Airbender":
    sort_title: Avatar 01
    seasons:
      1:
        title: "Book One: Water"
      2:
        title: "Book Two: Earth"
      3:
        title: "Book Three: Fire"
    episodes:
      S01E01:
        rating: 9.1
      S03E21:
        summary: The Epic Series Final of Avatar The Last Airbender
  "Avatar: The Legend of Korra":
    sort_title: Avatar 02
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
| :--- | :--- | :--- | :---: | :---: |
| Title | `title` | Title if different from the mapping value useful when you have multiple movies with the same name | :heavy_check_mark: | :heavy_check_mark: |
| Alternative Title | `alt_title` | Alternative title to look for | :heavy_check_mark: | :heavy_check_mark: |
| Year | `year` | Year of movie/show for better identification | :heavy_check_mark: | :heavy_check_mark: |
| TMDb Show ID | `tmdb_id` | TMDb Show ID to use for metadata useful for miniseries that have been compiled into a movie | :heavy_check_mark: | :x: |
| Original Title | `original_title` | Text to change Original Title | :heavy_check_mark: | :heavy_check_mark: |
| Sort Title | `sort_title` | Text to change Sort Title | :heavy_check_mark: | :heavy_check_mark: |
| Originally Available | `originally_available` | Date to change Originally Available<br>**Format:** YYYY-MM-DD  | :heavy_check_mark: | :heavy_check_mark: |
| Rating | `rating` | Number to change Rating | :heavy_check_mark:| :heavy_check_mark: |
| Content Rating | `content_rating` | Text to change Content Rating | :heavy_check_mark: | :heavy_check_mark: |
| Studio | `studio` | Text to change Studio | :heavy_check_mark: | :heavy_check_mark: |
| Tagline | `tagline` | Text to change Tagline | :heavy_check_mark:| :heavy_check_mark: |
| Summary | `summary` | Text to change Summary | :heavy_check_mark: | :heavy_check_mark: |
| Genre | `genre` | List or comma-separated text of each Genre | :heavy_check_mark: | :heavy_check_mark: |
| Genre Sync Mode | `genre_sync_mode` | `append`: Only Add Genres to the Item<br>`sync`: Add & Remove Genres from the Item<br>**Default Mode:** `append` | :heavy_check_mark: | :heavy_check_mark: |
| Label | `label` | List or comma-separated text of each Label | :heavy_check_mark: | :heavy_check_mark: |
| Label Sync Mode | `label_sync_mode` | `append`: Only Add Labels to the Item<br>`sync`: Add & Remove Labels from the Item<br>**Default Mode:** `append` | :heavy_check_mark: | :heavy_check_mark: |
| Episode Sorting | `episode_sorting` | `default`: Library default<br>`oldest`: Oldest first<br>`newest`: Newest first | :x: | :heavy_check_mark: |
| Keep Episodes | `keep_episodes` | `all`: All episodes<br>`5_latest`: 5 latest episodes<br>`3_latest`: 3 latest episodes<br>`latest`: Latest episodes<br>`past_3`: Episodes added in the past 3 days<br>`past_7`: Episodes added in the past 7 days<br>`past_30`: Episodes added in the past 30 days | :x: | :heavy_check_mark: |
| Delete Episodes | `delete_episodes` | `never`: Never<br>`day`: After a day<br>`week`: After a week<br>`refresh`: On next refresh | :x: | :heavy_check_mark: |
| Season Display | `season_display` | `default`: Library default<br>`show`: Show<br>`hide`: Hide | :x: | :heavy_check_mark: |
| Episode Ordering | `episode_ordering` | `default`: Library default<br>`tmdb_aired`*: The Movie Database (Aired)<br>`tvdb_aired`: TheTVDB (Aired)<br>`tvdb_dvd`: TheTVDB (DVD)<br>`tvdb_absolute`: TheTVDB (Absolute) | :x: | :heavy_check_mark: |
| Metadata Language* | `metadata_language` | `default`, `ar-SA`, `ca-ES`, `cs-CZ`, `da-DK`, `de-DE`, `el-GR`, `en-AU`, `en-CA`, `en-GB`, `en-US`, `es-ES`, `es-MX`, `et-EE`, `fa-IR`, `fi-FI`, `fr-CA`, `fr-FR`, `he-IL`, `hi-IN`, `hu-HU`, `id-ID`, `it-IT`, `ja-JP`, `ko-KR`, `lt-LT`, `lv-LV`, `nb-NO`, `nl-NL`, `pl-PL`, `pt-BR`, `pt-PT`, `ro-RO`, `ru-RU`, `sk-SK`, `sv-SE`, `th-TH`, `tr-TR`, `uk-UA`, `vi-VN`, `zh-CN`, `zh-HK`, `zh-TW` | :x: | :heavy_check_mark: |
| Use Original Title* | `use_original_title` | `default`: Library default<br>`no`: No<br>`yes`: Yes | :x: | :heavy_check_mark: |
| Seasons | `seasons` | [`seasons` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Seasons-Attributes) | :x: | :heavy_check_mark: |
| Episodes | `episodes` | [`episodes` mapping details](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Episodes-Attributes) | :x: | :heavy_check_mark: |

* \* Must be using the New Plex TV Agent 
* Metadata Language 

* YAML files cannot have two items with the same mapping name so if you have two movies/shows with the same name you would change the mapping values to whatever you want. Then use the `title` attribute to specify the real title and use the `year` attribute to specify which of the multiple movies/shows to choose.
    ```yaml
    metadata:
      Godzilla1:
        title: Godzilla
        year: 1954
        content_rating: R
      Godzilla2:
        title: Godzilla
        year: 1998
        content_rating: PG-13
    ```

* If you know of another Title your movie/show might exist under, but you want it titled differently you can use `alt_title` to specify another title to look under and then be changed to the mapping name. For Example TMDb uses the name `The Legend of Korra`, but I want it as `Avatar: The Legend of Korra` (Which must be surrounded by quotes since it uses the character `:`):
    ```yaml
    metadata:
      "Avatar: The Legend of Korra":
        alt_title: The Legend of Korra
    ```
    This would change the name of the TMDb default `The Legend of Korra` to `Avatar: The Legend of Korra` and would not mess up any subsequent runs.