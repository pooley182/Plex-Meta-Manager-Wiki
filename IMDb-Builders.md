You can build different collections using the features of [IMDb.com](https://www.imdb.com/) (IMDb).

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [IMDb ID](#imdb-id) | `imdb_id` | Gets the movie/show specified | :heavy_check_mark: | :heavy_check_mark: |
| [IMDb List](#imdb-list) | `imdb_list` | Gets every movie/show in an IMDb List or [IMDb Search](https://www.imdb.com/search/title/) | :heavy_check_mark: | :heavy_check_mark: |

## IMDb ID
Gets the movie/show specified

The expected input is an IMDb ID. Multiple values are supported as either a list or a comma separated string.

```yaml
collections:
  Star Wars (Animated Shows):
    imdb_id: tt0458290, tt2930604
```

## IMDb List
Gets every movie/show in an IMDb List or [IMDb Search](https://www.imdb.com/search/title/)

The expected input is an IMDb List URL or IMDb Search URL. Multiple values are supported as either a list or a comma separated string.

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
```yaml
  Christmas:
    imdb_list:
      - https://www.imdb.com/list/ls025976544/
      - https://www.imdb.com/list/ls003863000/
      - https://www.imdb.com/list/ls027454200/
      - https://www.imdb.com/list/ls027886673/
      - https://www.imdb.com/list/ls097998599/
    sync_mode: sync
    collection_order: alpha
```

You can also limit the number of movies/shows to search for by using the `limit` and `url` parameters under `imdb_list`.

```yaml
  IMDb Popular:
    imdb_list:
      url: https://www.imdb.com/search/title/?title_type=feature,tv_movie,documentary,short
      limit: 50
    sync_mode: sync
    collection_order: alpha
```

This can be used for multiple lists as seen below.

```yaml
  Top Action:
    imdb_list:
      - url: https://www.imdb.com/search/title/?title_type=feature&release_date=1990-01-01,&user_rating=5.0,10.0&num_votes=100000,&genres=action
        limit: 100
      - url: https://www.imdb.com/search/title/?title_type=feature&release_date=1990-01-01,&user_rating=5.0,10.0&num_votes=100000,&genres=action&sort=user_rating,desc
        limit: 100
```
