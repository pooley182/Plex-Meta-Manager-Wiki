You can build different collections using the features of TheMovieDb.org (TMDb).

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [TMDb Collection](#tmdb-collection) | `tmdb_collection` | Gets every movie in the TMDb collection | :heavy_check_mark: | :x: |
| [TMDb Collection Details](#tmdb-collection) | `tmdb_collection_details` | Gets every movie in the TMDb collection and updates the collection with the summary, poster, and background from the TMDb collection | :heavy_check_mark: | :x: |
| [TMDb List](#tmdb-list) | `tmdb_list` | Gets every movie/show in the TMDb List | :heavy_check_mark: | :heavy_check_mark: |
| [TMDb List Details](#tmdb-list) | `tmdb_list_details` | Gets every movie/show in the TMDb List and updates the collection with the description of the TMDb list | :heavy_check_mark: | :heavy_check_mark: |
| [TMDb Movie](#tmdb-movie) | `tmdb_movie` | Gets the movie specified | :heavy_check_mark: | :x: |
| [TMDb Movie Details](#tmdb-movie) | `tmdb_movie_details` | Gets the movie specified and updates the collection with the summary, poster, and background from the TMDb movie | :heavy_check_mark: | :x: |
| [TMDb Show](#tmdb-show) | `tmdb_show` | Gets the show specified | :x: | :heavy_check_mark: |
| [TMDb Show Details](#tmdb-show) | `tmdb_show_details` | Gets the show specified and updates the collection with the summary, poster, and background from the TMDb show | :x: | :heavy_check_mark: |
| [TMDb Company](#tmdb-company) | `tmdb_company` | Gets every movie from the TMDb company's movie list | :heavy_check_mark: | :x: |
| [TMDb Network](#tmdb-network) | `tmdb_network` | Gets every movie/show from the TMDb network's movie/show list | :heavy_check_mark: | :heavy_check_mark: |
| [TMDb Discover](#tmdb-discover) | `tmdb_discover` | Uses [TMDb's Discover Search](https://www.themoviedb.org/documentation/api/discover) to get every movie/show based on the [movie search parameters](https://developers.themoviedb.org/3/discover/movie-discover) or [show search parameters](https://developers.themoviedb.org/3/discover/tv-discover) provided | :heavy_check_mark: | :heavy_check_mark: |
| TMDb Now Playing | `tmdb_now_playing` | Gets the movies in the [TMDb Now Playing List](https://www.themoviedb.org/movie/now-playing) | :heavy_check_mark: | :x: |
| TMDb Popular | `tmdb_popular` | Gets the movies/shows in the [TMDb Popular Movies](https://www.themoviedb.org/movie)/[TMDb Popular Shows](https://www.themoviedb.org/tv) | :heavy_check_mark: | :heavy_check_mark: |
| TMDb Top Rated | `tmdb_top_rated` | Gets the movies/shows in the [TMDb Top Rated Movies](https://www.themoviedb.org/movie/top-rated)/[TMDb Top Rated Shows](https://www.themoviedb.org/tv/top-rated) | :heavy_check_mark: | :heavy_check_mark: |
| TMDb Trending Daily | `tmdb_trending_daily` | Gets the movies/shows Trending Daily on TMDb | :heavy_check_mark: | :heavy_check_mark: | 
| TMDb Trending Weekly | `tmdb_trending_weekly` | Gets the movies/shows Trending Weekly on TMDb | :heavy_check_mark: | :heavy_check_mark: | 

* For `tmdb_collection`, `tmdb_list`, `tmdb_movie`, `tmdb_show`, `tmdb_company`, or `tmdb_network` you can use the full URL or just type in the TMDb ID.

### TMDb Collection
Gets every movie in the TMDb collection.

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

### TMDb List
Gets every movie/show in the TMDb List.

```yaml
collections:
  Top 50 Grossing Films of All Time (Worldwide):
    tmdb_list: https://www.themoviedb.org/list/10
```
```yaml
collections:
  Top 50 Grossing Films of All Time (Worldwide):
    tmdb_list: 10
```

* You can update the collection details with the TMDb list's description by using `tmdb_list_details`.
* You can specify multiple lists in `tmdb_list_details` but it will only use the first one to update the collection details.

```yaml
collections:
  Top 50 Grossing Films of All Time (Worldwide):
    tmdb_list_details: 10
```

### TMDb Movie
Gets the movie specified.

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
    tmdb_movie: 336560
```

### TMDb Show
Gets the show specified.

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

### TMDb Company
Gets every movie from the TMDb company's movie list.

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

### TMDb Network
Gets every movie/show from the TMDb network's movie/show list.

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

### TMDb Discover
Uses [TMDb's Discover Search](https://www.themoviedb.org/documentation/api/discover) to get every movie/show based on the [movie search parameters](https://developers.themoviedb.org/3/discover/movie-discover) or [show search parameters](https://developers.themoviedb.org/3/discover/tv-discover) provided


### TMDb Now Playing

### TMDb Popular

### TMDb Top Rated

### TMDb Trending