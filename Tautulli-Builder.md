You can build different collections using the features of Tautulli.

It has watch analytics that can show the most watched or most popular Movies/Shows in each Library. 

Unlike other builder sections theres only one attribute, `tautulli`, but is has a few different subattributes detailed below.

| Attribute | Description | Required | Default |
| :-- | :-- | :--: | :--: |
| `list_type` | `watched` (For Most Watched Lists)<br>`popular` (For Most Popular Lists) | :heavy_check_mark: | N/A |
| `list_days` | Number of Days to look back of the list | :x: | 30 |
| `list_size` | Number of Movies/Shows to add to this list | :x: | 10 |
| `list_buffer` | Number of extra Movies/Shows to grab in case you have multiple show/movie Libraries. | :x: | 10 |

If you have multiple movie Libraries or multiple show Libraries Tautulli combines those in the popular/watched lists so there might not be 10 movies/shows from the library to make your `list_size`. 

In order to get around that you can use the `list_buffer` attribute that defaults to 10. This will get that number more movies from Tautulli but only add to the collection untilthe size reaches the number in `list_size`. 

So if your collection doesn't have as many movies/shows as your `list_size` attribute increase the number in the `list_buffer` attribute.

```yaml
collections:
  Most Popular Movies (30 Days):
    sync_mode: sync
    collection_mode: show_items
    tautulli:
      list_type: popular
      list_days: 30
      list_size: 10
```
```yaml
collections:
  Most Watched Movies (30 Days):
    sync_mode: sync
    collection_mode: show_items
    tautulli:
      list_type: watched
      list_days: 30
      list_size: 10
      list_buffer: 20
```