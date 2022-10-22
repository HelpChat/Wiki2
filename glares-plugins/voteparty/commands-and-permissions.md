---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Player Commands

| Command   | Permission              | Description                                   |
| --------- | ----------------------- | --------------------------------------------- |
| /vp       | none                    | Shows how many votes needed for a Vote Party. |
| /vp help  | none                    | Helpful commands for VoteParty.               |
| /vp claim | voteparty.command.claim | Claim offline voting rewards.                 |

## Admin Commands

| Command                                        | Permission              | Description                                                            |
| ---------------------------------------------- | ----------------------- | ---------------------------------------------------------------------- |
| /vp addvote \<amount>                          | voteparty.command.admin | Add votes to the current vote tally.                                   |
| /vp addvote \<player> \<silent> \<amount>      | voteparty.command.admin | Add votes to the current vote tally with some extra parameter options. |
| /vp givecrate \<player> \<amount>              | voteparty.command.admin | Supply a player with a vote crate.                                     |
| /vp checkvotes \<player> \<amount> \<timeunit> | voteparty.command.admin | Check the amount of votes a player has.                                |
| /vp totalvotes \<player>                       | voteparty.command.admin | Get the total amount of votes a player has.                            |
| /vp resetvotes \<player>                       | voteparty.command.admin | Reset the amount of votes a player has.                                |
| /vp setcounter \<amount>                       | voteparty.command.admin | Set the current vote counter.                                          |
| /vp startparty                                 | voteparty.command.admin | Force launch a Vote Party.                                             |
| /vp giveparty \<player>                        | voteparty.command.admin | Host a private Vote Party for a player.                                |
| /vp reload                                     | voteparty.command.admin | Reloads the config file.                                               |

## Permissions

| Permission              | Description                                             |
| ----------------------- | ------------------------------------------------------- |
| voteparty.command.admin | Gives access to all VoteParty commands and permissions. |
