---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Player Commands

| Command | Permission | Description |
| :--- | :--- | :--- |
| /vp | none | Shows how many votes needed for a Vote Party. |
| /vp help | none | Helpful commands for VoteParty. |

## Admin Commands

| Command | Permission | Description |
| :--- | :--- | :--- |
| /vp addvote &lt;amount&gt; | voteparty.command.admin | Add votes to the current vote tally. |
| /vp givecrate &lt;player&gt; &lt;amount&gt; | voteparty.command.admin | Supply a player with a vote crate. |
| /vp checkvotes &lt;player&gt; &lt;amount&gt; &lt;timeunit&gt; | voteparty.command.admin | Check the amount of votes a player has. |
| /vp totalvotes &lt;player&gt; | voteparty.command.admin | Get the total amount of votes a player has. |
| /vp resetvotes &lt;player&gt; | voteparty.command.admin | Reset the amount of votes a player has. |
| /vp setcounter &lt;amount&gt; | voteparty.command.admin | Set the current vote counter. |
| /vp startparty | voteparty.command.admin | Force launch a Vote Party. |
| /vp giveparty &lt;player&gt; | voteparty.command.admin | Host a private Vote Party for a player. |
| /vp reload | voteparty.command.admin | Reloads the config file. |

## Permissions

| Permission | Description |
| :--- | :--- |
| voteparty.command.admin | Gives access to all VoteParty commands and permissions. |

