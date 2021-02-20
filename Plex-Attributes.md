Configuring Plex is required in order to connect to your libraries. 

A `plex` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `plex` mapping individually per library. 

Below is a `plex` mapping example and the full set of attributes:
```yaml
plex:
  url: http://192.168.1.12:32400
  token: ####################
  asset_directory: config/assets
  sync_mode: append
  show_unmanaged: true
  show_filtered: false
  show_missing: true
  save_missing: true
```

| Name | Attribute | Allowed Values | Default | Required |
| :-- | :-- | :-- | :--: | :--: |
| Server URL | `url` | Plex Server URL<br><strong>Example:</strong> http://192.168.1.12:32400 | N/A | :heavy_check_mark: |
| Authentication Token | `token` | Plex Server Authentication Token | N/A | :heavy_check_mark: |
| Asset Directory | `asset_directory` | System Location For Assets | [Directory containing YAML config]/assets | :x: |
| Sync Mode | `sync_mode` | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection | append | :x: |
| Show Unmanaged Collections | `show_unmanaged` | Show collections not managed by Plex Meta Manager at the end of each run<br>**boolean:** true or false | true | :x: |
| Show Filtered Collections | `show_filtered` | Library Level toggle to show filtered collections<br>**boolean:** true or false | false | :x: |
| Show Missing | `show_missing` | Library Level toggle to show movies/shows missing from collections<br>**boolean:** true or false | true | :x: |
| Save Missing | `save_missing` | Library Level toggle to save movies/shows missing from collections to a file next to you Metadata file<br>**boolean:** true or false | true | :x: |


* This script can be run on a remote Plex server, but be sure that the `url` provided is publicly addressable and it's recommended to use `HTTPS`.

* If you need help finding your Plex authentication token, please see Plex's [support article](https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/).