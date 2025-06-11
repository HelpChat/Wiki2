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

## RGB/Hex

If you want to use RGB/Hex colors in DeluxeMenus on 1.16+ you can use the following format: "\&#aaFF00"

## Placeholders

There is one available placeholder from DeluxeMenus:

* `%deluxemenus_meta_<key>_<dataType>_[default_value]%` - Returns the meta value that is saved with the specified key and type. If no value is saved with the given key and type, the default value is returned. If no default value is specified, an empty value is returned.
* `%deluxemenus_meta_has_value_<key>_[dataType]%` - Returns yes/no response. Checks if there is a value with the given key. It also checks the type if specified.
* `%deluxemenus_opened_menu%` - Returns the ID of the menu that the player currently has open
* `%deluxemenus_has_open_menu%` - Returns yes/no if a user has a menu opened
* `%deluxemenus_previously_opened%` - Returns the previous ID of the menu that the player had opened

## General plugin options

### Debug

> ```yaml
> debug: STRING
> ```
>
> > **Default value:** `HIGHEST`\
> > **Available values:**\
> > `LOWEST`, `LOW`, `MEDIUM`, `HIGH`, `HIGHEST`

Determines which debug messages are going to be shown in console based on their importance.

`HIGHEST` LEVEL = only debug messages with highest priority are shown\
`LOWEST` LEVEL = all debug messages are shown\
[Stacktraces](https://rollbar.com/blog/java-stack-trace) are only displayed when the debug level is set to MEDIUM, HIGH or HIGHEST.

### Check updates

> ```yaml
> check_updates: BOOLEAN
> ```
>
> > **Default value:** `true`

Enables/Disables checking new updates for the plugin.\
Notifies any operator if there is an update available.
