A `plex` mapping in the config is required. Here's the full set of attributes you can set:

```yaml
plex:
  url: http://192.168.1.12:32400              # Can be individually specified per library as well
  token: ####################                 # Can be individually specified per library as well
  asset_directory: config/assets              # Can be individually specified per library as well
  sync_mode: append                           # Can be individually specified per library as well
  add_to_arr: false                           # Can be individually specified per library as well
  cache: true                                 
  cache_update_interval: 60
  libraries:
    Movies:                                   # Name of library
      library_type: movie                     # Type of Plex Library ('movie' or 'show')
    TV Shows:
      library_type: show
      url: http://192.168.1.35:32400          # This is only needed if your library is on a
      token: ####################             # different server from your global server
```

| Attribute | Description | Default | Required | Per Library |
| :-- | :-- | :-- | :--: | :--: |
| `url` | Plex Server URL<br><strong>Example:</strong> http://192.168.1.12:32400 | N/A | :heavy_check_mark: | :heavy_check_mark: |
| `token` | Plex Server Authentication Token | N/A | :heavy_check_mark: | :heavy_check_mark: |
| `asset_directory` | System Location For Assets | /config/assets | :x: | :heavy_check_mark: |
| `sync_mode` | Global Sync Mode<br><strong>Options:</strong><br>`append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection | append | :x: | :heavy_check_mark: |
| `add_to_arr` | Global Add to Radarr/Sonarr<br><strong>boolean:</strong> true or false | false| :x: | :heavy_check_mark: |
| `cache` | Store GUID mappings in a file next to your config<br><strong>boolean:</strong> true or false | true | :x: | :x: |
| `cache_update_interval` | How many days before the program updates the GUID in the cache<br><strong>integer:</strong> min 1 | 60 | :x: | :x: |
| `libraries` | Attribute to define the libraries inside of | N/A | :heavy_check_mark: | :x: |
| `library_type` | Type of Plex Library required per library<br><strong>Options:</strong> movie or show | N/A | :heavy_check_mark: | :heavy_check_mark: |

* All Attributes with a :heavy_check_mark: in the Per Library column can be set on a per library basis if needed.
* This script can be run on a remote Plex server, but be sure that the `url` provided is publicly addressable and it's recommended to use `HTTPS`.
* If you need help finding your Plex authentication token, please see Plex's [support article](https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/).