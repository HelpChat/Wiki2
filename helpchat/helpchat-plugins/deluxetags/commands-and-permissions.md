---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Commands

| Command | Permission | Description |
| --- | --- | --- |
| `/tags` | `deluxetags.gui` | Opens the tag selection GUI. |
| `/tags list` | `deluxetags.list` | Lists the sender's available tags. |
| `/tags list all` | `deluxetags.list.all` | Lists all loaded tags. |
| `/tags list <player>` | `deluxetags.list.player` | Lists the specified player's available tags. |
| `/tags select <tag>` | `deluxetags.select` | Selects an available tag. |
| `/tags set <player> <tag>` | `deluxetags.set` | Sets an available tag for another player. |
| `/tags clear <player>` | `deluxetags.clear` | Clears another player's active tag. |
| `/tags create <identifier> <tag>` | `deluxetags.create` | Creates a tag. New tags are placed in `general`. |
| `/tags delete <identifier>` | `deluxetags.delete` | Deletes a tag. |
| `/tags setorder <identifier> <order>` | `deluxetags.setorder` | Changes a tag's display order. |
| `/tags setdisplay <identifier> <display>` | `deluxetags.setdisplay` | Changes the value returned for a tag's display. |
| `/tags setdesc <identifier> <description>` | `deluxetags.setdescription` | Changes a tag's description. |
| `/tags reload` | `deluxetags.reload` | Reloads the plugin's files, categories, tags, GUI, and formatting options. |
| `/tags version` | `deluxetags.version` | Displays the plugin's version. |
| `/tags help` | None | Lists only the commands the sender has permission to use. |

## Tag permissions

| Permission | Description |
| --- | --- |
| `deluxetags.tag.<identifier>` | Allows the player to see and select the tag. This is the default permission when a custom `permission` is not configured for the tag. |
| `deluxetags.see.<identifier>` | Allows the player to see the tag in `/tags` without selecting it. |
| `deluxetags.see.all` | Allows the player to see every tag in `/tags` without selecting them. |
| `deluxetags.forcetag.<identifier>` | Forces this tag when `force_tags: true`. The tag with the lowest order wins when multiple forced-tag permissions are granted. |
| `deluxetags.defaulttag.<identifier>` | Uses this tag when the player has no forced, selected, or saved tag. The tag with the lowest order wins when multiple default-tag permissions are granted. |

{% hint style="info" %}
A player can see a category when they can see or select at least one tag inside it. The category selector is only displayed when the player can see tags in two or more real categories; otherwise, DeluxeTags opens the single available category directly.
{% endhint %}

## Other permissions

| Permission | Description |
| --- | --- |
| `deluxetags.gui` | Opens the tag selection GUI. |
| `deluxetags.select` | Selects a tag by command. |
| `deluxetags.list` | Lists the sender's available tags. |
| `deluxetags.list.all` | Lists every loaded tag. |
| `deluxetags.list.player` | Lists another player's available tags. |
| `deluxetags.set` | Sets another player's tag. |
| `deluxetags.clear` | Clears another player's active tag. |
| `deluxetags.create` | Creates tags. |
| `deluxetags.delete` | Deletes tags. |
| `deluxetags.setorder` | Changes tag order. |
| `deluxetags.setdisplay` | Changes tag display text. |
| `deluxetags.setdescription` | Changes tag descriptions. |
| `deluxetags.reload` | Reloads DeluxeTags. |
| `deluxetags.version` | Views version information. |
| `deluxetags.updates` | Receives update notifications. |

{% hint style="info" %}
Replace `<identifier>` with the tag's identifier without the angle brackets. Permission names are case-insensitive, but lowercase is recommended.
{% endhint %}
