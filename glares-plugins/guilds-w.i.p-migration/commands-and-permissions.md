---
description: Overview of all the commands in the plugin and an explanation of what they do.
---

# Commands & Permissions

Understanding how the commands work in the project is super simple. All you have to do is type `/guilds` and you will be presented with a very nice-looking help menu!

![](https://blobscdn.gitbook.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-Ljvb1saMgD8bceF8vll%2F-Lrz69CpJe5AnBwA0-lj%2F-Lrz6HlHLztXvL5sxc-5%2Fjavaw_2019-10_24-13-51-48.png?alt=media&token=b117dfcd-73a2-4aa3-9582-295bce3aeb51)

### Group Perms <a id="group-perms"></a>

To easily give a player / group access to all the correct commands, you can give the following permissions:

**Member:** guilds.group.member   
**Admin:** guilds.group.admin

### ​Aliases <a id="aliases"></a>

Since Guilds is such a big project, we knew that it can get repetitive typing out full commands each time so we have made the follow aliases work so you don't have to type everything out each time. Use whichever you want! You can configure this in the config!

## ​Action Commands <a id="action-commands"></a>

Action commands control the user's choice to proceed with some of the commands in the plugin. We know that some people get curious when playing with commands and we've designed the commands that cause bigger changes to ask for a confirmation.

`/guild cancel`   
**Permission**: guilds.command.cancel  
If a user has an active action, it will cancel it and not proceed further with what they were trying to do.

`/guild confirm`   
**Permission**: guilds.command.confirm  
If a user has an active action, it will confirm the action and continue with what they were attempting to do.

## ​Admin Commands <a id="admin-commands"></a>

Admin commands are basically self-understandable. They give you the power over how the plugin is used and can do many things to modify how the plugin works.

`/guild admin addplayer <player> <guild>`   
**Permission**: guilds.command.admin  
Allows you to put a player into a guild by force.

`/guild admin bank balance <guild>`   
**Permission**: guilds.command.admin   
Admin command to view a guild's bank balance.

`/guild admin bank deposit <guild> <amount>`   
**Permission**: guilds.command.admin   
Admin command to put money into a guild's ban.

`/guild admin bank withdraw <guild> <amount>`   
**Permission**: guilds.command.admin   
Admin command to put money into a guild's ban.

`/guild admin delhome <guild>`   
**Permission**: guilds.command.admin   
Admin command to delete the home of a guild.

`/guild admin give <player> <amount>`   
**Permission**: guilds.command.admin   
Allows you to give upgrade tickets to players.

`/guild admin home <guild>`   
**Permission**: guilds.command.admin   
Admin command to teleport to the home of a guild.   
  
`/guild admin motd <guild>`   
**Permission**: guilds.command.admin   
Allows you to view the MOTD of a guild.

`/guild admin motd remove <guild>`   
**Permission**: guilds.command.admin   
Allows you to remove the MOTD of a guild.

`/guild admin motd set <guild> <motd>`   
**Permission**: guilds.command.admin   
Allows you to set the MOTD of a guild

`/guild admin prefix <guild> <prefix>`   
**Permission**: guilds.command.admin   
Allows you to change the prefix of a guild by force.

`/guild admin remove <guild>`   
**Permission**: guilds.command.admin   
Allows you to remove a guild as a whole by force.

`/guild admin removeplayer <player>`   
**Permission**: guilds.command.admin   
Allows you to remove a player from their guild by force.

`/guild admin rename <guild> <new name>`   
**Permission**: guilds.command.admin   
Allows you change the current name of a guild by force.

`/guild admin sethome`   
**Permission**: guilds.command.admin   
Admin command to set the home of a guild.

`/guild admin spy`   
**Permission**: guilds.chat.spy   
Toggles the ability to see all guild chat.

`/guild admin status <guild>`   
**Permission**: guilds.command.admin   
Toggle the status of a guild by force.

`/guild admin transfer <guild> <new master>`   
**Permission:** guilds.command.admin   
Transfer a guild to another member by force

`/guild admin upgrade <guild>`   
**Permission**: guilds.command.admin   
Force upgrade a guild's tier.

`/guild admin vault <guild> <vault #>`   
**Permission**: guilds.command.admin   
Open any guild's vault

`/guild reload`   
**Permission**: guilds.command.admin   
Reloads the configuration files.

## ​Ally Commands <a id="ally-commands"></a>

The ally commands are a set of commands that let guild members control different actions such as listing their current allies or adding and removing them!

`/guild ally accept <guild>`   
**Permission**: guilds.command.ally.accept   
This command allows you to accept an ally invite from another guild if there is one currently pending!

`/guild ally add <guild>`   
**Permission**: guilds.command.ally.add   
This command allows you to send an ally request to another guild!

`/guild ally decline <guild>`   
**Permission**: guilds.command.ally.decline   
This command allows you to decline and incoming ally invite from another guild!

`/guild ally list`   
**Permission**: guilds.command.ally.list   
This command allows you to list all the allies of your guild!

`/guild ally remove <guild>`   
**Permission**: guilds.command.ally.remove   
This command allows you to remove any of your current allies!

## Arena Commands <a id="arena-commands"></a>

`/guild arena set challenger <arena>`   
**Permission**: guilds.command.admin   
Sets challenger side for an arena

`/guild arena create <name>`   
**Permission**: guilds.command.admin   
Create an arena

`/guild arena set defender <arena>`   
**Permission**: guilds.command.admin   
Sets defender side for an arena

`/guild arena delete <arena>`   
**Permission**: guilds.command.admin   
Delete an arena

`/guild arena list`   
**Permission**: guilds.command.admin   
Lists all arenas on the server

`/guild arena tp <arena> <side>`   
**Permission**: guilds.command.admin   
Teleport to specific side of an arena

## ​Bank Commands <a id="bank-commands"></a>

One of the cool features about this plugin is that it allows each guild to have a centralized bank that all players in a guild can work together to grow!

`/guild bank balance`   
**Permission**: guilds.command.bank.balance   
Allows you to check the current balance of your guild bank!

`/guild bank deposit <amount>`   
**Permission**: guilds.command.bank.deposit   
Allows you to put money from your balance into your guild bank!

`/guild bank withdraw <amount>`   
**Permission**: guilds.command.bank.withdraw   
Allows you to take money from your guild bank and put it back into your personal balance!

## ​Claim Commands <a id="claim-commands"></a>

Another cool feature of this plugin is the ability to make claims! This is ultilized through the WorldGuard Hook and allows players to "claim" land for their guild members to use.

`/guild claim`   
**Permission**: guilds.command.claim   
Create a guild claim surrounding you!

`/guild unclaim`   
**Permission**: guilds.command.unclaim   
Get rid of your current guild claim!

## ​Code Commands <a id="code-commands"></a>

This feature is actually a new one at the time of writing this wiki. The idea came to me when I realized I wanted to allow a group of my friends to join my guild but at the time I didn't know all their usernames. This feature allows you to create an invite code with the option of one-time-usage or multiple-uses and you can give it to anyone, then they can use that code to join the guild at any time!

`/guild code create [uses]`   
**Permission**: guilds.command.code.create   
Create an invite code for your guild that can be used by anyone!

`/guild code delete <code>`   
**Permission**: guilds.command.code.delete   
Remove an invite code from your guild

`/guild code info <code>`   
**Permission**: guilds.command.code.info   
Allows you to retrieve specific information about a guild code!

`/guild code list`   
**Permission**: guilds.command.code.list   
Allows you to list all your current guild codes!

`/guild code redeem <code>`   
**Permission**: guilds.command.code.redeem   
Allows you to redeem an invite code!

## Console Commands <a id="console-commands"></a>

These are commands that are only to be ran from console because they do important operations that typical players shouldn't be doing.

`/guild console update-languages`   
**Permission**: guilds.command.admin   
Update language files for the plugin

`/guild console backup`   
**Permission**: guilds.command.admin   
Create a backup of all plugin data

`/guild console migrate <type>`   
**Permission:** guilds.command.admin   
Migrate all the plugin data from one type of storage to another

`/guild console unclaim-all`   
**Permission:** guilds.command.admin   
Remove all claim data from the plugin

## ​GUI Commands <a id="gui-commands"></a>

`/guild buff`   
**Permission**: guilds.command.buff   
Opens the guild buff GUI.

`/guild list`   
**Permission**: guilds.command.list   
Opens the guild list GUI.

`/guild members`   
**Permission**: guilds.command.members   
Opens the member list GUI.

`/guild vault`   
**Permission**: guilds.command.vault   
Opens a guild vault GUI.

`/guild info`   
**Permission**: guilds.command.info   
Opens up the guild info GUI.

## ​Homes Commands <a id="homes-commands"></a>

`/guild delhome`   
**Permission**: guilds.command.delhome   
Delete your guild home.

`/guild home`   
**Permission**: guilds.command.home   
Teleport to your guild home.

`/guild sethome`   
**Permission**: guilds.command.sethome   
Set your guild home to your current location.

## ​Management Commands <a id="management-commands"></a>

`/guild create <name> [prefix]`   
**Permission**: guilds.command.create   
Create a new guild!

`/guild delete`   
**Permission**: guilds.command.delete   
Deletes your current guild.

`/guild kick <player>`   
**Permission**: guilds.command.kick   
Kicks a player from your guild.

`/guild prefix <prefix>`   
**Permission**: guilds.command.prefix   
Set a new prefix for your guild.

`/guild rename <name>`   
**Permission**: guilds.command.rename   
Set a new name for your guild.

`/guild status`   
**Permission**: guilds.command.status   
Toggles the status of your guild.

`/guild transfer <player>`   
**Permission**: guilds.command.transfer   
Transfer your guild to another person.

`/guild upgrade`   
**Permission**: guilds.command.upgrade   
Upgrade your guild's tier.

## ​Member Commands <a id="member-commands"></a>

Commands handled by members of the server / guild.

`/guild accept <name>`   
**Permission**: guilds.command.accept   
Accepted a guild invite from a guild.

`/guild check`   
**Permission**: guilds.command.check   
Checks to see if a user has any pending guild invites.

`/ guild decline <name>`   
**Permission**: guilds.command.decline   
Declines a pending guild invite from a guild.

`/guild demote <player>`   
**Permission**: guilds.command.demote   
Demote a player in your guild.

`/guild invite <player>`   
**Permission**: guilds.command.invite   
Invite a player to your guild.

`/guild language <language>`   
**Permission**: guilds.command.language   
Set the plugin language to your choosing!

`/guild leave`   
**Permission**: guilds.command.leave   
Leave your current guild.

`/guild promote <player>`   
**Permission**: guilds.command.promote   
Promote a player in your guild.

## ​MOTD Commands <a id="motd-commands"></a>

Commands that manage a guild's MOTD.

`/guild motd`   
**Permission**: guilds.command.motd   
View your guild's MOTD.

`/guild motd set <motd>`   
**Permission**: guilds.command.motd.modify   
Set the MOTD of your guild.

`/guild motd remove`   
**Permission**: guilds.command.motd.modify   
Remove the MOTD of your guild.

## ​Misc Commands <a id="misc-commands"></a>

Random commands that haven't been categorized yet.

`/guild chat`   
**Permission**: guilds.command.chat   
Toggles the guild chat.

`/guild request <guild>`   
**Permission**: guilds.command.request   
Send a request to join a guild.

## War Commands <a id="war-commands"></a>

`/guild war accept`   
**Permission**: guilds.command.war.accept   
Accept a war request

`/guild war challenge <guild>`   
**Permission**: guilds.command.war.challenge   
Challenge another guild to a war

`/guild war deny`   
**Permission**: guilds.command.war.deny   
Deny a war request

`/guild war join`   
**Permission**: guilds.command.war.join   
Join a guild war

