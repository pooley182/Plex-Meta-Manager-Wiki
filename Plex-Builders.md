You can build different collections using the features of Plex.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :-- | :-- | :-- | :--: | :--: |
| [Plex All](#plex-all) | `plex_all` | Gets every movie/show in your library. Useful with [collection filters](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Collection-Filters) | :heavy_check_mark: | :heavy_check_mark: |
| [Plex Collection](#plex-collection) | `plex_collection` | Gets every movie/show in another Plex Collection | :heavy_check_mark: | :heavy_check_mark: |
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