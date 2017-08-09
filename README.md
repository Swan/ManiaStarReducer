# ManiaStarReducer
Takes an osu!mania beatmap and fixes any found star rating inflated patterns.

When calculating star rating, osu!mania considers the density of notes to be a huge factor of difficulty. However, this can easily be abused by short and close LN (Mania Hold) patterns. It does not correctly reflect the difficulty of the map, causing the star rating to be heavily inflated.

**What exactly do you consider an inflated pattern?**

* The start times of LNs are too close together, but not directly on top of each other. In this case, if the player is hitting LNs on 1/8th notes, consider that partially inflated.
* If the LNs have a small and less than 1/4th per beat hold time.

If both of these cases are true, it will replace the current LN patterns with a normal note, thus making it the same beatmap playability wise, while reducing the star rating to its **REAL** value

# Example
```py
from deflate import fix_star_rating

# The beatmap that you are checking and fixing inflated patterns for
beatmap_path = "./Chip Skylark - Shiny Teeth (Of Mass M Remix) (Swan) [Vibro Teeth].osu"

# The new difficulty name (Version) of the beatmap
new_difficulty_name = "fixed"

# The output file path of the beatmap
output_path = "./Chip Skylark - Shiny Teeth (Of Mass M Remix) (Swan) [fixed].osu"

fix_star_rating(beatmap_path, new_difficulty_name, output_path)
```

# Media
![alt text](https://juicy.eggplants.org/ovy6ef.png)

# MIT
All the code in this repository is licensed under [MIT](https://github.com/Swan/ManiaStarReducer/blob/master/LICENSE)
