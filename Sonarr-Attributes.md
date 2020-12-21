Configuring Sonarr is optional but will allow you to send shows to a Sonarr instance when they're found missing while updating a library's collections. A `sonarr` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `sonarr` mapping individually per library. A TMDb configuration is required to use Sonarr. Here's the full set of attributes you can set with a `sonarr` mapping:

```YAML
sonarr:
  url: http://192.168.1.12:32789
  token: ################################
  quality_profile_id: 4
  root_folder_path: S:/Shows
  add: true
  search: false
```

| Name | Attribute | Allowed Values| Default | Required |
| :-- | :-- | :-- | :-- | :--: |
| Sonarr URL | `url` | Sonarr URL<br><strong>Example:</strong> http://192.168.1.12:32788 | N/A | :heavy_check_mark: |
| API Token | `token` | Sonarr API Token | N/A | :heavy_check_mark: |
| Root Folder Path | `root_folder_path` | Sonarr Root Folder Path To Use | N/A | :heavy_check_mark: |
| Quality Profile ID | `quality_profile_id` | Quality Profile ID To Use | N/A | :heavy_check_mark: |
| Add | `add` | Add missing shows found to Sonarr<br><strong>boolean:</strong> true or false | false | :x: |
| Search | `search` | Search when adding missing shows to Sonarr<br><strong>boolean:</strong> true or false | false | :x: |


* The `token` can be found by going to `Sonarr > Settings > General > Security > API Key`

* The `quality_profile_id` is the number of the desired profile. It can be found by going to `Sonarr > Settings > Profiles`. Unfortunately, there's not an explicit place to find the `id`, but you can infer it from the `Profiles` page. Each profile is numbered, starting at `1` and incrementing by one, left-to-right, top-to-bottom. For example, the default Sonarr installation comes with four profiles:
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

In this example, to set any added shows to the `Ultra-HD` profile, set `quality_profile_id` to `5`. To set any added shows to `HD-1080p`, set `quality_profile_id` to `4`.