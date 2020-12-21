A `radarr` mapping in the config is optional but will allow you to send movies to a Radarr instance when they're found missing while updating collections. A TMDb configuration is required to use Radarr. Here's the full set of attributes you can set for a `radarr` mapping:

```yaml
radarr:
  url: http://192.168.1.12:32788
  token: ################################
  version: v2
  quality_profile_id: 4
  root_folder_path: S:/Movies
  add: true
  search: false
```

| Name | Attribute | Allowed Values| Default | Required |
| :-- | :-- | :-- | :-- | :--: |
| Radarr URL | `url` | Radarr URL<br><strong>Example:</strong> http://192.168.1.12:32788 | N/A | :heavy_check_mark: |
| API Token | `token` | Radarr API Token | N/A | :heavy_check_mark: |
| Radarr Version | `version` | `v2`: for < 0.2<br>`v3`: for > 3.0 | v2 | :x: |
| Root Folder Path | `root_folder_path` | Radarr Root Folder Path To Use | N/A | :heavy_check_mark: |
| Quality Profile ID | `quality_profile_id` | Quality Profile ID To Use | N/A | :heavy_check_mark: |
| Add | `add` | Add missing moives found to Radarr<br><strong>boolean:</strong> true or false | false | :x: |
| Search | `search` | Search when adding missing movies to Radarr<br><strong>boolean:</strong> true or false | false | :x: |


* The `token` can be found by going to `Radarr > Settings > General > Security > API Key`

* The `quality_profile_id` is the number of the desired profile. It can be found by going to `Radarr > Settings > Profiles`. Unfortunately, there's not an explicit place to find the `id`, but you can infer it from the `Profiles` page. Each profile is numbered, starting at `1` and incrementing by one, left-to-right, top-to-bottom. For example, the default Radarr installation comes with four profiles:
```
     1          2          3          4
    Any         SD      HD-720p    HD-1080p
```

If you were to add two more profiles, the `id` would be as follows:
```
     1          2          3          4
    Any         SD      HD-720p    HD-1080p

     5          6
 Ultra-HD HD-720p/1080p
```

In this example, to set any added movies to the `Ultra-HD` profile, set `quality_profile_id` to `5`. To set any added movies to `HD-1080p`, set `quality_profile_id` to `4`.