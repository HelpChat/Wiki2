---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

{% hint style="info" %}
"/dm open" is meant to be an admin command. its not what players should use to open menus. instead you should set up "[open\_command](options-and-configurations/gui.md#open-command)"s for each menu.
{% endhint %}

## Admin Commands

| **Command**                             | **Permission**              | Description                                                                                                                                                             |
| --------------------------------------- | --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /dm                                     | -                           | Displays some info about the plugin.                                                                                                                                    |
| /dm open \<menu>                        | deluxemenus.open            | Opens the specified menu.                                                                                                                                               |
| /dm open \<menu> \<player>              | deluxemenus.open.others     | Opens the specified menu to the specified player.                                                                                                                       |
| /dm open \<menu> -p:\<target>           | deluxemenus.placeholdersfor | Opens the specified menu for you, but the placeholders in it will be parsed as the specified target.                                                                    |
| /dm open \<menu> \<viewer> -p:\<target> | deluxemenus.placeholdersfor | Opens the specified menu to the specified player but the placeholders in it will be parsed as the specified target.                                                     |
| /dm list \[page/all]                    | deluxemenus.list            | Lists loaded menus.                                                                                                                                                     |
| /dm execute \<player> \<action>         | Player needs to be Op       | Executes any action for a player. Check out the [Action Type](https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations#actions-types) for more info. |
| /dm dump \<menu-name>                   | deluxemenus.admin           | Create a paste bin with the menu and also some other important debugging stuff like server version and java version.                                                    |
| /dm dump config                         | deluxemenus.admin           | Create a paste bin with the config.yml and some other important debugging stuff such as server version and java version                                                 |
| /dm reload                              | deluxemenus.reload          | Reloads the plugin's files.                                                                                                                                             |
| /dm reload \<menu>                      | deluxemenus.reload          | Reload a menu.                                                                                                                                                          |

### Meta Commands

{% hint style="info" %}
"/dm open" is meant to be an admin command. its not what players should use to open menus. instead you should set up "[open\_command](options-and-configurations/gui.md#open-command)"s for each menu.
{% endhint %}

## Admin Commands

| **Command**                                         | **Permission**        | Description                                                                                                                                                                                                                                                                                                                  |
| --------------------------------------------------- | --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| /dm meta \<player> list \<type> \[page]             | Player needs to be Op | See a full list of meta values of given type for specified player.                                                                                                                                                                                                                                                           |
| /dm meta \<player> show \<key> \<type>              | Player needs to be Op | See the value of a specific meta key and type for specified player.                                                                                                                                                                                                                                                          |
| /dm meta \<playe> set \<key> \<type> \<value>       | Player needs to be Op | Set a new value of given type at given key for specified player. If a value already exists and is of same type, it will be overwritten. If a value exists and is of different type, the action will fail.                                                                                                                    |
| /dm meta \<player> remove \<key> \<type> \<value>   | Player needs to be Op | Remove the value of given type at given key for specified player. If the existent value is of different type, the action will fail. If there is no value, the action will fail.                                                                                                                                              |
| /dm meta \<player> switch \<key>                    | Player needs to be Op | Switches the value of a BOOLEAN type at given key for specified player. If no value exist at keys or the value is not of type BOOLEAN, the action will fail.                                                                                                                                                                 |
| /dm meta \<player> add \<key> \<type> \<value>      | Player needs to be Op | Adds the specified value to the value existent at given key for specified player. If no value exists at given key, the specified value is set. If value is not number type (DOUBLE, LONG, INTEGER), the action will fail. If the value is a natural number but added value is not, it will be rounded down.                  |
| /dm meta \<player> subtract \<key> \<type> \<value> | Player needs to be Op | Subtracts the specified value to the value existent at given key for specified player. If no value exists at given key, the negative of specified value is set. If value is not number type (DOUBLE, LONG, INTEGER), the action will fail. If the value is a natural number but added value is not, it will be rounded down. |

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
