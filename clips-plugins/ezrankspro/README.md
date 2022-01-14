---
description: The most customizable /rankup plugin
---

# EzRanksPro

![](<../../.gitbook/assets/Title (5).png>)

## Description

EzRanksPro allows users to rank-up the easy way, with a very flexible and extremely customizable rank-up system built for server owners by server owners. The config requires minimal effort an is a quick and simple setup.

## Setup

To give a player or group access to a rankup, they need access to the permission node associated with it! Without it EZRanksPro does not know what rankup they have access to. If you create a rankup for rank A to B, you will need to give the A rank the permission node: `ezranks.rank.A`. This will tell EZRanksPro that players in A should have the rankup associated with A. Players can have access to multiple `ezranks.rank.` permission nodes, the highest order rankup will always be applied for the player.

For a player to be considered the last rank, they need to have the permission node: `ezranks.lastrank` This tells EZRanksPro that the player is at the last rank and has no more rankups available.

Inside of your rankups.yml you will see a section with each rankup named rankup\_actions. In this section you may list many actions that the plugin will perform when a player ranks up. The format for actions are:

&#x20;\-'\<action> \<arguments>'

You must include required arguments :

&#x20;\<required>, (optional)

You may delay any rankup action by ending the action String with  example:&#x20;

\-'\[consolecommand] eco give %player% 100 '

### Rankup action list

* \[consolecommand]  - perform a console command
* \[playercommand]  - make the player perform a command
* \[message]  - send the player a message
* \[broadcast]  - send the server a message
* \[jsonmessage]  - send the player a json message
* \[jsonbroadcast]  - send the server a json message
* \[actionbarmessage]  - send the player an actionbar message
* \[actionbarbroadcast]  - send the server an actionbar message
* \[addgroup]  (world) - add the player to a permissions group
* \[removegroup]  (world) - remove the player from a permissions group
* \[addpermission]  (world) - add a permission node to the player
* \[removepermission]  (world) - remove a permission node from a player
* \[setprefix]  - set the players prefix
* \[setsuffix]  - set the players suffix
* \[effect]  - play an effect at the players location
* \[sound]    - play a sound at the players location

### Placeholders list

Placeholders can be used in your rankup actions and messages. Placeholders list:

* %player% - players name
* %displayname% - players displayname
* %world% - players current world
* %rank% - players current rank
* %rankup% - players next rank (if they have one)
* %cost% - cost to rankup
* %cost\_formatted% - formatted cost to rankup
* %balance% - players balance
* %balance\_formatted% - players formatted balance
* %difference% - amount still needed
* %difference\_formatted% - formatted amount still needed
* %progress% - rounded % of rankup cost obtained
* %progressexact% - exact % of rankup cost obtained
* %rankprefix% - players current rank prefix defined in this file
* %rankupprefix% - players next rank prefix defined in this file
* %lastrank% - last rank available
* %lastrankprefix% - last rank available prefix
* %rankup\_cost\_% - show the cost for a specific rank
* %rankup\_cost\_formatted\_% - show the formatted cost for a specific rank
* %rankup\_is\_completed\_% - show if a player has completed the specified rank
