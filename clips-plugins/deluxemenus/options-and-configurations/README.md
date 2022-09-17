---
description: About the plugin's options and configurations
---

# Options & Configurations

**DeluxeMenus** is a highly customizable plugin, it has many options and configurations to give you the ability to change everything you want to make your custom menus that fits your server's layout.\
It has **GUI** options to manage the GUI menu, and **Item** options to manage every single item on the GUI menu.

## Useful links

* [Placeholders](https://helpch.at/placeholders)
* Materials
  * [1.8.8](https://helpch.at/docs/1.8.8/org/bukkit/Material.html)
  * [1.12.2](https://helpch.at/docs/1.12.2/org/bukkit/Material.html)
  * [1.13.2](https://helpch.at/docs/1.13.2/org/bukkit/Material.html)
  * [1.14.4](https://helpch.at/docs/1.14.4/org/bukkit/Material.html)
  * [Latest](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
* [Enchantments](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html) (Be aware that some enchantments are not available on some items.)
* [Dye Colors](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/DyeColor.html)
* [Pattern Types](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html)
* [Sound Types](https://gist.github.com/Andre601/1ab3b4fabd0010ae241156333491c379)

## Values keywords

| Keyword        | Description                                                                                                                                                                                                                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **BOOLEAN**    | Replace this with `true` or `false` (If used with a PlaceholderAPI placeholder, this will be `yes` or `no` instead of `true`/`false` \[It's changeable from PlaceholderAPI config file, but `yes`/`no` are the default values]). |
| **TEXT**       | Replace this with any text. Check the description to find out if you can use color/formatting codes.                                                                                                                             |
| **#**          | Replace this with a number. Check the description to see if there are limits.                                                                                                                                                    |
| **COMMAND**    | Replace this with a command without slash (`/`).                                                                                                                                                                                 |
| **SOUND**      | Replace this with a sound name.                                                                                                                                                                                                  |
| **EXPRESSION** | Replace this with a java/placeholder expression/comparison. See [this](requirements.md) page for more information.                                                                                                               |

## Actions types

| Tag                                                            | Description                                                                                                                                                                        |
| -------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `[player] <command>`                                           | Executes a command as the player.                                                                                                                                                  |
| `[console] <command>`                                          | Executes a command from the console.                                                                                                                                               |
| `[commandevent] <command>`                                     | Executes an unregistered command as the player.                                                                                                                                    |
| `[placeholder] <papi-placeholders>`                            | Parse placeholders for a player without any chat or console output.                                                                                                                |
| `[message] <text>`                                             | Sends a message to the player. You can use [placeholders](https://helpch.at/placeholders) and color/format codes here.                                                             |
| `[broadcast] <text>`                                           | <p>Sends a message to everyone online including the console.</p><p>You can use <a href="https://helpch.at/placeholders">placeholders</a> and color/format codes here.</p>          |
| \[minimessage] \<text>                                         | Sends a message to a player using the more modern [MiniMessage](https://docs.adventure.kyori.net/minimessage/format.html) format!                                                  |
| \[minibroadcast] \<text>                                       | Sends a message to everyone online using the more modern [MiniMessage](https://docs.adventure.kyori.net/minimessage/format.html) format!                                           |
| `[openguimenu] <menu-name>`                                    | Opens another GUI from DeluxeMenus.                                                                                                                                                |
| `[connect] <server-name>`                                      | Connects the player to a server on the same BungeeCord.                                                                                                                            |
| `[close]`                                                      | Closes the currently opened GUI.                                                                                                                                                   |
| `[json] <JSON-text>`                                           | Send a json message to the player. Use [this](https://minecraftjson.com/) website to easily generate the JSON text.                                                                |
| `[jsonbroadcast] <JSON-text>`                                  | Send a json message to everyone online. Use [this](https://minecraftjson.com/) website to easily generate the JSON text.                                                           |
| `[refresh]`                                                    | Refresh items in the current menu view. This updates the shown Items themselves.                                                                                                   |
| `[broadcastsound] <sound> <volume> <pitch>`                    | Broadcast a sound to all players on the server.                                                                                                                                    |
| `[broadcastsoundworld] <sound> <volume> <pitch>`               | Broadcast a sound to all players in the world.                                                                                                                                     |
| `[sound] <sound> <volume> <pitch>`                             | Play a sound for the player.                                                                                                                                                       |
| `[takemoney] <amount>`                                         | Take a certain amount of money from the player. [Vault](https://www.spigotmc.org/resources/34315/) is required for this action to work.                                            |
| `[givemoney] <amount>`                                         | Give a certain amount of money to the player. [Vault](https://www.spigotmc.org/resources/34315/) is required for this action to work.(requires Vault)                              |
| `[takeexp] #L`                                                 | Take a certain amount of exp levels or points from a player. To give levels, add `L` at the end, otherwise remove it.                                                              |
| `[giveexp] #L`                                                 | Give a certain amount of exp levels or points to a player. To give levels, add `L` at the end, otherwise remove it                                                                 |
| `[givepermission] <perm.node>`                                 | Giv a permission to a player. [Vault](https://www.spigotmc.org/resources/vault.34315/) is required for this action to work.                                                        |
| `[takepermission] <perm.node>`                                 | Take a permission from a player. [Vault](https://www.spigotmc.org/resources/vault.34315/) is required for this action work.                                                        |
| `[meta] <set/remove/add/subtract/switch> <key> <type> <value>` | Modifies the player's meta. `add/subtract` are for number types. `switch` is for boolean, it will swap it from true/false. Check [here](requirements.md#has-meta) for more detail. |
| `[chat] <message>`                                             | Send a message in chat as the player who this action got executed for.                                                                                                             |

### **Action tags**

These tags can be added with the action (e.g. `- '[message] example<delay=20>'`).

| Tag                 | Description                                                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `<delay=<time>>`    | Executes the action after the specified delay (in ticks, 20 ticks = 1 second).                                                                   |
| `<chance=<chance>>` | Sets a chance to execute the action. Can be from 0 to 100 where 0 means that the action will never execute and 100 means it will always execute. |

{% hint style="danger" %}
To note is that chance tags are per action. So if you have 2 action, both with a 50% chance, there won't be just 1 of the actions that execute but instead it will could be none, 1 or both.
{% endhint %}

## RGB/Hex

If you want to use RGB/Hex colors in DeluxeMenus on 1.16+ you can use the following format: "\&#aaFF00"

## Placeholders

There is one available placeholder from DeluxeMenus:

* `%deluxemenus_meta_<key>_<dataType>_<default_value>%`

## General options

### Debug

> ```yaml
> debug: BOOLEAN
> ```
>
> > **Default value:** `false`

Enables/Disables debug mode.\
Sends debug messages to the console.

### Check updates

> ```yaml
> check_updates: BOOLEAN
> ```
>
> > **Default value:** `true`

Enables/Disables checking new updates for the plugin.\
Notifies any operator if there is an update available.
