---
description: >-
  Actions, also known as commands are the muscles of menus. They are used as
  interactions for clicks, requirement denies and requirement successes.
---

# Actions

## Actions types

The full list of actions is as follows:

| Tag                                                            | Description                                                                                                                                                                                                                                      |
| -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `[player] <command>`                                           | Executes a command as the player.                                                                                                                                                                                                                |
| `[console] <command>`                                          | Executes a command from the console.                                                                                                                                                                                                             |
| `[commandevent] <command>`                                     | <p>Executes an unregistered command as the player.<br><br>IMPORTANT: Currently, this action is simply an alias for the [player] action.</p>                                                                                                      |
| `[placeholder] <papi-placeholders>`                            | <p>Parse placeholders for a player without any chat or console output from DeluxeMenus.<br><br>IMPORTANT: If the placeholders have output, it is not hidden!</p>                                                                                 |
| `[message] <text>`                                             | Sends a message to the player. You can use [placeholders](https://helpch.at/placeholders) and color/format codes here.                                                                                                                           |
| `[broadcast] <text>`                                           | <p>Sends a message to everyone online including the console.</p><p>You can use <a href="https://helpch.at/placeholders">placeholders</a> and color/format codes here.</p>                                                                        |
| `[minimessage] <text>`                                         | Sends a message to a player using the more modern [MiniMessage](https://docs.adventure.kyori.net/minimessage/format.html) format!                                                                                                                |
| `[minibroadcast] <text>`                                       | Sends a message to everyone online using the more modern [MiniMessage](https://docs.adventure.kyori.net/minimessage/format.html) format!                                                                                                         |
| `[openguimenu] <menu-name>`                                    | Opens another GUI from DeluxeMenus.                                                                                                                                                                                                              |
| `[connect] <server-name>`                                      | <p>Connects the player to a server on the same BungeeCord.<br><br>IMPORTANT: Requires BungeeMessaging. This is present on BungeeCord and WaterFall. On Velocity it might be disabled by default. Check your proxy config.</p>                    |
| `[close]`                                                      | Closes the currently opened GUI.                                                                                                                                                                                                                 |
| `[json] <JSON-text>`                                           | Send a json message to the player. Use [this](https://minecraftjson.com/) website to easily generate the JSON text.                                                                                                                              |
| `[jsonbroadcast] <JSON-text>`                                  | Send a json message to everyone online. Use [this](https://minecraftjson.com/) website to easily generate the JSON text.                                                                                                                         |
| `[refresh]`                                                    | Refresh items in the current menu view. This updates the shown Items themselves.                                                                                                                                                                 |
| `[broadcastsound] <sound> <volume> <pitch>`                    | Broadcast a sound to all players on the server.                                                                                                                                                                                                  |
| `[broadcastsoundworld] <sound> <volume> <pitch>`               | Broadcast a sound to all players in the world.                                                                                                                                                                                                   |
| `[sound] <sound> <volume> <pitch>`                             | Play a sound for the player.                                                                                                                                                                                                                     |
| `[takemoney] <amount>`                                         | Take a certain amount of money from the player. [Vault](https://www.spigotmc.org/resources/34315/) is required for this action to work.                                                                                                          |
| `[givemoney] <amount>`                                         | Give a certain amount of money to the player. [Vault](https://www.spigotmc.org/resources/34315/) is required for this action to work.(requires Vault)                                                                                            |
| `[takeexp] #L`                                                 | Take a certain amount of exp levels or points from a player. To give levels, add `L` at the end, otherwise remove it.                                                                                                                            |
| `[giveexp] #L`                                                 | Give a certain amount of exp levels or points to a player. To give levels, add `L` at the end, otherwise remove it                                                                                                                               |
| `[givepermission] <perm.node>`                                 | Giv a permission to a player. [Vault](https://www.spigotmc.org/resources/vault.34315/) is required for this action to work.                                                                                                                      |
| `[takepermission] <perm.node>`                                 | Take a permission from a player. [Vault](https://www.spigotmc.org/resources/vault.34315/) is required for this action work.                                                                                                                      |
| `[meta] <set/remove/add/subtract/switch> <key> <type> <value>` | Modifies the player's meta. `add/subtract` are for number types. `switch` is for boolean, it will swap it from true/false. Check [here](../../../clips-plugins/deluxemenus/options-and-configurations/requirements.md#has-meta) for more detail. |
| `[chat] <message>`                                             | Send a message in chat as the player who this action got executed for.                                                                                                                                                                           |

### **Action tags**

These tags can be added with the action (e.g. `- '[message] example<delay=20>'`).

<table data-header-hidden><thead><tr><th width="374">Tag</th><th>Description</th></tr></thead><tbody><tr><td>Tag</td><td>Description</td></tr><tr><td><code>&#x3C;delay=&#x3C;time>></code></td><td>Executes the action after the specified delay (in ticks, 20 ticks = 1 second).</td></tr><tr><td><code>&#x3C;chance=&#x3C;chance>></code></td><td>Sets a chance to execute the action. Can be from 0 to 100 where 0 means that the action will never execute and 100 means it will always execute.</td></tr></tbody></table>

{% hint style="danger" %}
To note is that chance tags are per action. So if you have 2 action, both with a 50% chance, there won't be just 1 of the actions that execute but instead it will could be none, 1 or both.
{% endhint %}
