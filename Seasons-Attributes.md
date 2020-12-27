To edit the metadata of a particular Season in a show use the `seasons` attribute.

The mapping name is the season number (use 0 for specials).

A simple example is below:
```yaml
metadata:
  "Avatar: The Last Airbender":
    seasons:
      1:
        title: "Book One: Water"
      2:
        title: "Book Two: Earth"
      3:
        title: "Book Three: Fire"
```

The available attributes for each season are as follows
| Name | Attribute | Allowed Values |
| :-- | :-- | :-- |
| Title | `title` | Text to change Title |
| Summary | `summary` | Text to change Summary |
