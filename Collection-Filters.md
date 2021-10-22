Collection filters allow for you to filter every movie/show added to the collection from every collection builder using the `filters` attribute. 

You can have multiple collection filters but a movie/show must match at least one value from **each** collection filter to be added to a collection. The values for each must match what Plex has including special characters in order to match.

All collection filter options are listed below. To display collections filtered out add `show_filtered: true` to the collection.

You can use `plex_all: true` to start your filter from your entire library.

**Filters can be very slow. Try to build or narrow your collection using [Plex Search](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Plex-Builders#plex-search) if possible.** 

## String Filters
String filters can be used with either no modifier or with `.not`, `.is`, `.isnot`, `.begins`, `.ends`, or `.regex`.

String filters can take multiple values **only as a list**.

### Modifier

| String Modifier | Description |
| :--- | :--- |
| No Modifier | Matches every item where the attribute contains the given string |
| `.not` | Matches every item where the attribute does not contain the given string |
| `.is` | Matches every item where the attribute exactly matches the given string |
| `.isnot` | Matches every item where the attribute does not exactly match the given string |
| `.begins` | Matches every item where the attribute begins with the given string |
| `.ends` | Matches every item where the attribute ends with the given string |
| `.regex` | Matches every item where the attribute matches the regex given |

### Attribute

| String Filter | Description | Movie<br>Libraries | Show<br>Libraries |
| :--- | :--- | :---: | :---: |
| `title` | Uses the title attribute to match | :heavy_check_mark: | :heavy_check_mark: |
| `studio` | Uses the studio attribute to match | :heavy_check_mark: | :heavy_check_mark: |
| `filepath` | Uses the item's filepath to match | :heavy_check_mark: | :heavy_check_mark: |
| `audio_track_title` | Uses the audio track titles to match | :heavy_check_mark: | :x: |

## Tag Filters
Tag filters can be used with either no modifier or with `.not`.

Tag filters can take multiple values as a **list or a comma-separated string**.

The `original_language` filter will also filter out movies from being added to Radarr.

### Modifier

| Tag Modifier | Description |
| :--- | :--- |
| No Modifier | Matches every item where the attribute matches the given string |
| `.not` | Matches every item where the attribute does not match the given string |

### Attribute

| Tag Filters | Description | Movie<br>Libraries | Show<br>Libraries |
| :--- | :--- | :---: | :---: |
| `actor` | Uses the actor tags to match | :heavy_check_mark: | :heavy_check_mark: |
| `collection` | Uses the collection tags to match | :heavy_check_mark: | :heavy_check_mark: |
| `content_rating` | Uses the content rating tags to match | :heavy_check_mark: | :heavy_check_mark: |
| `country` | Uses the country tags to match | :heavy_check_mark: | :x: |
| `director` | Uses the director tags to match | :heavy_check_mark: | :x: |
| `genre` | Uses the genre tags to match | :heavy_check_mark: | :heavy_check_mark: |
| `label` | Uses the label tags to match | :heavy_check_mark: | :heavy_check_mark: |
| `producer` | Uses the actor tags to match | :heavy_check_mark: | :x: |
| `year` | Uses the year tag to match | :heavy_check_mark: | :heavy_check_mark: |
| `writer` | Uses the writer tags to match | :heavy_check_mark: | :x: |
| `original_language` | Uses TMDb original language [ISO 639-1 codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) to match<br>Example: `original_language: en, ko` | :heavy_check_mark: | :x: |
| `resolution` | Uses the resolution tag to match | :heavy_check_mark: | :x: |
| `audio_language` | Uses the audio language tags to match | :heavy_check_mark: | :x: |
| `subtitle_language` | Uses the subtitle language tags to match | :heavy_check_mark: | :x: |

## Date Filters
Date filters can be used with either no modifier or with `.not`, `.before`, `.after`, or `.regex`.

Date filters can **NOT** take multiple values.

The `first_episode_aired` and `last_episode_aired` filters will also filter out movies/shows from being added to Radarr/Sonarr.

### Modifier

| Date Modifier | Description | Format |
| :--- | :--- | :---: |
| No Modifier | Matches every item where the date attribute<br>is in the last X days | **Format:** number of days<br>e.g. `30` |
| `.not` | Matches every item where the date attribute<br>is not in the last X days | **Format:** number of days<br>e.g. `30` |
| `.before` | Matches every item where the date attribute<br>is before the given date | **Format:** MM/DD/YYYY<br>e.g. `01/01/2000` |
| `.after` | Matches every item where the date attribute<br>is after the given date | **Format:** MM/DD/YYYY<br>e.g. `01/01/2000` |
| `.regex` | Matches every item where the attribute matches the regex given | N/A |

### Attribute

| Date Filter | Description | Movie<br>Libraries | Show<br>Libraries |
| :--- | :--- | :---: | :---: |
| `release` | Uses the release date attribute (originally available) to match | :heavy_check_mark: | :heavy_check_mark: |
| `added` | Uses the date added attribute to match | :heavy_check_mark: | :heavy_check_mark: |
| `last_played` | Uses the date last played attribute to match | :heavy_check_mark: | :heavy_check_mark: |
| `first_episode_aired` | Uses the first episode aired date to match | :x: | :heavy_check_mark: |
| `last_episode_aired` | Uses the last episode aired date to match | :x: | :heavy_check_mark: |

## Number Filters
Number filters must use `.gt`, `.gte`, `.lt`, or `.lte` as a modifier.

Number filters can **NOT** take multiple values.

The `tmdb_vote_count` and `tmdb_year` filters will also filter out movies/shows from being added to Radarr/Sonarr.

### Modifier

| Number Modifier | Description | Format |
| :--- | :--- | :---: |
| `.gt` | Matches every item where the number attribute<br>is greater then the given number | **Format:** number<br>e.g. `30`, `1995`, or `7.5` |
| `.gte` | Matches every item where the number attribute<br>is greater then or equal to the given number | **Format:** number<br>e.g. `30`, `1995`, or `7.5` |
| `.lt` | Matches every item where the number attribute<br>is less then the given number | **Format:** number<br>e.g. `30`, `1995`, or `7.5` |
| `.lte` | Matches every item where the number attribute<br>is less then or equal to the given number | **Format:** number<br>e.g. `30`, `1995`, or `7.5` |

### Attribute

| Number Filters | Description | Restrictions | Movie<br>Libraries | Show<br>Libraries |
| :--- | :--- | :---: | :---: | :---: |
| `year` | Uses the year attribute to match | `1800` - `Current Year` | :heavy_check_mark: | :heavy_check_mark: |
| `tmdb_year` | Uses the year on TMDb to match | `1800` - `Current Year` | :heavy_check_mark: | :heavy_check_mark: |
| `critic_rating` | Uses the critic rating attribute to match | `0.0` - `10.0` | :heavy_check_mark: | :heavy_check_mark: |
| `audience_rating` | Uses the audience rating attribute to match | `0.0` - `10.0` | :heavy_check_mark: | :heavy_check_mark: |
| `user_rating` | Uses the user rating attribute to match | `0.0` - `10.0` | :heavy_check_mark: | :heavy_check_mark: |
| `tmdb_vote_count` | Uses the tmdb vote count to match | minimum: `1` | :heavy_check_mark: | :heavy_check_mark: |
| `plays` | Uses the plays attribute to match | minimum: `1` | :heavy_check_mark: | :x: |
| `duration` | Uses the duration attribute to match using minutes | minimum: `1` | :heavy_check_mark: | :x: |

## Special Filters
Special Filters each have their own set of rules for how they're used.

### Attribute

| Special Filters | Description | Movie<br>Libraries | Show<br>Libraries |
| :--- | :--- | :---: | :---: |
| `history` | Uses the release date attribute (originally available) to match dates throughout history<br>`day`: Match the Day and Month to Today's Date<br>`month`: Match the Month to Today's Date<br>`1-30`: Match the Day and Month to Today's Date or `1-30` days before Today's Date  | :heavy_check_mark: | :heavy_check_mark: |

## Collection Filter Examples

A few examples are listed below:

```yaml
collections:
  1080p Documentaries:
    genre: Documentary
    summary: A collection of 1080p Documentaries
    filters:
      resolution: 1080
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
      release.after: 5/1/2020
      release.before: 8/31/2020
```
```yaml
collections:
  Movies Released in the Last 180 Days:
    plex_all: true
    filters:
      release: 180
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
```yaml
collections:
  Movies with Commentary:
    plex: all
    filters:
      audio_track_title: Commentary
```
