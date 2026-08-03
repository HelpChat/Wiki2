---
description: Allow players to select chat tags that can be awarded by permission!
---

# DeluxeTags

## Description

**DeluxeTags** gives players an extra tag that can be displayed in chat, tab lists, scoreboards, and any other plugin that supports PlaceholderAPI. Tags are permission based, so a player can unlock multiple tags and select the one they want from a configurable GUI.

## Features

* Create an unlimited number of permission-based tags.
* Organize tags into configurable categories.
* Automatically skip the category selector when a player can only see tags in one category.
* Configure the display name, lore, material, and data value of every tag item.
* Use legacy color codes, hex colors, or MiniMessage formatting.
* Customize the GUI layout, navigation buttons, and modern item model data.
* Grant tags as selectable, visible-only, forced, or default tags.
* Use built-in PlaceholderAPI placeholders with almost any chat plugin.
* Receive update notifications sourced from Modrinth.
* Use DeluxeTags' own chat formatter when no separate chat plugin is installed.

## Documentation

{% content-ref url="categories-and-gui.md" %}
[categories-and-gui.md](categories-and-gui.md)
{% endcontent-ref %}

{% content-ref url="formatting.md" %}
[formatting.md](formatting.md)
{% endcontent-ref %}

{% content-ref url="commands-and-permissions.md" %}
[commands-and-permissions.md](commands-and-permissions.md)
{% endcontent-ref %}

{% content-ref url="placeholders.md" %}
[placeholders.md](placeholders.md)
{% endcontent-ref %}

{% content-ref url="files.md" %}
[files.md](files.md)
{% endcontent-ref %}

## Setup

### Chat plugins with PlaceholderAPI support

1. Stop the server.
2. Place the DeluxeTags JAR in the server's `plugins` folder.
3. Start the server once to generate the configuration files.
4. Edit `/plugins/DeluxeTags/config.yml` and `/plugins/DeluxeTags/messages.yml`.
5. Set `papi_chat: true` in `config.yml`.
6. Add the required [DeluxeTags placeholders](placeholders.md) to the chat plugin's format.
7. Restart the server.
8. Grant players `deluxetags.tag.<identifier>` for each tag they may select.
9. Players can now open `/tags` and select a tag.

### DeluxeTags' built-in chat formatter

1. Place the DeluxeTags JAR in the server's `plugins` folder and start the server once.
2. Set `papi_chat: false` in `config.yml`.
3. Set `format_chat.enabled: true`.
4. Customize `format_chat.format`. The default is `{deluxetags_tag} <%1$s> %2$s`.
5. Make sure another plugin is not also changing the chat format.
6. Restart the server.

{% hint style="warning" %}
Back up `config.yml` before upgrading. DeluxeTags 1.9 automatically migrates existing tag GUI settings to the new per-tag format and places uncategorized tags in the `general` category.
{% endhint %}
