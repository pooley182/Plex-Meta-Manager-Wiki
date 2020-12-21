Configuring Plex is required in order to connect to your library. A `plex` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `plex` mapping individually per library. Here's the full set of attributes you can set with a `plex` mapping:

```yaml
plex:
  url: http://192.168.1.12:32400
  token: ####################
  asset_directory: config/assets
  sync_mode: append
```

| Name | Attribute | Allowed Values | Default | Required |
| :-- | :-- | :-- | :-- | :--: |
| Server URL | `url` | Plex Server URL<br><strong>Example:</strong> http://192.168.1.12:32400 | N/A | :heavy_check_mark: |
| Authentication Token | `token` | Plex Server Authentication Token | N/A | :heavy_check_mark: |
| Asset Directory | `asset_directory` | System Location For Assets | Directory of Config/assets | :x: |
| Sync Mode | `sync_mode` | `append`: Only Add Items to the Collection<br>`sync`: Add & Remove Items from the Collection | append | :x: |

* This script can be run on a remote Plex server, but be sure that the `url` provided is publicly addressable and it's recommended to use `HTTPS`.
* If you need help finding your Plex authentication token, please see Plex's [support article](https://support.plex.tv/articles/204059436-finding-an-authentication-token-x-plex-token/).