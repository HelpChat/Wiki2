---
description: >-
  Create custom text commands which utilize JSON and allows player specific
  placeholders!
---

# DeluxeCommands

## Description

Ever wanted to create custom text commands which allow you to utilize JSON formatting? Now you can create text-based commands which allow you to have tooltips, click events, and much more!  
This can be used for awesome info-packed /vote command, or even a cool /stats command, and much more!

## Features

* Hover tooltips.
* Click actions.
* Ability to create unlimited commands.
* Supports running the command as another player with different actions.
* Supports various actions, like running a command as console/player.
* [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) support.

## Creating JSON message

**JSON** message is the kind of messages that have hovering tooltips and clicking actions, you can simply create them from [minecraftjson.com](http://minecraftjson.com/) \(or any **JSON** creation website\).  
Follow the steps below to create your **JSON** message and use it in **DeluxeCommands**:

1. Create the **JSON** message using the website you like.
2. Copy the text after `@p`  from the **Command:** box. e.g.  `/tellraw @p ["",{"text":"This is a JSON text","color":"blue","clickEvent":{"action":"suggest_command","value":"/command"},"hoverEvent":{"action":"show_text","value":{"text":"","extra":[{"text":"Hey there!","color":"aqua"}]}}}]`  Copy this part only: `["",{"text":"This is a JSON text","color":"blue","clickEvent":{"action":"suggest_command","value":"/command"},"hoverEvent":{"action":"show_text","value":{"text":"","extra":[{"text":"Hey there!","color":"aqua"}]}}}]` 
3. Now paste it in your command in **DeluxeCommands** config file like this: `- '["",{"text":"This is a JSON text","color":"blue","clickEvent":{"action":"suggest_command","value":"/command"},"hoverEvent":{"action":"show_text","value":{"text":"","extra":[{"text":"Hey there!","color":"aqua"}]}}}]'` 
4. Reload **DeluxeCommands** `/DeluxeCommands reload`.
5. That's it! Enjoy your beautiful **JSON** command.

