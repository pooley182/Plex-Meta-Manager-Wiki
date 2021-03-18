You can build different collections using the lists on [Letterboxd.com](https://letterboxd.com/) (Letterboxd). 

No configuration is required for these builders.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :--- | :--- | :--- | :---: | :---: |
| [Letterboxd List](#letterboxd-list) | `letterboxd_list` | Gets every movie in the Letterboxd List | :heavy_check_mark: | :x: |
| [Letterboxd List Details ](#letterboxd-list) | `letterboxd_list_details` | Gets every movie in the Letterboxd List and updates the collection with the description of the Letterboxd list | :heavy_check_mark: | :x: |

## Letterboxd List
Gets every movie in the Letterboxd List.

The expected input is a Letterboxd List URL. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Vulture’s 101 Best Movie Endings:
    letterboxd_list: https://letterboxd.com/brianformo/list/vultures-101-best-movie-endings/
```

* You can update the collection details with the Letterboxd List's description by using `letterboxd_list_details`.
* You can specify multiple collections in `letterboxd_list_details` but it will only use the first one to update the collection summary.

```yaml
collections:
  Vulture’s 101 Best Movie Endings:
    letterboxd_list_details: https://letterboxd.com/brianformo/list/vultures-101-best-movie-endings/
```
