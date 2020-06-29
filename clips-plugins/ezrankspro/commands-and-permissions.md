---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Player commands

| Command | Permission | Description |
| :--- | :--- | :--- |
|  /rankup | ezranks.rankup | Attempt to rankup from your current rank |
| /ranks | ezranks.listranks | View the current server ranks list with prices! |
| /autorankup | ezranks.autorankup | Toggle autorankup on or off |

## Admin commands

| Command | Permission | Description |
| :--- | :--- | :--- |
| /ezadmin | ezranks.admin | View plugin version |
| /ezadmin help | ezranks.admin | Admin Help Menu |
| /ezadmin createrankup &lt;rankFrom&gt; &lt;rankTo&gt; &lt;cost&gt; | ezranks.admin | Create and load default rankup section inside of the rankups.yml for the specific rankup specified in command. |
| /ezadmin deleterankup &lt;rankFrom&gt; | ezranks.admin | Delete an active rankup from memory and the rankups.yml |
| /ezadmin list | ezranks.admin | List all/rank specific rankups |
| /ezadmin info &lt;rankFrom&gt; &lt;rankTo&gt; | ezranks.admin | View detailed information about a specific rankup. |
| /ezadmin forcerankup &lt;player&gt; | ezranks.admin | Force a player to rankup at no cost |
| /ezadmin reload | ezranks.admin | Reload config/rankups.yml |

**Commands aliases**

* **/rankup:** /ezru, /ru, /ezr, /promote
* **/ranks:** /rankslist
* **/autorankup:** /arankup

## Permissions

| Permission | Description |
| :--- | :--- |
| ezranks.rank.&lt;rank&gt; | Tells EZRanksPro what rank the player is at |
| ezranks.lastrank | This tells EZRanksPro that the player is at the last rank and has no more rankups available |
| ezranks.cooldown.bypass | Allows players to bypass the rankup cooldown if it is enabled |
| ezranks.admin | Grants access to all the admin related commands |

