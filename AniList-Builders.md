You can build different collections using the features of [AniList.co](https://anilist.co/) (AniList).

No configuration is required for these builders.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :--- | :--- | :--- | :---: | :---: |
| [AniList Top Rated Anime](#anilist-top-rated-anime) | `anilist_popular` | Gets every anime in AniList's [Top Rated Anime](https://anilist.co/search/anime?sort=SCORE_DESC) list | :heavy_check_mark: | :heavy_check_mark: |
| [AniList Popular Anime](#anilist-popular-anime) | `anilist_popular` | Gets every anime in AniList's [Popular Anime](https://anilist.co/search/anime?sort=POPULARITY_DESC) list | :heavy_check_mark: | :heavy_check_mark: |
| [AniList Seasonal Anime](#anilist-seasonal-anime) | `anilist_season` | Gets anime in AniList's Seasonal Anime list the options are detailed below | :heavy_check_mark: | :heavy_check_mark: |
| [AniList Relations](#anilist-relations) | `anilist_relations` | Gets the anime specified by the AniList ID and every relation in its relation tree except Character and Other relations | :heavy_check_mark: | :heavy_check_mark: |
| [AniList Studio](#anilist-studio) | `anilist_studio` | Gets all anime specified by the AniList Studio ID | :heavy_check_mark: | :heavy_check_mark: |
| [AniList Genre](#anilist-genre) | `anilist_genre` | Gets all anime specified by the AniList Genre | :heavy_check_mark: | :heavy_check_mark: |
| [AniList Tag](#anilist-tag) | `anilist_tag` | Gets all anime specified by the AniList Tag | :heavy_check_mark: | :heavy_check_mark: |
| [AniList ID](#anilist-id) | `anilist_id` | Gets the anime specified by the AniList ID | :heavy_check_mark: | :heavy_check_mark: |

* To find possible genres and tags go to the [AniList Anime](https://anilist.co/search/anime) page and click the Genres dropdown to see all the genres and tags. 

## AniList Top Rated Anime
Gets every anime in AniList's [Top Rated Anime](https://anilist.co/search/anime?sort=SCORE_DESC) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Watched lists are continuously updated.

```yaml
collections:
  Top Rated Anime:
    anilist_popular: 30
    sync_mode: sync
```

## AniList Popular Anime
Gets every anime in AniList's [Popular Anime](https://anilist.co/search/anime?sort=POPULARITY_DESC) list.

The expected input is a single integer value of how many movies/shows to query. 

The `sync_mode: sync` option is also recommended since the Trakt Watched lists are continuously updated.

```yaml
collections:
  Popular Anime:
    anilist_popular: 10
    sync_mode: sync
```

## AniList Seasonal Anime
Gets anime in AniList's Seasonal Anime list the options are detailed below.

| Attribute | Description | Required | Default |
| :--- | :--- | :---: | :---: |
| `season` | `winter` (For winter season December, January, February)<br>`spring` (For spring season March, April, May)<br>`summer` (For summer season June, July, August)<br>`fall` (For fall season September, October, November) | :x: | Current Season |
| `year` | 4 digit integer year between 1917-Current | :x: | Current Year |
| `sort_by` | `score` (Sort by Score)<br>`popular` (Sort by Most Popular) | :x: | `score` |
| `limit` | Number of Anime to query from AniList (use 0 for all; max: 500) | :x: | 0 |

```yaml
collections:
  Current Anime Season:
    anilist_season:
      sort_by: popular
    sync_mode: sync
```
```yaml
collections:
  Fall 2020 Anime:
    anilist_season:
      season: fall
      year: 2020
    sync_mode: sync
```

## AniList Relations
Gets the anime specified by the AniList ID and every relation in its relation tree except Character and Other relations.

The expected input is an AniList ID. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  One Piece:
    anilist_relations: 21
```

## AniList Studio
Gets all anime specified by the AniList Studio ID.

The expected input is an AniList ID. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Studio Ghibli:
    anilist_studio: 21
```

## AniList Genre
Gets anime with the specified AniList Genre the options are detailed below. 

| Attribute | Description | Required | Default |
| :--- | :--- | :---: | :---: |
| `genre` | AniList Genre to search by | :heavy_check_mark: | N/A |
| `sort_by` | `score` (Sort by Score)<br>`popular` (Sort by Most Popular) | :x: | `score` |
| `limit` | Number of Anime to query from AniList (use 0 for all; max: 500) | :x: | 0 |

```yaml
collections:
  Sports Anime:
    anilist_genre:
      genre: Sports
      sort_by: popular
    sync_mode: sync
```

* To find possible genres and tags go to the [AniList Anime](https://anilist.co/search/anime) page and click the Genres dropdown to see all the genres and tags. 

## AniList Tag
Gets anime with the specified AniList Tag the options are detailed below. 

| Attribute | Description | Required | Default |
| :--- | :--- | :---: | :---: |
| `tag` | AniList Tag to search by | :heavy_check_mark: | N/A |
| `sort_by` | `score` (Sort by Score)<br>`popular` (Sort by Most Popular) | :x: | `score` |
| `limit` | Number of Anime to query from AniList (use 0 for all; max: 500) | :x: | 0 |

```yaml
collections:
  Pirates Anime:
    anilist_tag:
      tag: Pirates
      sort_by: popular
    sync_mode: sync
```

* To find possible genres and tags go to the [AniList Anime](https://anilist.co/search/anime) page and click the Genres dropdown to see all the genres and tags. 

## AniList ID
Gets the anime specified by the AniList ID.

The expected input is an AniList ID. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Cowboy Bebop:
    anilist_id: 23, 219
```