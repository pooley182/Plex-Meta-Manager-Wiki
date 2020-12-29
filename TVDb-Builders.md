You can build different collections using the features of [TheTVDb.com](https://www.thetvdb.com/) (TVDb).

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [TVDb List](#tvdb-list) | `tvdb_list` | Gets every show in a [TVDb List](https://www.thetvdb.com/lists) or [TVDb Userlist](https://www.thetvdb.com/lists/custom) | :x: | :heavy_check_mark: |
| [TVDb Show](#tvdb-show) | `tvdb_show` | Gets the show specified | :x: | :heavy_check_mark: |

## TVDb List
Gets every show in a [TVDb List](https://www.thetvdb.com/lists) or [TVDb Userlist](https://www.thetvdb.com/lists/custom)

The expected input is a TVDb List or TVDb Userlist URL.

```yaml
collections
  Arrowverse:
    tvdb_list: https://www.thetvdb.com/lists/arrowverse
```
```yaml
collections
  Saved by the Bell:
    tvdb_list: https://www.thetvdb.com/lists/6957
```

## TVDb ID
Gets the show specified

The expected input is a TVDB Show ID.

```yaml
collections:
  Star Wars (Animated Shows):
    tvdb_show:
      - 83268
      - 283468
```