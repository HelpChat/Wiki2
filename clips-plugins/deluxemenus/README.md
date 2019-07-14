# DeluxeMenus

## Options & Configurations

The page is divided into 2 sections, [**GUI**](https://github.com/help-chat/DeluxeMenus/wiki/gui) options and then [**Item**](https://github.com/help-chat/DeluxeMenus/wiki/item) options. GUI options are what comes first in the configuration, and the Item options are for any items defined underneath the **"items:"** section of the GUI config.

* [Placeholders](https://github.com/PlaceholderAPI/PlaceholderAPI/wiki/Placeholders)
* Materials:
  * [1.8.8](https://helpch.at/docs/1.8.8/org/bukkit/Material.html)
  * [1.12.2](https://helpch.at/docs/1.12.2/org/bukkit/Material.html)
  * [1.13.2](https://helpch.at/docs/1.13.2/org/bukkit/Material.html)
  * [Latest](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
* [Enchantments](https://helpch.at/docs/1.12.2/org/bukkit/enchantments/Enchantment.html) \(Be aware that some enchantments are not available on some items.\)
* [Dye Colors](https://helpch.at/docs/1.12.2/org/bukkit/DyeColor.html)
* [Pattern Types](https://helpch.at/docs/1.12.2/org/bukkit/block/banner/PatternType.html)
* [Sound Types](https://gist.github.com/Andre601/1ab3b4fabd0010ae241156333491c379) 

| **Type** | **Description** |
| :--- | :--- |
| **TEXT** | Replace this with any text. Check the description to find out if you can use color/formatting codes. |
| **BOOLEAN** | Replace this with true or false \(If used with PlaceholderAPI for view\_requirements this may be yes/no instead of true/false \[This is the default configuration for PlaceholderAPI\]\). |
| **EXPRESSION** | A java/placeholder expression/comparison. See this page for more information. |
| **\#** | Replace this with a number. Check the description to see if there are limits. |
| **SOUND** | Replace this with the sound name. |
| **COMMAND** | Replace this with the command you want without slash "/" |
|  |  |

| **Command** | **Permission** | **Default** |
| :--- | :--- | :--- |
| /dm | - | yes |
| /dm open \ | deluxemenus.open | yes |
| /dm list | deluxemenus.list | no |
| /dm reload | deluxemenus.reload | no |
| /dm open \ \ | deluxemenus.open.others | no |

## Example GUI Menus

* [**Kits**](/help-chat/DeluxeMenus/blob/master/gui_menus/kits.yml)

To make this work fine you have to download [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/), [Essentials](https://ci.ender.zone/job/EssentialsX/lastSuccessfulBuild/) and download the Essentials expansion using:

> /papi ecloud download Essentials  
> /papi reload

* [**Mines**](/help-chat/DeluxeMenus/blob/master/gui_menus/mines.yml)

Here I show a ranks example that was created by [@clip](https://github.com/extendedclip) and I am now bringing it live \(with a few modest changes\). This mines gui requires [EZRanksPro](https://www.spigotmc.org/resources/ezrankspro.10731/) in order to function properly, of course you can still edit what you need to. Hope you enjoy.

To make this work fine you have to download [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) and download the Player, EzRanksPro expansions using:

> /papi ecloud download Player  
> /papi ecloud download EzRanksPro  
> /papi reload

* [**Server Selector**](/help-chat/DeluxeMenus/blob/master/gui_menus/serverselector.yml)

To make this work fine you have to download [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) and download the Pinger and \(optional\) Server expansion using:

> /papi ecloud download Pinger  
> /papi ecloud download Server  
> /papi reload

In this example, we have 2 different servers on one BungeeCord: **vanilla** and **games**. We are on the server **games** in this example.

If we now want, that the player should be able to connect to the server vanilla, we need to setup the right functions in the section **left\_click\_commands:**  
In our example, we will first close the menu with **\[close\]**, send a message to the viewer of the menu with **\[message\]** and finally connect to the server with **\[connect\]**.  
You can use the name of the server, that you set in the config of your BungeeCord.

To show, how many players are on the server vanilla, we will use the placeholder **%pinger**_**players**_**\:\%**  
You can use the name you set in the config of the BungeeCord, or just use the IP with the port.  
Please keep in mind, that the updateinterval of the pinger-placeholders are different from the other placeholder.  
To change the updateinterval, go to the PlaceholderAPI-folder and change the interval \(default is 30\) in the config.  
But what if the server is currently offline?  
In this case, we can use a second item with a lower priority, that will be displayed, if the **view\_requirement:** of the first item aren't true.  
So now we can show a different item, if the server is offline. But we have still one problem. DeluxeMenu doesn't update the item by itself, if the view\_requirement have changed \(from Offline to Online\).  
We can fix that, by let the player execute **\[refresh\]**, if he clicks on the item.

The second item is easier. Because we are already connected, we just need to send a message. And we can show the amount of players on the server with the **%server\_online%** placeholder.

* [**Store**](/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml)

To make this work fine you have to download [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) and download the Player expansion using:

> /papi ecloud download CheckItem \# needed  
> /papi ecloud download Player \# needed  
> /papi ecloud download TokenEnchant \# optional  
> /papi ecloud download PlayerPoints \# optional  
> /papi reload
>
> * [x] [**Vault**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L4)
> * [x] [**Token Enchant**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L38)
> * [x] [**Player Points**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L73)

