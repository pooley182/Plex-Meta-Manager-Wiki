You can find items using the features of [TheMovieDb.org](https://www.themoviedb.org/) (TMDb).

## Standard TMDb Builders

| Name | Attribute | Description | Works with Movies | Works with Shows | Works with Playlists and Custom Sort |
| :--- | :--- | :--- | :---: | :---: | :---: |
| [TMDb Collection](#tmdb-collection) | `tmdb_collection` | Finds every item in the TMDb collection | :heavy_check_mark: | :x: | :x: |
| [TMDb List](#tmdb-list) | `tmdb_list` | Finds every item in the TMDb List | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| [TMDb Actor](#tmdb-actor) | `tmdb_actor` | Finds every item in the TMDb Person's Actor Credits | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Crew](#tmdb-crew) | `tmdb_crew` | Finds every item in the TMDb Person's Crew Credits | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Director](#tmdb-director) | `tmdb_director` | Finds every item in the TMDb Person's Actor Credits | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Producer](#tmdb-producer) | `tmdb_producer` | Finds every item in the TMDb Person's Producer Credits | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Writer](#tmdb-writer) | `tmdb_writer` | Finds every item in the TMDb Person's Writer Credits | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Movie](#tmdb-movie) | `tmdb_movie` | Finds the movie specified | :heavy_check_mark: | :x: | :x: |
| [TMDb Show](#tmdb-show) | `tmdb_show` | Finds the show specified | :x: | :heavy_check_mark: | :x: |
| [TMDb Company](#tmdb-company) | `tmdb_company` | Finds every item from the TMDb company's movie/show list | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Network](#tmdb-network) | `tmdb_network` | Finds every item from the TMDb network's show list | :x: | :heavy_check_mark: | :x: |
| [TMDb Keyword](#tmdb-keyword) | `tmdb_keyword` | Finds every item from the TMDb keyword's movie/show list | :heavy_check_mark: | :heavy_check_mark: | :x: |

## Standard TMDb Details Builders

| Name | Attribute | Description | Works with Movies | Works with Shows | Works with Playlists and Custom Sort |
| :--- | :--- | :--- | :---: | :---: | :---: |
| [TMDb Collection Details](#tmdb-collection) | `tmdb_collection_details` | Finds every item in the TMDb collection and updates the collection with the summary, poster, and background from the TMDb collection | :heavy_check_mark: | :x: | :x: |
| [TMDb List Details](#tmdb-list) | `tmdb_list_details` | Finds every item in the TMDb List and updates the collection with the description of the TMDb list | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Actor Details](#tmdb-actor) | `tmdb_actor_details` | Finds every item in the TMDb Person's Actor Credits with the biography and profile from the TMDb person | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Crew Details](#tmdb-crew) | `tmdb_crew_details` | Finds every item in the TMDb Person's Crew Credits with the biography and profile from the TMDb person | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Director Details](#tmdb-director) | `tmdb_director_details` | Finds every item in the TMDb Person's Actor Credits with the biography and profile from the TMDb person | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Producer Details](#tmdb-producer) | `tmdb_producer_details` | Finds every item in the TMDb Person's Producer Credits with the biography and profile from the TMDb person | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Writer Details](#tmdb-writer) | `tmdb_writer_details` | Finds every item in the TMDb Person's Writer Credits with the biography and profile from the TMDb person | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [TMDb Movie Details](#tmdb-movie) | `tmdb_movie_details` | Finds the movie specified and updates the collection with the summary, poster, and background from the TMDb movie | :heavy_check_mark: | :x: | :x: |
| [TMDb Show Details](#tmdb-show) | `tmdb_show_details` | Finds the show specified and updates the collection with the summary, poster, and background from the TMDb show | :x: | :heavy_check_mark: | :x: |

## Other TMDb Builders

| Name | Attribute | Description | Works with Movies | Works with Shows | Works with Playlists and Custom Sort |
| :--- | :--- | :--- | :---: | :---: | :---: |
| [TMDb Popular](#tmdb-popular) | `tmdb_popular` | Finds the movies/shows in TMDb's [Popular Movies](https://www.themoviedb.org/movie)/[Popular Shows](https://www.themoviedb.org/tv) list | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| [TMDb Now Playing](#tmdb-now-playing) | `tmdb_now_playing` | Finds the movies in TMDb's [Now Playing](https://www.themoviedb.org/movie/now-playing) list | :heavy_check_mark: | :x: | :heavy_check_mark: |
| [TMDb Top Rated](#tmdb-top-rated) | `tmdb_top_rated` | Finds the movies/shows in TMDb's [Top Rated Movies](https://www.themoviedb.org/movie/top-rated)/[Top Rated Shows](https://www.themoviedb.org/tv/top-rated) list | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |
| [TMDb Trending Daily](#tmdb-trending-daily) | `tmdb_trending_daily` | Finds the movies/shows in TMDb's Trending Daily list | :heavy_check_mark: | :heavy_check_mark: |  :heavy_check_mark: |
| [TMDb Trending Weekly](#tmdb-trending-weekly) | `tmdb_trending_weekly` | Finds the movies/shows in TMDb's Trending Weekly list | :heavy_check_mark: | :heavy_check_mark: |  :heavy_check_mark: |
| [TMDb Discover](#tmdb-discover) | `tmdb_discover` | Uses [TMDb's Discover Search](https://www.themoviedb.org/documentation/api/discover) to find every movie/show based on the [movie search parameters](https://developers.themoviedb.org/3/discover/movie-discover) or [show search parameters](https://developers.themoviedb.org/3/discover/tv-discover) provided | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |

## Expected Input

The builders below are expected to have the full URL to the item or the TMDb ID of the item. Multiple values are supported as either a list or a comma-separated string.
* [TMDb Collection](#tmdb-collection) and [TMDb Collection Details](#tmdb-collection)
* [TMDb List](#tmdb-list) and [TMDb List Details](#tmdb-list)
* [TMDb Actor](#tmdb-actor) and [TMDb Actor Details](#tmdb-actor)
* [TMDb Crew](#tmdb-crew) and [TMDb Crew Details](#tmdb-crew)
* [TMDb Director](#tmdb-director) and [TMDb Director Details](#tmdb-director)
* [TMDb Producer](#tmdb-producer) and [TMDb Producer Details](#tmdb-producer)
* [TMDb Writer](#tmdb-writer) and [TMDb Writer Details](#tmdb-writer)
* [TMDb Movie](#tmdb-movie) and [TMDb Movie Details](#tmdb-movie)
* [TMDb Show](#tmdb-show) and [TMDb Show Details](#tmdb-show)
* [TMDb Company](#tmdb-company)
* [TMDb Network](#tmdb-network)

The builders below are expected to have a single integer value of how many movies/shows to query.
* [TMDb Popular](#tmdb-popular)
* [TMDb Now Playing](#tmdb-now-playing)
* [TMDb Top Rated](#tmdb-top-rated)
* [TMDb Trending Daily](#tmdb-trending-daily)
* [TMDb Trending Weekly](#tmdb-trending-weekly)

[TMDb Discover](#tmdb-discover)'s attributes are detailed [below](#tmdb-discover).

## TMDb Collection
Finds every item in the TMDb collection.

```yaml
collections:
  The Lord of the Rings:
    tmdb_collection: https://www.themoviedb.org/collection/119
  The Hobbit:
    tmdb_collection: 121938
  Middle Earth:
    tmdb_collection:
      - 119
      - https://www.themoviedb.org/collection/121938
```

* You can update the collection details with the TMDb collection's summary, poster, and background by using `tmdb_collection_details`.
* You can specify multiple collections in `tmdb_collection_details` but it will only use the first one to update the collection details.
* Posters and background in the library's asset directory will be used over the collection details unless `tmdb_poster`/`tmdb_background` is also specified.

```yaml
collections:
  The Lord of the Rings:
    tmdb_collection_details: https://www.themoviedb.org/collection/119
  The Hobbit:
    tmdb_collection_details: 121938
  Middle Earth:
    tmdb_collection_details:
      - 119
      - https://www.themoviedb.org/collection/121938
```

## TMDb List
Finds every item in the TMDb List.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order. 

```yaml
collections:
  Top 50 Grossing Films of All Time (Worldwide):
    tmdb_list: https://www.themoviedb.org/list/10
    collection_order: custom
    sync_mode: sync
```
```yaml
collections:
  Top 50 Grossing Films of All Time (Worldwide):
    tmdb_list: 10
    collection_order: custom
    sync_mode: sync
```

* You can update the collection details with the TMDb list's description by using `tmdb_list_details`.
* You can specify multiple lists in `tmdb_list_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Top 50 Grossing Films of All Time (Worldwide):
    tmdb_list_details: 10
```

## TMDb Actor
Finds every item in the TMDb Person's Actor Credits.

```yaml
collections:
  Robin Williams:
    tmdb_actor: https://www.themoviedb.org/person/2157-robin-williams
```
```yaml
collections:
  Robin Williams:
    tmdb_actor: 2157
```

* You can update the collection details with the TMDb Person's biography and profile by using `tmdb_actor_details`.
* You can specify multiple people in `tmdb_actor_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Robin Williams:
    tmdb_actor_details: 2157
```

## TMDb Crew
Finds every item in the TMDb Person's Crew Credits.

```yaml
collections:
  Quentin Tarantino:
    tmdb_crew: https://www.themoviedb.org/person/138-quentin-tarantino
```
```yaml
collections:
  Quentin Tarantino:
    tmdb_crew: 138
```

* You can update the collection details with the TMDb Person's biography and profile by using `tmdb_crew_details`.
* You can specify multiple people in `tmdb_crew_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Quentin Tarantino:
    tmdb_crew_details: 138
```

## TMDb Director
Finds every item in the TMDb Person's Director Credits.

```yaml
collections:
  Steven Spielberg:
    tmdb_director: https://www.themoviedb.org/person/488-steven-spielberg
```
```yaml
collections:
  Steven Spielberg:
    tmdb_director: 488
```

* You can update the collection details with the TMDb Person's biography and profile by using `tmdb_director_details`.
* You can specify multiple people in `tmdb_director_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Steven Spielberg:
    tmdb_director_details: 488
```

## TMDb Producer
Finds every item in the TMDb Person's Producer Credits.

```yaml
collections:
  Adam Sandler:
    tmdb_producer: https://www.themoviedb.org/person/19292-adam-sandler
```
```yaml
collections:
  Adam Sandler:
    tmdb_producer: 19292
```

* You can update the collection details with the TMDb Person's biography and profile by using `tmdb_producer_details`.
* You can specify multiple people in `tmdb_producer_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Adam Sandler:
    tmdb_producer_details: 19292
```

## TMDb Writer
Finds every item in the TMDb Person's Writer Credits.

```yaml
collections:
  Woody Allen:
    tmdb_writer: https://www.themoviedb.org/person/1243-woody-allen
```
```yaml
collections:
  Woody Allen:
    tmdb_writer: 1243
```

* You can update the collection details with the TMDb Person's biography and profile by using `tmdb_writer_details`.
* You can specify multiple people in `tmdb_writer_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Woody Allen:
    tmdb_writer_details: 1243
```

## TMDb Movie
Finds the movie specified.

```yaml
collections:
  Anaconda:
    tmdb_collection: https://www.themoviedb.org/collection/105995
    tmdb_movie: https://www.themoviedb.org/movie/336560
```
```yaml
collections:
  Anaconda:
    tmdb_collection: 105995
    tmdb_movie: 336560
```

* You can update the collection details with the TMDb movie's summary, poster, and background by using `tmdb_movie_details`.
* You can specify multiple movies in `tmdb_movie_details` but it will only use the first one to update the collection details.
* Posters and background in the library's asset directory will be used over the collection details unless `tmdb_poster`/`tmdb_background` is also specified.

```yaml
collections:
  Anaconda:
    tmdb_collection: 105995
    tmdb_movie_details: 336560
```

## TMDb Show
Finds the show specified.

```yaml
collections:
  Star Wars (Animated Shows):
    tmdb_show:
      - https://www.themoviedb.org/tv/4194-star-wars-the-clone-wars
      - https://www.themoviedb.org/tv/60554-star-wars-rebels
```
```yaml
collections:
  Star Wars (Animated Shows):
    tmdb_show:
      - 4194
      - 60554
```

* You can update the collection details with the TMDb show's summary, poster, and background by using `tmdb_show_details`.
* You can specify multiple shows in `tmdb_show_details` but it will only use the first one to update the collection details.
* Posters and background in the library's asset directory will be used over the collection details unless `tmdb_poster`/`tmdb_background` is also specified.

```yaml
collections:
  Star Wars (Animated Shows):
    tmdb_show_details:
      - 4194
      - 60554
```

## TMDb Company
Finds every movie from the TMDb company's movie list.

```yaml
collections:
  Studio Ghibli:
    tmdb_company: 10342
```

```yaml
collections:
  Studio Ghibli:
    tmdb_company: https://www.themoviedb.org/company/10342
```

## TMDb Network
Finds every item from the TMDb network's movie/show list.

```yaml
collections:
  CBS:
    tmdb_network: 16
```

```yaml
collections:
  CBS:
    tmdb_network: https://www.themoviedb.org/network/16
```

## TMDb Keyword
Finds every item from the TMDb keyword's movie/show list.

```yaml
collections:
  Marvel Cinematic Universe:
    tmdb_keyword: 180547
```

```yaml
collections:
  Marvel Cinematic Universe:
    tmdb_keyword: https://www.themoviedb.org/keyword/180547
```

## TMDb Popular
Finds the movies/shows in TMDb's [Popular Movies](https://www.themoviedb.org/movie)/[Popular Shows](https://www.themoviedb.org/tv) list.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

```yaml
collections:
  TMDb Popular:
    tmdb_popular: 30
    collection_order: custom
    sync_mode: sync
```

## TMDb Now Playing
Finds the movies in TMDb's [Now Playing](https://www.themoviedb.org/movie/now-playing) list.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

```yaml
collections:
  TMDb Now Playing:
    tmdb_now_playing: 30
    collection_order: custom
    sync_mode: sync
```

## TMDb Top Rated
Finds the movies/shows in TMDb's [Top Rated Movies](https://www.themoviedb.org/movie/top-rated)/[Top Rated Shows](https://www.themoviedb.org/tv/top-rated) list.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

```yaml
collections:
  TMDb Top Rated:
    tmdb_top_rated: 30
    collection_order: custom
    sync_mode: sync
```

## TMDb Trending Daily
Finds the movies/shows in TMDb's Trending Daily list.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

```yaml
collections:
  TMDb Daily Trending:
    tmdb_trending_daily: 30
    collection_order: custom
    sync_mode: sync
```

## TMDb Trending Weekly
Finds the movies/shows in TMDb's Trending Weekly list.

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

```yaml
collections:
  TMDb Weekly Trending:
    tmdb_trending_weekly: 30
    collection_order: custom
    sync_mode: sync
```

## TMDb Discover
Uses [TMDb's Discover Search](https://www.themoviedb.org/documentation/api/discover) to find every movie/show based on the [movie search parameters](https://developers.themoviedb.org/3/discover/movie-discover) or [show search parameters](https://developers.themoviedb.org/3/discover/tv-discover) provided

The `sync_mode: sync` and `collection_order: custom` Details are recommended since the lists are continuously updated and in a specific order.

| Type | Description |
| :--- | :--- |
| String | Any number of alphanumeric characters |
| Integer | Any whole number greater than zero i.e. 2, 10, 50 |
| Number | Any number greater than zero i.e. 2.5, 7.4, 9 |
| Boolean | Must be `true` or `false` |
| Date: `MM/DD/YYYY` | Date that fits the specified format |
| Year: `YYYY` | Year must be a 4 digit integer i.e. 1990 |

### Discover Movies Parameters
| Movie Parameters | Description | Type |
| :--- | :--- | :---: |
| `limit` | Specify how many movies you want returned by the query. (default: 100) | Integer |
| `language` | Specify a language to query translatable fields with. (default: en-US) | `([a-z]{2})-([A-Z]{2})` |
| `region` | Specify a [ISO 3166-1 code](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes) to filter release dates. Must be uppercase. | `^[A-Z]{2}$` |
| `sort_by` | Choose from one of the many available sort options. (default: `popularity.desc`) | See [sort options](#sort-options) below |
| `certification_country` | Used in conjunction with the certification parameter, use this to specify a country with a valid certification. | String |
| `certification` | Filter results with a valid certification from the `certification_country` parameter. | String |
| `certification.lte` | Filter and only include movies that have a certification that is less than or equal to the specified value. | String |
| `certification.gte` | Filter and only include movies that have a certification that is greater than or equal to the specified value. | String |
| `include_adult` | A filter and include or exclude adult movies. | Boolean |
| `include_video` | A filter and include or exclude videos. | Boolean |
| `primary_release_year` | A filter to limit the results to a specific primary release year. | Year: YYYY |
| `primary_release_date.gte` | Filter and only include movies that have a primary release date that is greater or equal to the specified value. | Date: `MM/DD/YYYY` |
| `primary_release_date.lte` | Filter and only include movies that have a primary release date that is less than or equal to the specified value. | Date: `MM/DD/YYYY` |
| `release_date.gte` | Filter and only include movies that have a release date (looking at all release dates) that is greater or equal to the specified value. | Date: `MM/DD/YYYY` |
| `release_date.lte` | Filter and only include movies that have a release date (looking at all release dates) that is less than or equal to the specified value. | Date: `MM/DD/YYYY` |
| `with_release_type` | Specify a comma (AND) or pipe (OR) separated value to filter release types by. (1: Premiere, 2: Theatrical (limited), 3: Theatrical, 4: Digital, 5: Physical, 6: TV) | String |
| `year` | A filter to limit the results to a specific year (looking at all release dates). | Year: YYYY |
| `vote_count.gte` | Filter and only include movies that have a vote count that is greater or equal to the specified value. | Integer |
| `vote_count.lte` | Filter and only include movies that have a vote count that is less than or equal to the specified value. | Integer |
| `vote_average.gte` | Filter and only include movies that have a rating that is greater or equal to the specified value. | Number |
| `vote_average.lte` | Filter and only include movies that have a rating that is less than or equal to the specified value. | Number |
| `with_cast` | A comma-separated list of person ID's. Only include movies that have one of the ID's added as an actor. | String |
| `with_crew` | A comma-separated list of person ID's. Only include movies that have one of the ID's added as a crew member. | String |
| `with_people` | A comma-separated list of person ID's. Only include movies that have one of the ID's added as either an actor or a crew member. | String |
| `with_companies` | A comma-separated list of production company ID's. Only include movies that have one of the ID's added as a production company. | String |
| `without_companies` | Filter the results to exclude the specific production companies you specify here. AND / OR filters are supported. | String |
| `with_genres` | Comma-separated value of genre ids that you want to include in the results. | String |
| `without_genres` | Comma-separated value of genre ids that you want to exclude from the results. | String |
| `with_keywords` | A comma-separated list of keyword ID's. Only includes movies that have one of the ID's added as a keyword. | String |
| `without_keywords` | Exclude items with certain keywords. You can comma and pipe separate these values to create an 'AND' or 'OR' logic. | String |
| `with_runtime.gte` | Filter and only include movies that have a runtime that is greater or equal to a value. | Integer |
| `with_runtime.lte` | Filter and only include movies that have a runtime that is less than or equal to a value. | Integer |
| `with_original_language` | Specify an ISO 639-1 string to filter results by their original language value. | String |
| `with_watch_providers` | A comma or pipe separated list of watch provider ID's. Combine this filter with `watch_region` in order to filter your results by a specific watch provider in a specific region. | String |
| `watch_region` | An [ISO 3166-1 code](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes). Combine this filter with `with_watch_providers` in order to filter your results by a specific watch provider in a specific region. | String |
| `with_watch_monetization_types` | In combination with `watch_region`, you can filter by monetization type. | `flatrate`, `free`, `ads`, `rent`, `buy` |

### Discover Shows Parameters
| Show Parameters | Description | Type |
| :--- | :--- | :---: |
| `limit` | Specify how many movies you want to be returned by the query. (default: 100) | Integer |
| `language` | Specify a language to query translatable fields with. (default: en-US) | `([a-z]{2})-([A-Z]{2})` |
| `sort_by` | Choose from one of the many available sort options. (default: `popularity.desc`) | See [sort options](#sort-options) below |
| `air_date.gte` | Filter and only include TV shows that have an air date (by looking at all episodes) that is greater or equal to the specified value. | Date: `MM/DD/YYYY` |
| `air_date.lte` | Filter and only include TV shows that have an air date (by looking at all episodes) that is less than or equal to the specified value. | Date: `MM/DD/YYYY` |
| `first_air_date.gte` | Filter and only include TV shows that have a original air date that is greater or equal to the specified value. Can be used in conjunction with the `include_null_first_air_dates` filter if you want to include items with no air date. | Date: `MM/DD/YYYY` |
| `first_air_date.lte` | Filter and only include TV shows that have a original air date that is less than or equal to the specified value. Can be used in conjunction with the `include_null_first_air_dates` filter if you want to include items with no air date. | Date: `MM/DD/YYYY` |
| `first_air_date_year` | Filter and only include TV shows that have an original air date year that equal to the specified value. Can be used in conjunction with the `include_null_first_air_dates` filter if you want to include items with no air date. | Year: YYYY |
| `include_null_first_air_dates` | Use this filter to include TV shows that don't have an air date while using any of the `first_air_date` filters. | Boolean |
| `timezone` | Used in conjunction with the `air_date.gte/lte` filter to calculate the proper UTC offset. (default: America/New_York) | String |
| `vote_count.gte` | Filter and only include TV that have a vote count that is greater or equal to the specified value. | Integer |
| `vote_count.lte` | Filter and only include TV that have a vote count that is less than or equal to the specified value. | Integer |
| `vote_average.gte` | Filter and only include TV that have a rating that is greater or equal to the specified value. | Number |
| `vote_average.lte` | Filter and only include TV that have a rating that is less than or equal to the specified value. | Number |
| `with_networks` | Pipe-separated value of network ids that you want to include in the results. | String |
| `with_companies` | A comma-separated list of production company ID's. Only include movies that have one of the ID's added as a production company. | String |
| `without_companies` | Filter the results to exclude the specific production companies you specify here. AND / OR filters are supported. | String |
| `with_genres` | Comma-separated value of genre ids that you want to include in the results. | String |
| `without_genres` | Comma-separated value of genre ids that you want to exclude from the results. | String |
| `with_keywords` | A comma-separated list of keyword ID's. Only includes TV shows that have one of the ID's added as a keyword. | String |
| `without_keywords` | Exclude items with certain keywords. You can comma and pipe separate these values to create an 'AND' or 'OR' logic. | String |
| `with_runtime.gte` | Filter and only include TV shows with an episode runtime that is greater than or equal to a value. | Integer |
| `with_runtime.lte` | Filter and only include TV shows with an episode runtime that is less than or equal to a value. | Integer |
| `with_original_language` | Specify an ISO 639-1 string to filter results by their original language value. | String |
| `screened_theatrically` | Filter results to include items that have been screened theatrically. | Boolean |
| `with_watch_providers` | A comma or pipe separated list of watch provider ID's. Combine this filter with `watch_region` in order to filter your results by a specific watch provider in a specific region. | String |
| `watch_region` | An [ISO 3166-1 code](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes). Combine this filter with `with_watch_providers` in order to filter your results by a specific watch provider in a specific region. | String |
| `with_watch_monetization_types` | In combination with `watch_region`, you can filter by monetization type. | `flatrate`, `free`, `ads`, `rent`, `buy` |
| `with_status` | Filter TV shows by their status. | `0`: Returning Series, `1`: Planned, `2`: In Production, `3`: Ended, `4`: Cancelled, `5`: Pilot) | 
| `with_type` | Filter TV shows by their type. | `0`: Documentary, `1`: News, `2`: Miniseries, `3`: Reality, `4`: Scripted, `5`: Show, `6`: Video) |

### Sort Options
| Sort Option | Movie Sort | Show Sort |
| :--- | :---: | :---: |
| `popularity.asc` | :heavy_check_mark: | :heavy_check_mark: |
| `popularity.desc` | :heavy_check_mark: | :heavy_check_mark: |
| `original_title.asc` | :heavy_check_mark: | :x: |
| `original_title.desc` | :heavy_check_mark: | :x: |
| `revenue.asc` | :heavy_check_mark: | :x: |
| `revenue.desc` | :heavy_check_mark: | :x: |
| `release_date.asc` | :heavy_check_mark: | :x: |
| `release_date.desc` | :heavy_check_mark: | :x: |
| `primary_release_date.asc` | :heavy_check_mark: | :x: |
| `primary_release_date.desc` | :heavy_check_mark: | :x: |
| `first_air_date.asc` | :x: | :heavy_check_mark: |
| `first_air_date.desc` | :x: | :heavy_check_mark: |
| `vote_average.asc` | :heavy_check_mark: | :heavy_check_mark: |
| `vote_average.desc` | :heavy_check_mark: | :heavy_check_mark: |
| `vote_count.asc` | :heavy_check_mark: | :x: |
| `vote_count.desc` | :heavy_check_mark: | :x: |

```yaml
collections:
  Movies Released in October 2020:
    tmdb_discover:
      primary_release_date.gte: 10/01/2020
      primary_release_date.lte: 10/31/2020
```
```yaml
collections:
  Popular Movies:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      sort_by: popularity.desc
```
```yaml
collections:
  Highest Rated R Movies:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      certification_country: US
      certification: R
      sort_by: vote_average.desc
```
```yaml
collections:
  Most Popular Kids Movies:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      certification_country: US
      certification.lte: G
      sort_by: popularity.desc
```
```yaml
collections:
  Highest Rated Movies From 2010:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      primary_release_year: 2010
      sort_by: vote_average.desc
```
```yaml
collections:
  Best Dramas From 2014:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      with_genres: 18
      primary_release_year: 2014
      sort_by: vote_average.desc
```
```yaml
collections:
  Highest Rated Science Fiction Movies with Tom Cruise:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      with_genres: 878
      with_cast: 500
      sort_by: vote_average.desc
```
```yaml
collections:
  Highest Grossing Comedy Movies with Will Ferrell:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      with_genres: 35
      with_cast: 23659
      sort_by: revenue.desc
```
```yaml
collections:
  Top Rated Movies with Brad Pitt and Edward Norton:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      with_people: 287,819
      sort_by: vote_average.desc
```
```yaml
collections:
  Popular Movies with David Fincher and Rooney Mara:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      with_people: 108916,7467
      sort_by: popularity.desc
```
```yaml
collections:
  Top Rated Dramas:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      with_genres: 18
      sort_by: vote_average.desc
      vote_count.gte: 10
```
```yaml
collections:
  Highest Grossing R Movies with Liam Neeson:
    collection_order: custom
    sync_mode: sync
    tmdb_discover:
      certification_country: US
      certification: R
      sort_by: revenue.desc
      with_cast: 3896
```
