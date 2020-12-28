
The available collection details attributes for each collection are as follows
| Name | Attribute | Description | Allowed Values |
| :-- | :-- | :-- | :-- |
| Schedule | `schedule` | Used to schedule this collection | [`schedule` mapping details]() | 
| Sync Mode | `sync_mode` | Used to change how collection builders sync with this collection | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection<br>**Default Mode:** `append` | :heavy_check_mark: | :heavy_check_mark: |
| Sort Title<sup>1</sup> | `sort_title` | Used to change the collection's sort title | Text to change Sort Title |
| Content Rating | `content_rating` | Used to change the collection's content rating | Text to change Content Rating |
| Summary | `summary` | Used to change the collection's summary | Text to change Summary |
| TMDb Summary<sup>2</sup> | `tmdb_summary` | Used to change the collection's summary to a TMDb Movie/Show/Collection summary | TMDb Movie/Show/Collection ID |
| TMDb Description<sup>2</sup> | `tmdb_description` | Used to change the collection's summary to a TMDb List Discription | TMDb List ID |
| TMDb Biography<sup>2</sup> | `tmdb_biography` | Used to change the collection's summary to a TMDb Person's biography | TMDb Person ID |
| Collection Mode | `collection_mode` | Used to change the Collection Mode | `default`: Library default<br>`hide`: Hide Collection<br>`hide_items`: Hide Items in this Collection<br>`show_items`: Show this Collection and its Items |
| Collection Order | `collection_order` | Used to change the Collection Order | `release`: Order Collection by Release Dates<br>`alpha`: Order Collection Alphabetically | :heavy_check_mark: | :heavy_check_mark: |
| URL Poster<sup>3</sup> | `url_poster` | Used to change the collection's poster to a URL | URL of image publicly available on the internet |
| TMDb Poster<sup>2, 3</sup> | `tmdb_poster` | Used to change the collection's poster to a TMDb Movie/Show/Collection poster | TMDb Movie/Show/Collection ID | 
| TMDb List Poster<sup>2, 3</sup> | `tmdb_list_poster` | Used to change the collection's poster to a TMDb List poster | TMDb List ID | 
| TMDb Profile<sup>2, 3</sup> | `tmdb_profile` | Used to change the collection's poster to a TMDb Person's profile | TMDb Person ID | 
| File Poster<sup>3</sup> | `file_poster` | Used to change the collection's poster to an image in the file system | Path to image in the file system |
| URL Background<sup>4</sup> | `url_background` | Use to change the collection's background to a URL | URL of image publicly available on the internet |
| TMDb Background<sup>2, 4</sup> | `tmdb_background` | Used to change the collection's background to a TMDb Movie/Show/Collection background | TMDb Movie/Show/Collection ID | 
| File Background<sup>4</sup> | `file_background` | Used to change the collection's background to an image in the file system | Path to image in the file system |
| Name Mapping<sup>5</sup> | `name_mapping` | Used to specify the folder name in the assests directory | Folder Name In Assets Directory |

1. You can use `sort_title` to "promote" certain collections to the top of a library by creating a sort title starting with a `#`.
2. To use any TMDb collection detail you must configure TMDb in the config, where you can also change the language if needed.
3. If no poster is specified the script will look in the library's asset directory for a folder named either the collection name or the `name_mapping` if specified and look for a poster.ext file in that folder.
4. If no background is specified the script will look in the library's asset directory for a folder named either the collection name or the `name_mapping` if specified and look for a background.ext file in that folder.
5. If your collection name contains characters that are not allowed in filepaths (i.e. for windows `<`, `>`, `:`, `"`, `/`, `\`, `|`, `?`, `*` cannot be in the file path) but you want them in your collection name you can use the `name_mapping` attribute to specific this collection's name in the file system.