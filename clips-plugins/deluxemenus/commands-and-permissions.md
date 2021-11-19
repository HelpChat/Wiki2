---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

{% hint style="info" %}
"/dm open" is meant to be an admin command. its not what players should use to open menus. instead you should set up "[open\_command](options-and-configurations/gui.md#open-command)"s for each menu.
{% endhint %}

## Commands

| **Command**                             | **Permission**              | Description                                                                                                                                                             |
| --------------------------------------- | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /dm                                     | -                           | Displays some info about the plugin.                                                                                                                                    |
| /dm open \<menu>                        | deluxemenus.open            | Opens the specified menu.                                                                                                                                               |
| /dm open \<menu> \<player>              | deluxemenus.open.others     | Opens the specified menu to the specified player.                                                                                                                       |
| /dm open \<menu> -p:\<target>           | deluxemenus.placeholdersfor | Opens the specified menu for you, but the placeholders in it will be parsed as the specified target.                                                                    |
| /dm open \<menu> \<viewer> -p:\<target> | deluxemenus.placeldersfor   | Opens the specified menu to the specified player but the placeholders in it will be parsed as the specified target.                                                     |
| /dm list                                | deluxemenus.list            | Lists loaded menus.                                                                                                                                                     |
| /dm execute \<player> \<action>         | Player needs to be Op       | Executes any action for a player. Check out the [Action Type](https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations#actions-types) for more info. |
| /dm reload                              | deluxemenus.reload          | Reloads the plugin's files.                                                                                                                                             |
| /dm reload \<menu>                      | deluxemenus.reload          | Reload a menu.                                                                                                                                                          |

### Command Aliases

* /deluxemenus
* /deluxemenu
* /dmenu

## Permissions

| Permission                                 | Description                                                                     |
| ------------------------------------------ | ------------------------------------------------------------------------------- |
| deluxemenus.openrequirement.bypass.\*      | Bypasses open requirements for every menu.                                      |
| deluxemenus.openrequirement.bypass.\<menu> | Bypasses open requirements for a specified menu                                 |
| deluxemenus.placeholdersfor.exempt         | Blocks other players from using you in this command `/DM Open <Menu> -p:<You>`. |

{% hint style="info" %}
All text between the less-than and greater-than signs (**<>**) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs (**<>**).
{% endhint %}
