You can build different collections using the features of Plex.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [Plex All](#plex-all) | `plex_all` | Gets every movie/show in your library. Useful with [collection filters](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Filters) | :heavy_check_mark: | :heavy_check_mark: |
| [Plex Collection](#plex-collection) | `plex_collection` | Gets every movie/show in another Plex Collection | :heavy_check_mark: | :heavy_check_mark: |
| [Plex Collectionless](#plex-collectionless) | `plex_collectionless` | Gets every movie/show that is not in a collection | :heavy_check_mark: | :heavy_check_mark: |
| [Plex Search](#plex-search) | `plex_search` | Gets every movie/show based on the search parameters provided | :heavy_check_mark: | :heavy_check_mark: |

## Plex All
Gets every movie/show in your library. Useful with [collection filters](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Filters).

The expected input is either true or false. 

```yaml
collections:
  9.0 Movies:
    all: true
    filters:
      rating.gte: 9
```

## Plex Collection
Gets every movie/show in another Plex Collection. 

The expected input is the exact name of a Collection in Plex

```yaml
collections:
  Dinosaurs:
    plex_collection: Jurassic Park
```

If you want to add multiple collections you have to use a list. Comma separated values will not work.

 ```yaml
 collections:
   Dinosaurs:
     plex_collection:
       - Jurassic Park
       - The Land Before Time
 ```

## Plex Collectionless
Gets every movie/show that is not in a collection unless the collection is in the exclusion list. This is a special collection type to help keep your library looking correct. When items in your library are in multiple collections it can mess up how they're displayed in your library. 

For Example if you have a `Marvel Cinematic Universe` Collection set to `Show this collection and its items` and an `Iron Man` Collection set to `Hide items in this collection` what happens is the show overrides the hide and you end up with both collections displaying as well as the 3 Iron Man movies and if you set the `Marvel Cinematic Universe` Collection to `Hide items in this collection` then movies without a collection like `The Incredible Hulk` will be hidden from the library view. 

To combat the problem above you set all collections to `Hide items in this collection` and create a collection and set it to `Hide collection` and put every movie that you still want to display in that collection. 

With the variability of Plex Meta Manager maintaining a collection like this becomes very difficult, so in order to automate you can use `plex_collectionless`. You just have to tell it what collections to exclude or what collection prefix to use.

This is a known issue with Plex Collection and there is a [Feature Suggestion](https://forums.plex.tv/t/collection-display-issue/305406) detailing the issue more on their forms. 



## Plex Search
Gets every movie/show based on the search parameters provided. The search will return any movie/show that matches at least one term from each search option. You can run multiple searches. 

### Search Options
| Search Option | Description | Movie<br>Libraries | Show<br>Libraries |
| :-- | :-- | :--: | :--: |
| `actor` | Gets every movie with the specified actor | :heavy_check_mark: | :x: |
| `actor_details_tmdb` | Gets every movie with the specified actor and updates the collection details with the TMDb Person's Profile and Biography | :heavy_check_mark: | :x: |
| `country` | Gets every movie with the specified country | :heavy_check_mark: | :x: |
| `decade` | Gets every movie from the specified year + the 9 that follow i.e. 1990 will get you 1990-1999 | :heavy_check_mark: | :x: |
| `director` | Gets every movie with the specified director | :heavy_check_mark: | :x: |
| `director_details_tmdb` | Gets every movie with the specified director and updates the collection details with the TMDb Person's Profile and Biography | :heavy_check_mark: | :x: |
| `genre` | Gets every movie/show with the specified genre | :heavy_check_mark: | :heavy_check_mark: |
| `studio` | Gets every movie/show with the specified studio | :heavy_check_mark: | :heavy_check_mark: |
| `year` | Gets every movie/show with the specified year (Put a `-` between two years for a range i.e. `year: 1990-1999` or end with `NOW` to go till current i.e. `year: 2000-NOW`) | :heavy_check_mark: | :heavy_check_mark: |
| `writer` | Gets every movie with the specified writer | :heavy_check_mark: | :x: |
| `writer_details_tmdb` | Gets every movie with the specified writer and updates the collection details with the TMDb Person's Profile and Biography | :heavy_check_mark: | :x: |

* TMDb configuration is required to use `actor_details_tmdb`, `director_details_tmdb`, or `writer_details_tmdb`.
* You can only use each search option once per `plex_search` but you can give the search multiple values.
* If you want to restrict the search by multiples of the same attribute (i.e. You want every movie that is a Romance and Comedy) try using [collection filters](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Filters).

```yaml
collections:
  Documentaries:
    plex_search:
      genre: Documentary
```
```yaml
collections:
  Dave Chappelle Comedy:
    plex_search:
      actor: Dave Chappelle
      genre: Comedy
```
```yaml
collections:
  Robin Williams:
    actor_details_tmdb: 2157
```
```yaml
collections:
  Steven Spielberg:
    director_details_tmdb: https://www.themoviedb.org/person/488-steven-spielberg
```
```yaml
collections:
  Quentin Tarantino:
    writer_details_tmdb: 138
```
```yaml
collections:
  Pixar:
    plex_search:
      studio: Pixar
```
```yaml
collections:
  90s Movies:
    plex_search:
      year:
        - 1990
        - 1991
        - 1992
        - 1993
        - 1994
        - 1995
        - 1996
        - 1997
        - 1998
        - 1999
```
```yaml
collections:
  90s Movies:
    plex_search:
      year: 1990-1999
```
```yaml
collections:
  2010+ Movies:
    plex_search:
      year: 2010-NOW
```
```yaml
collections:
  90s Movies:
    plex_search:
      decade: 1990
```

If you only want to search using a single attribute you can do so without `plex_search`.

```yaml
collections:
  90s Movies:
    year: 1990-1999
```