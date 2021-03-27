You can build different collections using the features of [Trakt.tv](https://trakt.tv/) (Trakt). 

[Configuring Trakt](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Trakt-Attributes) in the config is required for any of these builders.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :--- | :--- | :--- | :---: | :---: |
| [Trakt List](#trakt-list) | `trakt_list` | Gets every movie/show in the Trakt List | :heavy_check_mark: | :heavy_check_mark: |
| [Trakt List Details](#trakt-list) | `trakt_list_details` | Gets every movie/show in the Trakt List and updates the collection summary with the list description | :heavy_check_mark: | :heavy_check_mark: |
| [Trakt User Watchlist](#trakt-user-watchlist) | `trakt_watchlist` | Gets every movie/show in a Users Watchlist | :heavy_check_mark: | :heavy_check_mark: |
| [Trakt User Collection](#trakt-user-collection) | `trakt_collection` | Gets every movie/show in a Users Collection | :heavy_check_mark: | :heavy_check_mark: |
| [Trakt Trending](#trakt-trending) | `trakt_trending` | Gets the movies/shows in Trakt's Trending [Movies](https://trakt.tv/movies/trending)/[Shows](https://trakt.tv/shows/trending) list | :heavy_check_mark: | :heavy_check_mark: | 
| [Trakt Popular](#trakt-popular) | `trakt_popular` | Gets the movies/shows in Trakt's Popular [Movies](https://trakt.tv/movies/popular)/[Shows](https://trakt.tv/shows/popular) list | :heavy_check_mark: | :heavy_check_mark: | 
| [Trakt Recommended](#trakt-recommended) | `trakt_recommended` | Gets the movies/shows in Trakt's Recommended [Movies](https://trakt.tv/movies/recommended/weekly)/[Shows](https://trakt.tv/shows/recommended/weekly) list | :heavy_check_mark: | :heavy_check_mark: | 
| [Trakt Watched](#trakt-watched) | `trakt_watched` | Gets the movies/shows in Trakt's Watched [Movies](https://trakt.tv/movies/watched/weekly)/[Shows](https://trakt.tv/shows/watched/weekly) list | :heavy_check_mark: | :heavy_check_mark: | 
| [Trakt Collected](#trakt-collected) | `trakt_collected` | Gets the movies/shows in Trakt's Collected [Movies](https://trakt.tv/movies/collected/weekly)/[Shows](https://trakt.tv/shows/collected/weekly) list | :heavy_check_mark: | :heavy_check_mark: | 

## Trakt List
Gets every movie/show in the Trakt List.

The expected input is a Trakt List URL. Multiple values are supported as either a list or a comma-separated string.

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

* You can update the collection details with the Trakt List's description by using `trakt_list_details`.
* You can specify multiple collections in `trakt_list_details` but it will only use the first one to update the collection summary.

```yaml
collections:
  Reddit Top 250:
    trakt_list_details: https://trakt.tv/users/jay-greene/lists/reddit-top-250-2019-edition
```

## Trakt User Watchlist
Gets every movie/show in a Users Watchlist.

The expected input is a user's Trakt Username or `me`. Multiple values are supported as either a list or a comma-separated string.

The `sync_mode: sync` option is also recommended since the Trakt Watchlists are continuously updated.

```yaml
collections:
  Trakt Watchlist:
    trakt_watchlist:
      - me
      - traktbuddy
    sync_mode: sync
```

## Trakt User Collection
Gets every movie/show in a Users Collection.

The expected input is a user's Trakt Username or `me`. Multiple values are supported as either a list or a comma-separated string.

The `sync_mode: sync` option is also recommended since the Trakt Watchlists are continuously updated.

```yaml
collections:
  Trakt Collection:
    trakt_collection:
      - me
      - traktbuddy
    sync_mode: sync
```

## Trakt Trending
Gets the movies/shows in Trakt's Trending [Movies](https://trakt.tv/movies/trending)/[Shows](https://trakt.tv/shows/trending) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Trending lists are continuously updated.

```yaml
collections:
  Trakt Trending:
    trakt_trending: 30
    sync_mode: sync
```

## Trakt Popular
Gets the movies/shows in Trakt's Popular [Movies](https://trakt.tv/movies/popular)/[Shows](https://trakt.tv/shows/popular) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Popular lists are continuously updated.

```yaml
collections:
  Trakt Popular:
    trakt_popular: 30
    sync_mode: sync
```

## Trakt Recommended
Gets the movies/shows in Trakt's Recommended [Movies](https://trakt.tv/movies/recommended/weekly)/[Shows](https://trakt.tv/shows/recommended/weekly) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Recommended lists are continuously updated.

```yaml
collections:
  Trakt Recommended:
    trakt_recommended: 30
    sync_mode: sync
```

## Trakt Watched
Gets the movies/shows in Trakt's Watched [Movies](https://trakt.tv/movies/watched/weekly)/[Shows](https://trakt.tv/shows/watched/weekly) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Watched lists are continuously updated.

```yaml
collections:
  Trakt Watched:
    trakt_watched: 30
    sync_mode: sync
```

## Trakt Collected
Gets the movies/shows in Trakt's Collected [Movies](https://trakt.tv/movies/collected/weekly)/[Shows](https://trakt.tv/shows/collected/weekly) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Collected lists are continuously updated.

```yaml
collections:
  Trakt Collected:
    trakt_collected: 30
    sync_mode: sync
```
