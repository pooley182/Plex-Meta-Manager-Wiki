Configuring Sonarr is optional but will allow you to send shows to a Sonarr instance when they're found missing while updating a library's collections.

A `sonarr` mapping can be either in the root of the config file as global mapping for all libraries or you can specify the `sonarr` mapping individually per library.

Below is a `sonarr` mapping example and the full set of attributes:
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
| :-- | :-- | :-- | :--: | :--: |
| Sonarr URL | `url` | Sonarr URL<br><strong>Example:</strong> http://192.168.1.12:32788 | N/A | :heavy_check_mark: |
| API Token | `token` | Sonarr API Token | N/A | :heavy_check_mark: |
| Root Folder Path | `root_folder_path` | Sonarr Root Folder Path To Use | N/A | :heavy_check_mark: |
| Quality Profile ID | `quality_profile_id` | Quality Profile ID To Use | N/A | :heavy_check_mark: |
| Add | `add` | Add missing shows found to Sonarr<br><strong>boolean:</strong> true or false | false | :x: |
| Search | `search` | Search when adding missing shows to Sonarr<br><strong>boolean:</strong> true or false | false | :x: |


* The `token` can be found by going to `Sonarr > Settings > General > Security > API Key`

* The `quality_profile_id` is the number of the desired profile. The IDs of default Profiles are below and if you add a custom Quality Profile it is given the next number available.

| Name | Profile ID |
| :-- | :--: |
| Any | 1 |
| SD | 2 |
| HD-720p | 3 |
| HD-1080p | 4 |
| Ultra-HD | 5 |
| HD - 720p/1080p | 6 |

Alternatively instead of a number you can write the exact name of the profile and the script will attempt to find the Profile ID