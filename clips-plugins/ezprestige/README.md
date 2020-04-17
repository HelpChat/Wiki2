---
description: Let players /prestige the EZ way
---

# EzPrestige

## Description

## Description

Keep it going! **EZPrestige** gives you the ability to add prestige levels to your server's rank up system, where players can start over as a prestige player when they reach a certain rank.

**EzPrestige** gives players the ability to prestige using /prestige. Features plenty of configurable requirements for prestiging, as well as placeholders to display the prestige info such as prefix, next prestige and much more.

## Features

## Features

* Ability to create unlimited prestige levels!
* Highly customizable.
* Built-in GUI to display all prestige levels.
* An option to confirm before upgrading to the next prestige level.
* Supports any chat plugin to display the prestige level!
* Supports any rank up system/plugin.
* Ability for players to prestige
* Highly customizable.
* Placeholders to display prestige info
* Compatible with rankup plugins \(EzRanksPro, etc\)
* Permission based

## Dependencies

## Setup

**EZPrestige** requires any rank up system/plugin to work properly and fulfill its purpose.

### DeluxeChat

## Setup

* To display the prestige tag within your deluxechat chat format, use the placeholder provided by the ezprestige expansion
* download the expansion using /papi ecloud download ezprestige \(make sure to reload PlaceholderAPI afterwards\)
* set the prestige placeholder `%ezprestige_prestige%` within your format
* Other placeholders \([https://api.extendedclip.com/expansions/ezprestige/](https://api.extendedclip.com/expansions/ezprestige/)\)

1. Put the **EZPrestige jar** file you downloaded in your **plugins** folder.
2. Download a rank up plugin \(such as [**EZRanksPro**](https://www.spigotmc.org/resources/10731/)\) or set up your own.
3. Restart the server.
4. Modify the **config.yml** file that was generated to fit your server's layout \(File path: `/plugins/EZPrestige/`\).
5. Create your prestige levels in **prestiges.yml** file. Don't forget to give the players the prestige permission \(`ezprestige.prestige.<Prestige Number>`\) in the `prestige_commands` section!
6. Reload **EZPrestige** `/prestige reload`.
7. Check the [Commands & Permissions](commands-and-permissions.md) page, to give players access to the commands you want them to use.
8. And you're done!

### Essentials Chat

* If you are using Essentials Chat you will need to do the following
* Open the Essentials config and find the EssentialsChat section
* Place the prestige placeholder for essentials chat `{prestige}` inside the format

### Useful Guides

* [koz4christ - Minecraft Server Admin Guide](https://www.youtube.com/watch?time_continue=2&v=ZMFpLnxRGW0&feature=emb_logo)

