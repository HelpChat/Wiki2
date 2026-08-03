---
description: Plugin's placeholders
---

# Placeholders

{% hint style="info" %}
Replace `<identifier>` with the tag's identifier without the angle brackets.
{% endhint %}

## PlaceholderAPI placeholders

DeluxeTags includes its own [PlaceholderAPI](https://www.spigotmc.org/resources/6245/) expansion. No separate eCloud download is required.

| Placeholder | Return value | Description |
| --- | --- | --- |
| `%deluxetags_tag%` | Text | The player's active tag display. |
| `%deluxetags_identifier%` | Text | The player's active tag identifier. |
| `%deluxetags_description%` | Text | The player's active tag description. |
| `%deluxetags_order%` | Number | The player's active tag order. |
| `%deluxetags_amount%` | Number | The number of tags the player has permission to select. |
| `%deluxetags_tag_<identifier>%` | Text | The configured display of a specific tag. |
| `%deluxetags_description_<identifier>%` | Text | The configured description of a specific tag. |
| `%deluxetags_order_<identifier>%` | Number | The configured order of a specific tag. |
| `%deluxetags_has_tag_<identifier>%` | Boolean | Whether the player has permission to select a specific tag. |

## Internal placeholders

Internal placeholders can be used in DeluxeTags' GUI text, item names, lore, and other supported configuration strings. Both percent and brace forms are supported, for example `%deluxetags_tag%` and `{deluxetags_tag}`.

| Placeholder | Return value | Description |
| --- | --- | --- |
| `%player%` | Text | The player's username. |
| `%displayname%` | Text | The player's display name. |
| `%deluxetags_tag%` | Text | The displayed tag's value, or the active tag where appropriate. |
| `%deluxetags_identifier%` | Text | The displayed tag's identifier. |
| `%deluxetags_description%` | Text | The displayed tag's description. |
| `%deluxetags_amount%` | Number | The total number of tags the player can select. |
| `%deluxetags_category_amount%` | Number | The number of tags the player can select in the current category. In `all`, this is the total available tag count. |
| `%deluxetags_available%` | Text | The configured `gui.tag_availability_placeholder` value for the displayed tag. |

## GUI page placeholders

| Placeholder | Description |
| --- | --- |
| `%previous_page%` | Previous page number, or an empty value on the first page. |
| `%current_page%` | Current page number. |
| `%next_page%` | Next page number, or an empty value on the last page. |
| `%page%` | Destination page number when used on the next or previous page item. Kept for compatibility with older configurations. |

The brace forms `{previous_page}`, `{current_page}`, `{next_page}`, and `{page}` are also supported.
