---
description: Few examples to help you make your own!
---

# Example GUI menus

## [**Kits**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/kits.yml)

A simple example to show you how you can make a Kits menu that displays 3 different items for each kit, when the kit is available to claim, when it's on cooldown and when it's unavailable \(Locked\).  
  
To make this work fine you have to download [Essentials](https://ci.ender.zone/job/EssentialsX/lastSuccessfulBuild/) and download the Essentials expansion using:

> /papi ecloud download Essentials  
> /papi reload

## [**Mines**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/mines.yml)

A simple example to show you how you can make a Mines menu that displays 3 items for each mine, when the mine is unlocked, when it's the current mine and when it's locked.  
  
To make this work fine you have to download [EzRanksPro](https://www.spigotmc.org/resources/10731/) and download Player and EzRanksPro expansions using:

> /papi ecloud download Player  
> /papi ecloud download EzRanksPro  
> /papi reload

## [**Server Selector**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/serverselector.yml)

A simple example to show you how you can make a Server Selector menu that displays 2 different items for each server, when the server is online and when it's offline.  
  
To make this work fine you have to download Pinger and \(optional\) Server expansions using:

> /papi ecloud download Pinger  
> /papi ecloud download Server  
> /papi reload

In this example, we have 2 different servers on one BungeeCord: **vanilla** and **games**. We are on the server **games** in this example.

If we want the player to connect to the **vanilla** server, we need to setup the right functions in the `left_click_commands:` ****section   
In our example, we will first close the menu with `[close]`, send a message to the player with `[message]` and finally connect him to the server with `[connect]`.

To show, how many players are on the server vanilla, we will use the placeholder **%pinger\_players\_&lt;ip&gt;:&lt;port&gt;%**  
Please keep in mind, that Pinger placeholders have their own update interval, to change it, go to the PlaceholderAPI config file and change the `check_interval:` \(default is 30 seconds\).  
But what if the server is currently offline?  
In this case, we can use a second item with a lower priority, that will be displayed, if the `view_requirement:` of the first item isn't true.  
So now we can show a different item, if the server is offline. But keep in mind that the items don't update automatically, if the view requirement has changed \(from Offline to Online\). We can update the menu, by letting the player execute `[refresh]` if he clicks on the item.

The second item is easier. Because we are already connected, so we just need to send a message. And we can show the amount of players on the server with the **%server\_online%** placeholder.

## [**Store**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml)

A simple example to show you how you can make a Store/Shop menu that you can buy/sell items from using various economic systems.  
  
To make this work fine you have to download the Player and CheckItem expansions and the expansion of the economic system that you'll use using:

> /papi ecloud download Player  
> /papi ecloud download CheckItem  
> /papi ecloud download Vault  
> /papi ecloud download TokenEnchant  
> /papi ecloud download PlayerPoints  
> /papi reload

* [x] \*\*\*\*[**Vault**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L18-L59)\*\*\*\*
* [x] \*\*\*\*[**Token Enchant**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L61-L106)\*\*\*\*
* [x] \*\*\*\*[**Player Points**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L108-L150)\*\*\*\*
* [x] [**Player XP**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/store.yml#L152-L195)\*\*\*\*


## [**Meta**](https://github.com/help-chat/DeluxeMenus/blob/master/gui_menus/meta.yml)

A simple example to show you how [meta](options-and-configurations/#actions-types) works.
