---
description: The most customizable /rankup plugin
---

# EzRanksPro

![](../../.gitbook/assets/title%20%285%29.png)

## Description

EzRanksPro allows users to rank-up the easy way, with a very flexible and extremely customizable rank-up system built for server owners by server owners. The config requires minimal effort an is a quick and simple setup.

## Setup

To give a player or group access to a rankup, they need access to the permission node associated with it! Without it EZRanksPro does not know what rankup they have access to. If you create a rankup for rank A to B, you will need to give the A rank the permission node: ezranks.rank.A. This will tell EZRanksPro that players in A should have the rankup associated with A. Players can have access to multiple ezranks.rank.<rank> permission nodes, the highest order rankup will always be applied for the player.

For a player to be considered the last rank, they need to have the permission node: ezranks.lastrank
This tells EZRanksPro that the player is at the last rank and has no more rankups available.

Inside of your rankups.yml you will see a section with each rankup named rankup_actions.
In this section you may list many actions that the plugin will perform when a player ranks up. The format for actions are:
- '<action> <arguments>'

You must include required arguments
<required>, (optional)

You may delay any rankup action by ending the action String with <delay=(time in seconds)>
example:
- '[consolecommand] eco give %player% 100 <delay=10>'

# Rankup action list

* [consolecommand] <command> - perform a console command
* [playercommand] <command> - make the player perform a command
* [message] <message> - send the player a message
* [broadcast] <message> - send the server a message
* [jsonmessage] <json> - send the player a json message
* [jsonbroadcast] <json> - send the server a json message
* [actionbarmessage] <message> - send the player an actionbar message
* [actionbarbroadcast] <message> - send the server an actionbar message
* [addgroup] <group> (world) - add the player to a permissions group
* [removegroup] <group> (world) - remove the player from a permissions group
* [addpermission] <permission> (world) - add a permission node to the player
* [removepermission] <permission> (world) - remove a permission node from a player
* [setprefix] <prefix> - set the players prefix
* [setsuffix] <suffix> - set the players suffix
* [effect] <effect> - play an effect at the players location
* [sound] <sound> <volume> <pitch> - play a sound at the players location

# Placeholders list

* %player% - players name
* %displayname% - players displayname
* %world% - players current world
* %rank% - players current rank
* %rankup% - players next rank (if they have one)
* %cost% - cost to rankup
* %cost_formatted% - formatted cost to rankup
* * %balance% - players balance
* %balance_formatted% - players formatted balance
* %difference% - amount still needed
* %difference_formatted% - formatted amount still needed
* %progress% - rounded % of rankup cost obtained
* %progressexact% - exact % of rankup cost obtained
* %rankprefix% - players current rank prefix defined in this file
* %rankupprefix% - players next rank prefix defined in this file
* %lastrank% - last rank available
* %lastrankprefix% - last rank available prefix
* %rankup_cost_<rankname>% - show the cost for a specific rank
* %rankup_cost_formatted_<rankname>% - show the formatted cost for a specific rank
* %rankup_is_completed_<rankname>% - show if a player has completed the specified rank
