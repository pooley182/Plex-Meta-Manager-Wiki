A `tmdb` mapping in the config is optional but highly reccomended. Here's the full set of attributes you can set:

```yaml
tmdb:
  apikey: ################################
  language: en
```

| Attribute | Description | Default | Required |
| :-- | :-- | :-- | :--: |
| `apikey` | User TMDb API Key | N/A | :heavy_check_mark: |
| `language` | User Language | en | :x: |

* If you do not have an API key please refer to this [guide](https://developers.themoviedb.org/3/getting-started/introduction).