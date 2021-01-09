You can build different collections using the features of [Trakt.tv](https://trakt.tv/) (Trakt). 

[Configuring Trakt](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Trakt-Attributes) in the config is required for all of these lists.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [Trakt List](#trakt-list) | `trakt_list` | Gets every movie/show in the Trakt List | :heavy_check_mark: | :heavy_check_mark: |
| [Trakt Trending](#trakt-trending) | `trakt_trending` | Gets the movies/shows in Trakt's [Trending Movies](https://trakt.tv/movies/trending)/[Shows](https://trakt.tv/shows/trending) list | :heavy_check_mark: | :heavy_check_mark: | 
| [Trakt Watchlist](#tmdb-watchlist) | `trakt_watchlist` | Gets every movie/show in a Users Watchlist | :heavy_check_mark: | :heavy_check_mark: |

## Trakt List
Gets every movie/show in the Trakt List.

The expected input is a Trakt List URL. Multiple values are supported as either a list or a comma separated string.

```yaml
collections:
  Christmas:
    trakt_list:
      - https://trakt.tv/users/movistapp/lists/christmas-movies
      - https://trakt.tv/users/2borno2b/lists/christmas-movies-extravanganza
```
```yaml
collections:
  Reddit Top 250:
    trakt_list: https://trakt.tv/users/jay-greene/lists/reddit-top-250-2019-edition
```

## Trakt Trending
Gets the movies/shows in Trakt's [Trending Movies](https://trakt.tv/movies/trending)/[Shows](https://trakt.tv/shows/trending) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Trending lists are continuously updated.

```yaml
collections:
  Trakt Trending:
    trakt_trending: 30
    sync_mode: sync
```

## Trakt Watchlist
Gets every movie/show in a Users Watchlist.

The expected input is a user's Trakt Username or `me`. Multiple values are supported as either a list or a comma separated string.

The `sync_mode: sync` option is also recommended since the Trakt Watchlists are continuously updated.

```yaml
collections:
  Trakt Watchlist:
    trakt_watchlist:
      - me
      - traktbuddy
    sync_mode: sync
```