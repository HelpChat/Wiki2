---
description: >-
  Highly customizable permission based join and leave "action" plugin with tons
  of placeholders!
---

# DeluxeJoin

## Description

**DeluxeJoin** is the all in one plugin for join and leave actions. You can create group based join and leave action lists that are performed from a wide variety of things. It also features a permission-based in-game MOTD system which allows players to view MOTD messages on join and by command.

## Features

* Hover tooltips.
* Click actions.
* Unlimited permission-based join/leave messages.
* Unlimited permission-based MOTD messages on join.
* Unique first join message.
* Supports all the actions you would need!
* [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) support.

## Creating a JSON message

**JSON** message is the kind of messages that have hovering tooltips and clicking actions, you can simply create them from [minecraftjson.com](http://minecraftjson.com) (or any **JSON** creation website).\
Follow the steps below to create your **JSON** message and use it in **DeluxeJoin**:

1. Create the **JSON** message using the website you like.
2. Copy the text between `["",` and `]` from the **Command:** box. e.g.\
   \
   `/tellraw @p ["",{"text":"This is a JSON text","color":"blue","clickEvent":{"action":"suggest_command","value":"/command"},"hoverEvent":{"action":"show_text","value":{"text":"","extra":[{"text":"Hey there!","color":"aqua"}]}}}]`\
   \
   Copy this part only:\
   `{"text":"This is a JSON text","color":"blue","clickEvent":{"action":"suggest_command","value":"/command"},"hoverEvent":{"action":"show_text","value":{"text":"","extra":[{"text":"Hey there!","color":"aqua"}]}}}`\
   \
   **Note:** If you have more than one **JSON** text in the same line, split them with `&&` (Check the default config).
3. Now paste it in your format in **DeluxeJoin** config file like this:\
   `- '[JSON] {"text":"Welcome %player_name%!","color":"blue","clickEvent":{"action":"suggest_command","value":"/command"},"hoverEvent":{"action":"show_text","value":{"text":"","extra":[{"text":"Hey there!","color":"aqua"}]}}}'`\

4. Reload **DeluxeJoin** `/DeluxeJoin reload`.
5. That's it! Enjoy your beautiful **JSON** messages.
