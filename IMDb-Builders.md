You can build different collections using the features of [IMDb.com](https://www.imdb.com/) (IMDb).

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [IMDb List](#imdb-list) | `imdb_list` | Gets every movie/show in an IMDb List or [IMDb Search](https://www.imdb.com/search/title/) | :heavy_check_mark: | :heavy_check_mark: |
| [IMDb ID](#imdb-id) | `imdb_id` | Gets the movie/show specified | :heavy_check_mark: | :heavy_check_mark: |

## IMDb List
Gets every movie/show in an IMDb List or [IMDb Search](https://www.imdb.com/search/title/)

The expected input is an IMDb List URL or IMDb Search URL.

```yaml
collections:
  James Bonds:
    imdb_list: https://www.imdb.com/list/ls006405458
```
```yaml
collections:
  IMDb Top 250:
    imdb_list: https://www.imdb.com/search/title/?groups=top_250
```

## IMDb ID
Gets the movie/show specified

The expected input is an IMDb ID.

```yaml
collections:
  Star Wars (Animated Shows):
    imdb_id: tt0458290, tt2930604
```