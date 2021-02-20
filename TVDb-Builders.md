You can build different collections using the features of [TheTVDb.com](https://www.thetvdb.com/) (TVDb).

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [TVDb List](#tvdb-list) | `tvdb_list` | Gets every show in a [TVDb List](https://www.thetvdb.com/lists) or [TVDb Userlist](https://www.thetvdb.com/lists/custom) | :heavy_check_mark: | :heavy_check_mark: |
| [TVDb Show](#tvdb-show) | `tvdb_show` | Gets the series specified | :x: | :heavy_check_mark: |
| [TVDb Movie](#tvdb-movie) | `tvdb_movie` | Gets the movie specified | :heavy_check_mark: | :x: |

## TVDb List
Gets every show in a [TVDb List](https://www.thetvdb.com/lists) or [TVDb Userlist](https://www.thetvdb.com/lists/custom)

The expected input is a TVDb List URL or TVDb Userlist URL. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Arrowverse:
    tvdb_list: https://www.thetvdb.com/lists/arrowverse
```
```yaml
collections:
  Saved by the Bell:
    tvdb_list: https://www.thetvdb.com/lists/6957
```

## TVDb Show
Gets the show specified

The expected input is a TVDb Series ID or TVDb Series URL. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Star Wars (Animated Shows):
    tvdb_show: 83268, 283468
```
```yaml
collections:
  Star Wars (Animated Shows):
    tvdb_show:
      - https://www.thetvdb.com/series/star-wars-the-clone-wars
      - https://www.thetvdb.com/series/star-wars-rebels
```

## TVDb Movie
Gets the movie specified

The expected input is a TVDb Movie ID or TVDb Movie URL. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  The Lord of the Rings:
    tvdb_show: 107, 157, 74
```
```yaml
collections:
  The Lord of the Rings:
    tvdb_show:
      - https://www.thetvdb.com/movies/the-lord-of-the-rings-the-fellowship-of-the-ring
      - https://www.thetvdb.com/movies/the-lord-of-the-rings-the-two-towers
      - https://www.thetvdb.com/movies/the-lord-of-the-rings-the-return-of-the-king
```