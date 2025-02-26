---
description: >-
  Starting with Spigot (and forks such as PaperMC) 1.14, a new feature called
  Persistent Data Container (PDC) was added. This is a small document explaining
  what it is and how DeluxeMenus uses it.
---

# Meta (Metadata)

### What is it?

The Persistent Data Container is a way to store custom data on a whole range of objects; such as items, entities, and block entities. This data is persistent (DOES NOT disappear on server restart) and is stored in the server files.

DeluxeMenus uses PDC to allow menu creators to store and retrieve custom data for menu users (players). You will find this feature on the wiki usually listed as "meta" or "metadata".

### Data Types

While PDC allows storage of a wide range of data types and even allows custom implementation, DeluxeMenus only supports 3 of those types: DOUBLE, INTEGER, STRING. Some times you may see that LONG and BOOLEAN are supported as well, but these two are aliases for INTEGER (LONG) and STRING (BOOLEAN).



| Name    | Aliases | Data Type                                     |
| ------- | ------- | --------------------------------------------- |
| INTEGER | LONG    | 64 bit signed number                          |
| STRING  | BOOLEAN | String ("true" or "false" when using BOOLEAN) |
| DOUBLE  |         | Fractional number from 1.7e−308 to 1.7e+308   |



If you want a more in-depth description of PDC, we recommend this amazing post from the PaperMC team: [https://docs.papermc.io/paper/dev/pdc](https://docs.papermc.io/paper/dev/pdc)
