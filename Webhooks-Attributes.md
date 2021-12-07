Configuring Webhooks is optional but can allow you to receive notifications when certain events happen.

A `webhooks` mapping is in the root of the config file.

Below is a `webhooks` mapping example and the full set of attributes:

```yaml
webhooks:
  error: https://www.myspecialdomain.com/pmm
  run_start:
  run_end:
  collection_changes:
```

| Name | Attribute | Global | Library | Collection |
| :--- | :--- | :---: | :---: | :---: |
| [Error](#error-notifications) | `error` | :heavy_check_mark: | :heavy_check_mark: | :x: |
| [Run Start](#run-start-notifications) | `run_start` | :heavy_check_mark: | :x: | :x: |
| [Run End](#run-end-notifications) | `run_end` | :heavy_check_mark: | :x: | :x: |
| [Collection Changes](#collection-notifications) | `collection_changes` | :heavy_check_mark: | :heavy_check_mark: | :heavy_check_mark: |

* Each Attribute can be either a webhook url as a string or a comma-separated list of webhooks urls.
* To send notifications to [Notifiarr](https://github.com/meisnate12/Plex-Meta-Manager/wiki/Notifiarr-Attributes) just add `notifiarr` to a webhook instead of the webhook url.

## Error Notifications

The Error notification will be sent whenever an error occurs. The payload that is sent is different Depending on which level the error occurs.

#### Global JSON Payload

```yaml
{
  "error": str,         // Error Message
  "critical": bool      // Critical Error
}
```

#### Library JSON Payload

```yaml
{
  "error": str,         // Error Message
  "critical": bool,     // Critical Error
  "server_name": str,   // Server Name
  "library_name": str   // Library Name
}
```

#### Collection JSON Payload

```yaml
{
  "error": str,         // Error Message
  "critical": bool,     // Critical Error
  "server_name": str,   // Server Name
  "library_name": str,  // Library Name
  "collection": str     // Collection Name
}
```

## Run Start Notifications

The Run Start notification will be sent at the beginning of every run.

#### JSON Payload

```yaml
{
  "start_time": str,            // Time Run is started Format "YY-mm-dd HH:MM:SS"
}
```

## Run End Notifications

The Run End notification will be sent at the end of every run with statistics.

#### JSON Payload

```yaml
{
  "start_time": str,            // Time Run started Format "YY-mm-dd HH:MM:SS"
  "end_time": str,              // Time Run ended Format "YY-mm-dd HH:MM:SS"
  "run_time": str,              // Time Run took to complete Format "HH:MM"
  "collections_created": int,   // Number of Collections Created
  "collections_modified": int,  // Number of Collections Modified
  "collections_deleted": int,   // Number of Collections Removed
  "items_added": int,           // Number of Items added across all Collections
  "items_removed": int,         // Number of Items removed across all Collections
  "added_to_radarr": int,       // Number of Items added to Radarr
  "added_to_sonarr": int        // Number of Items added to Sonarr
}
```

## Collection Notifications

The Collection Notification will be sent after each collection containing the following payload if the collection has been created, has new items, or has had items removed.

#### JSON Payload

```yaml
{
  "server_name": str,           // Server Name
  "library_name": str,          // Library Name
  "type": str,                  // Will be either "movie" or "show"
  "collection": str,            // Collection Name
  "created": bool,              // Was the Collection Created on this run
  "poster": str,                // Base64 Encoded Collection Poster
  "background": str,            // Base64 Encoded Collection Background
  "additions": [int],           // List of TMDb/TVDb IDs added to the colleciton
  "removals": [int]             // List of TMDb/TVDb IDs removed from the colleciton
}
```

* TMDb IDs are sent if the `type` is `movie` and TVDb IDs are sent if the type is `show`
