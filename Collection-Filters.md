Collection filters allow for you to filter every movie/show added to the collection from every collection builder using the `filters` attribute. 

You can have multiple collection filters but a movie/show must match at least one value from **each** collection filter to be added to a collection. The values for each must match what Plex has including special characters in order to match.

All collection filter options are listed below.

### Standard Filters

| Standard Filters | Description | Movie<br>Libraries | Show<br>Libraries |
| :-- | :-- | :--: | :--: |
| `actor` | Matches every movie/show with the specified actor | :heavy_check_mark: | :heavy_check_mark: |
| `collection` | Matches every movie/show with the specified plex collection | :heavy_check_mark: | :heavy_check_mark: |
| `content_rating` | Matches every movie/show with the specified content rating | :heavy_check_mark: | :heavy_check_mark: |
| `country` | Matches every movie with the specified country | :heavy_check_mark: | :x: |
| `director` | Matches every movie with the specified director | :heavy_check_mark: | :x: |
| `genre` | Matches every movie/show with the specified genre | :heavy_check_mark: | :heavy_check_mark: |
| `studio` | Matches every movie/show with the specified studio | :heavy_check_mark: | :heavy_check_mark: |
| `year` | Matches every movie/show with the specified year | :heavy_check_mark: | :heavy_check_mark: |
| `writer` | Matches every movie with the specified writer | :heavy_check_mark: | :x: |
| `video_resolution` | Matches every movie with the specified video resolution | :heavy_check_mark: | :x: |
| `audio_language` | Matches every movie with the specified audio language | :heavy_check_mark: | :x: |
| `subtitle_language` | Matches every movie with the specified subtitle language | :heavy_check_mark: | :x: |

* Standard filters can have multiple values either by being a list or comma separated values
* You can also use the `.not` at the end of any standard collection filter to do an inverse search matching everything that doesn't have the value specified. You can use `plex_all: true` to start your filter from your entire library.

### Advanced Filters

| Advanced Filters | Description | Movie<br>Libraries | Show<br>Libraries |
| :-- | :-- | :--: | :--: |
| `max_age` | Matches any movie/show whose Originally Available date is within the last specified number of days | :heavy_check_mark: | :heavy_check_mark: |
| `year.gte` | Matches any movie/show whose year is greater then or equal to the specified year | :heavy_check_mark: | :heavy_check_mark: |
| `year.lte` | Matches any movie/show whose year is less then or equal to the specified year | :heavy_check_mark: | :heavy_check_mark: |
| `rating.gte` | Matches any movie/show whose rating is greater then or equal to the specified rating | :heavy_check_mark: | :heavy_check_mark: |
| `rating.lte` | Matches any movie/show whose rating is less then or equal to the specified rating | :heavy_check_mark: | :heavy_check_mark: |
| `originally_available.gte` | Matches any movie/show whose originally_available date is greater then or equal to the specified originally_available date (Date must be in the MM/DD/YYYY Format) | :heavy_check_mark: | :heavy_check_mark: |
| `originally_available.lte` | Matches any movie/show whose originally_available date is less then or equal to the specified originally_available date (Date must be in the MM/DD/YYYY Format) | :heavy_check_mark: | :heavy_check_mark: |

* Advance filters can not take multiple values

### Collection Filter Examples

A few examples are listed below:

```yaml
collections:
  1080p Documentaries:
    genre: Documentary
    summary: A collection of 1080p Documentaries
    filters:
      video_resolution: 1080
```
```yaml
collections:
  Daniel Craig only James Bonds:
    imdb_list: https://www.imdb.com/list/ls006405458/
    filters:
      actor: Daniel Craig
```
```yaml
collections:
  French Romance:
    genre: Romance
    filters:
      audio_language: Français
```
```yaml
collections:
  Romantic Comedies:
    genre: Romance
    filters:
      genre: Comedy
```
```yaml
collections:
  9.0 Movies:
    plex_all: true
    filters:
      rating.gte: 9
```
```yaml
collections:
  Summer 2020 Movies:
    plex_all: true
    filters:
      originally_available.gte: 5/1/2020
      originally_available.lte: 8/31/2020
```
```yaml
collections:
  Movies Released in the Last 180 Days:
    plex_all: true
    filters:
      max_age: 180
```
```yaml
collections:
  Good Adam Sandler Romantic Comedies:
    plex_search:
      genre: Romance
      actor: Adam Sandler
    filters:
      genre: Comedy
      rating.gte: 7
```
