---
description: Plugin's placeholders
---

# Placeholders

{% hint style="info" %}
All text between the less-than and greater-than signs (**<>**) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs (**<>**).
{% endhint %}

**DeluxeTags** plugin provides [**PlaceholderAPI** ](https://www.spigotmc.org/resources/6245/)placeholders that you can use in any plugin that supports [**PlaceholderAPI**](https://www.spigotmc.org/resources/6245/).

| Placeholder                         | Return Value | Description                                                           |
| ----------------------------------- | ------------ | --------------------------------------------------------------------- |
| %deluxetags\_tag%                   | Text         | Returns the player's current tag.                                     |
| %deluxetags\_amount%                | Number       | Returns the total of the player's available tags.                     |
| %deluxetags\_order%                 | Number       | Returns the player's current tag's order.                             |
| %deluxetags\_description%           | Text         | Returns the player's current tag's description.                       |
| %deluxetags\_identifier%            | Text         | Returns the player's current tag's identifier.                        |
| %deluxetags\_tag\_\<TagID>%         | Text         | Returns the specified tag.                                            |
| %deluxetags\_order\_\<TagID>%       | Number       | Returns the specified tag's order.                                    |
| %deluxetags\_description\_\<TagID>% | Text         | Returns the specified tag's description.                              |
| %deluxetags\_has\_tag\_\<TagID>%    | Boolean      | Returns whether if the player has access to the specified tag or not. |

## Download

**There is no need to download the expansion anymore!** The expansion was moved inside the plugin itself in the 1.8.2 update which means less work for you! As long as you have PlaceholderAPI installed, the expansion will register automatically.
