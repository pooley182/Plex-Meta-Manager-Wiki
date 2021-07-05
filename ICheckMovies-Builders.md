You can build different collections using the lists on [icheckmovies.com](https://www.icheckmovies.com/) (ICheckMovies). 

No configuration is required for these builders.

| Name | Attribute | Description | Works with Movies | Works with Shows |
| :--- | :--- | :--- | :---: | :---: |
| [ICheckMovies List](#icheckmovies-list) | `icheckmovies_list` | Gets every movie in the ICheckMovies List | :heavy_check_mark: | :x: |
| [ICheckMovies List Details](#icheckmovies-list) | `icheckmovies_list_details` | Gets every movie in the ICheckMovies List and updates the collection with the description of the ICheckMovies list | :heavy_check_mark: | :x: |

## ICheckMovies List
Gets every movie in the ICheckMovies List.

The expected input is a ICheckMovies List URL. Multiple values are supported as either a list or a comma-separated string.

```yaml
collections:
  Vulture’s 101 Best Movie Endings:
    icheckmovies_list: https://www.icheckmovies.com/lists/academy+award+-+best+picture
```

* You can update the collection details with the ICheckMovies List's description by using `icheckmovies_list_details`.
* You can specify multiple collections in `icheckmovies_list_details` but it will only use the first one to update the collection summary.

```yaml
collections:
  Vulture’s 101 Best Movie Endings:
    icheckmovies_list_details: https://www.icheckmovies.com/lists/academy+award+-+best+picture
```
