You can build different collections using the features of [MyAnimeList.net](https://myanimelist.net/) (MyAnimeList).

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [MyAnimeList Top All Anime](#myanimelist-top-all-anime) | `mal_all` | Gets every anime in MyAnimeList's [Top All Anime](https://myanimelist.net/topanime.php) list | :heavy_check_mark: | :heavy_check_mark: |
| [MyAnimeList Top Airing Anime](#myanimelist-top-airing-anime) | `mal_airing` | Gets every anime in MyAnimeList's [Top Airing Anime](https://myanimelist.net/topanime.php?type=airing) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Top Upcoming Anime](#myanimelist-top-upcoming-anime) | `mal_upcoming` | Gets every anime in MyAnimeList's [Top Upcoming Anime](https://myanimelist.net/topanime.php?type=upcoming) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Top Anime TV Series](#myanimelist-top-anime-tv-series) | `mal_tv` | Gets every anime in MyAnimeList's [Top Anime TV Series](https://myanimelist.net/topanime.php?type=tv) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Top Anime Movies](#myanimelist-top-anime-movies) | `mal_movie` | Gets every anime in MyAnimeList's [Top Anime Movies](https://myanimelist.net/topanime.php?type=movie) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Top Anime OVA Series](#myanimelist-top-anime-ova-series) | `mal_ova` | Gets every anime in MyAnimeList's [Top Anime OVA Series](https://myanimelist.net/topanime.php?type=ova) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Top Anime Specials](#myanimelist-top-anime-specials) | `mal_special` | Gets every anime in MyAnimeList's [Top Anime Specials](https://myanimelist.net/topanime.php?type=special) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Most Popular Anime](#myanimelist-most-popular-anime) | `mal_popular` | Gets every anime in MyAnimeList's [Most Popular Anime](https://myanimelist.net/topanime.php?type=bypopularity) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Most Favorited Anime](#myanimelist-most-favorited-anime) | `mal_favorite` | Gets every anime in MyAnimeList's [Most Favorited Anime](https://myanimelist.net/topanime.php?type=favorite) list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Suggested Anime](#myanimelist-suggested-anime) | `mal_suggested` | Gets the suggested anime in by MyAnimeList for the authorized user | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList User Anime List](#myanimelist-user-anime-list) | `mal_userlist` | Gets anime in MyAnimeList User's Anime list | :heavy_check_mark: | :heavy_check_mark: | 
| [MyAnimeList Seasonal Anime](#myanimelist-seasonal-anime) | `mal_season` | Gets anime in MyAnimeList's [Seasonal Anime](https://myanimelist.net/anime/season) list | :heavy_check_mark: | :heavy_check_mark: | 

## Expected Input
The builders below are expected to have a single integer value of how many movies/shows to query. The `sync_mode: sync` option is also recommended for these builders since the lists they're based on are continuously updated.
* [MyAnimeList Top All Anime](#myanimelist-top-all-anime)
* [MyAnimeList Top Airing Anime](#myanimelist-top-airing-anime)
* [MyAnimeList Top Upcoming Anime](#myanimelist-top-upcoming-anime)
* [MyAnimeList Top Anime TV Series](#myanimelist-top-anime-tv-series)
* [MyAnimeList Top Anime Movies](#myanimelist-top-anime-movies)
* [MyAnimeList Top Anime OVA Series](#myanimelist-top-anime-ova-series)
* [MyAnimeList Top Anime Specials](#myanimelist-top-anime-specials)
* [MyAnimeList Most Popular Anime](#myanimelist-most-popular-anime)
* [MyAnimeList Most Favorited Anime](#myanimelist-most-favorited-anime)
* [MyAnimeList Suggested Anime](#myanimelist-suggested-anime)

## MyAnimeList Top All Anime
Gets every anime in MyAnimeList's [Top Airing Anime](https://myanimelist.net/topanime.php?type=airing) list

```yaml
collections:
  Top All Anime:
    mal_all: 30
    sync_mode: sync
```

## MyAnimeList Top Airing Anime
Gets every anime in MyAnimeList's [Top Airing Anime](https://myanimelist.net/topanime.php?type=airing) list

```yaml
collections:
  Top Airing Anime:
    mal_airing: 10
    sync_mode: sync
```

## MyAnimeList Top Upcoming Anime
Gets every anime in MyAnimeList's [Top Upcoming Anime](https://myanimelist.net/topanime.php?type=upcoming) list

```yaml
collections:
  Top Upcoming Anime:
    mal_upcoming: 10
    sync_mode: sync
```

## MyAnimeList Top Anime TV Series
Gets every anime in MyAnimeList's [Top Anime TV Series](https://myanimelist.net/topanime.php?type=tv) list

```yaml
collections:
  Top Anime TV Series:
    mal_tv: 20
    sync_mode: sync
```

## MyAnimeList Top Anime Movies
## MyAnimeList Top Anime OVA Series
## MyAnimeList Top Anime Specials
## MyAnimeList Most Popular Anime
## MyAnimeList Most Favorited Anime
## MyAnimeList Suggested Anime
## MyAnimeList User Anime List
## MyAnimeList Seasonal Anime

## Trakt List
Gets every movie/show in the Trakt List.

The expected input is a Trakt List URL.

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

The expected input is a user's Trakt Username or `me`.

The `sync_mode: sync` option is also recommended since the Trakt Watchlists are continuously updated.

```yaml
collections:
  Trakt Watchlist:
    trakt_watchlist:
      - me
      - traktbuddy
    sync_mode: sync
```