---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Commands

| Command                              | Permission                | Description                                                |
| ------------------------------------ | ------------------------- | ---------------------------------------------------------- |
| /Tags                                | DeluxeTags.GUI            | <p>Opens the tags GUI <br>to select a tag.</p>             |
| /Tags List                           | DeluxeTags.List           | Lists your available tags.                                 |
| /Tags List All                       | DeluxeTags.List.All       | Lists all loaded tags.                                     |
| /Tags List \<Player>                 | DeluxeTags.List.Player    | Lists the specified player's available tags.               |
| /Tags Select \<TagID>                | DeluxeTags.Select         | Selects the specified tag.                                 |
| /Tags Set \<Player> \<TagID>         | DeluxeTags.Set            | <p>Sets the specified tag <br>to the specified player.</p> |
| /Tags Clear \<Player>                | DeluxeTags.Clear          | Clears the player's tag.                                   |
| /Tags Create \<TagID> \<Tag>         | DeluxeTags.Create         | Creates new tag.                                           |
| /Tags Delete \<TagID>                | DeluxeTags.Delete         | Deletes the specified tag.                                 |
| /Tags SetOrder \<TagID> \<Order>     | DeluxeTags.SetOrder       | Sets the specified tag's order.                            |
| /Tags SetDisplay \<TagID> \<Display> | DeluxeTags.SetDisplay     | Sets the specified tag's display.                          |
| /Tags SetDesc \<TagID> \<Desc>       | DeluxeTags.SetDescription | <p>Sets the specified <br>tag's description.</p>           |
| /Tags Reload                         | DeluxeTags.Reload         | Reloads the plugin's files.                                |
| /Tags Version                        | -                         | Displays the plugin's version.                             |
| /Tags Help                           | -                         | Displays the player's available commands.                  |

## Permissions

{% hint style="info" %}
People with DeluxeTags.Tag.\<TagID> will still be able to see the tags in the GUI without the DeluxeTags.See.\<TagID> permission.
{% endhint %}

| DeluxeTags.See.\<TagID>                   | Gives access to see the specified tag in the /tags GUI without being able to select it. |
| ----------------------------------------- | --------------------------------------------------------------------------------------- |
| DeluxeTags.See.All                        | Gives access to see all tags in the /tags GUI without being able to select them.        |
| <p></p><p>DeluxeTags.Tag.&#x3C;TagID></p> | Gives access to the specified tag.                                                      |
| DeluxeTags.ForceTag.\<TagID>              | Force the specified tag to the player if `force_tags:` option is enabled.               |

{% hint style="info" %}
All text between the less-than and greater-than signs (**<>**) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs (**<>**).
{% endhint %}
