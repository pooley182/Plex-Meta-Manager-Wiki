The script is designed so that while running the collections will update once a day. If you want a collection to only update on specific days you can add the `schedule` attribute to it.

Below is an example of a collection with multiple schedules: 
```yaml
collections:
  TMDb Trending Weekly:
    tmdb_trending_weekly: 30
    sync_mode: sync
    schedule: weekly(sunday)
  TMDb Top Rated:
    tmdb_top_rated: 30
    sync_mode: sync
    schedule: monthly(1), monthly(15)
```

The scheduling options are:
| Name | Description | Format | Example |
| :-- | :-- | :-- | :-- |
| Weekly | Update this collection once a week on the specified day | weekly(Day of Week) | weekly(sunday) |
| Monthly | Update this collection once a month on the specified day | monthly(Day of Month) | monthly(1) |
| Yearly | Update this collection once a year on the specified day | yearly(MM/DD) | yearly(01/30) |

* To do a daily collection update simply do not include the `schedule` attribute
* You can have multiple scheduling options just make them a list or comma separated values