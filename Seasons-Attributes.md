To edit the metadata of a particular Season in a show use the `seasons` attribute.

The mapping name is the season number (use 0 for specials).

A simple example is below:
```yaml
metadata:
  "Avatar: The Last Airbender":
    seasons:
      1:
        title: "Book One: Water"
        summary: After a lapse of 100 years, the Avatar-spiritual master of the elements-has returned. And just in the nick of time. The Four Nations (Water, Earth, Fire, and Air) have become unbalanced. The Fire Nation wants to rule the world, and its first conquest will be the Northern Water Tribe. It's up to a 12-year-old Airbender named Aang to find a way to stop it. Join Aang, Katara, Sokka, Momo, and Appa as they head north on the adventure of a lifetime.
      2:
        title: "Book Two: Earth"
        summary: 
      3:
        title: "Book Three: Fire"
```

The available attributes for each season are as follows
| Name | Attribute | Allowed Values |
| :-- | :-- | :-- |
| Title | `title` | Text to change Title |
| Summary | `summary` | Text to change Summary |
