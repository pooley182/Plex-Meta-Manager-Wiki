
### Episodes Attributes
To edit the metadata of a particular Episode in a show use the `episodes` attribute.

The mapping name uses the format S##E## to determine what episode to edit (use 0 for specials).

A simple example is below:
```yaml
metadata:
  "Avatar: The Last Airbender":
    episodes:
      S01E01:
        rating: 9.1
      S03E21:
        summary: The Epic Series Final of Avatar The Last Airbender
```

The available attributes for each episode are as follows

### General Attributes

| Name | Attribute | Allowed Values |
| :--- | :--- | :--- |
| Title | `title` | Text to change Title |
| Sort Title | `sort_title` | Text to change Sort Title |
| Originally Available | `originally_available` | Date to change Originally Available<br>**Format:** YYYY-MM-DD  |
| Rating | `rating` | Number to change Rating |
| Summary | `summary` | Text to change Summary |
| URL Poster | `url_poster` | URL of image publicly available on the internet |
| File Poster | `file_poster` | Path to image in the file system |

### Tag Attributes

You can add `.sync` to any tag attribute to sync all tags vs just appending the new ones i.e. `writer.sync`.

| Name | Attribute | Allowed Values |
| :--- | :--- | :--- |
| Writer | `writer` | List or comma-separated text of each Writer Tag |
| Director | `director` | List or comma-separated text of each Director Tag |
