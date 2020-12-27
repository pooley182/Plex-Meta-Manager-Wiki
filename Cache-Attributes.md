Having a cache to store each Plex GUID and its accompanying IDs is highly recommended because it will vastly speed up the execution of the script.

A `cache` mapping is in the root of the config file.

Below is a `cache` mapping example and the full set of attributes:
```yaml
cache:
  cache: true
  cache_update_interval: 60
```

| Name | Attribute | Allowed Values | Default | Required |
| :-- | :-- | :-- | :--: | :--: |
| Cache | `cache` | Should the script store a cache<br><strong>boolean:</strong> true or false | true | :x: |
| Cache Update Interval | `cache_update_interval` | Interval at which the cache updates each GUID<br><strong>boolean:</strong> true or false | 60 | :x: |

* The cache database file is created in the same location as your config file.