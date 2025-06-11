---
description: >-
  Starting with Spigot (and forks such as PaperMC) 1.14, a new feature called
  Persistent Data Container (PDC) was added. This is a small document explaining
  what it is and how DeluxeMenus uses it.
---

# Meta (Metadata)

### What is it?

The Persistent Data Container is a way to store custom data on a whole range of objects; such as items, entities, and block entities. This data is persistent (DOES NOT disappear on server restart) and is stored in the server files.

DeluxeMenus uses PDC to allow menu creators to store and retrieve custom data for menu users (players). You will find this feature on the wiki usually listed under the names "meta" or "metadata".

### Data Types

While PDC allows storage of a wide range of data types and even allows custom implementation, DeluxeMenus only supports 3 of those types: DOUBLE, INTEGER, STRING. Some times you may see that LONG and BOOLEAN are supported as well, but these two are aliases for INTEGER (LONG) and STRING (BOOLEAN).

| Name    | Aliases | Data Type                                     |
| ------- | ------- | --------------------------------------------- |
| INTEGER | LONG    | 64 bit signed number                          |
| STRING  | BOOLEAN | String ("true" or "false" when using BOOLEAN) |
| DOUBLE  |         | Fractional number from 1.7e−308 to 1.7e+308   |

### How to use it?

Setting a value is pretty easy:

1. You can use the `[meta]` action which you can read more about [here](actions.md#actions-types).
2. You can use the `/dm meta <player> <set/remove/add/subtract/switch>` command which you can read more about [here](../../../clips-plugins/deluxemenus/commands-and-permissions.md#meta-commands).

Retrieving a value is just as easy:

1. You can use the PlaceholderAPI placeholder `%deluxemenus_meta_<key>_<data-type>_[default_value]%`.
2. You can use the `/dm meta <player> show <key> <type>` to see a single value with specified key and type.
3. You can use the `/dm meta <player> list <type> [page]` to see a list of all values of one type.

Checking that the player has a value is no harder:

1. You can use the PlaceholderAPI placeholder `%deluxemenus_meta_has_<key>_[data-type]%`.
2. You can use the `has meta` requirement which you can read more about [here](../../../clips-plugins/deluxemenus/options-and-configurations/requirements.md#has-meta).

### What else must I know?

* Values are stored with a prefix (namespace) even if you don't set one. If you don't specify a namespace, `deluxemenus:` is used.
* Keys (including namespaces) are **case-insensitive**. This means that `my_key` will work the same as `MY_Key` and `MY_KEY`.

If you want a more in-depth description of PDC, we recommend this amazing post from the PaperMC team: [https://docs.papermc.io/paper/dev/pdc](https://docs.papermc.io/paper/dev/pdc)
