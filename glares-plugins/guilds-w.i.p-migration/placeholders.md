---
description: Guild's placeholders
---

# Placeholders

**Guilds** provides placeholders in various forms to support different APIs.

### [PlaceholderAPI](https://placeholderapi.com), [MVdWPlaceholderAPI](https://www.spigotmc.org/resources/11182/), and [EssentialsXChat](https://www.spigotmc.org/resources/9089/)

**Note:** For MVdWPlaceholderAPI, in order to ensure they all stay up-to-date with each other, we just hook into regular PlaceholderAPI. This means that PlaceholderAPI is **also** required.

**EssentialsX Example:**   
\(Make sure you enabled the hook in the config and reboot for this to work\)

```yaml
format: '<{GUILD} {DISPLAYNAME}> {MESSAGE}'
```

| PlaceholderAPI | MVdWPlaceholderAPI | EssentialsXChat |
| :--- | :--- | :--- |
| %guilds\_name% | {placeholderapi\_guilds\_name} | {GUILD} |
| %guilds\_master% | {placeholderapi\_guilds\_master} | {GUILD\_MASTER} |
| %guilds\_member\_count% | {placeholderapi\_guilds\_member\_count} | {GUILD\_MEMBER\_COUNT} |
| %guilds\_prefix% | {placeholderapi\_guilds\_prefix} | {GUILD\_PREFIX} |
| %guilds\_members\_online% | {placeholderapi\_guilds\_members\_online} | {GUILD\_MEMBERS\_ONLINE} |
| %guilds\_status% | {placeholderapi\_guilds\_status} | {GUILD\_STATUS} |
| %guilds\_role% | {placeholderapi\_guilds\_role} | {GUILD\_ROLE} |
| %guilds\_tier% | {placeholderapi\_guilds\_tier} |  |
| %guilds\_balance% | {placeholderapi\_guilds\_balance} |  |
| %guilds\_tier\_name% | {placeholderapi\_guilds\_tier\_name} |  |
| %guilds\_role\_node% | {placeholderapi\_guilds\_role\_node} |  |
| %guilds\_id% | {placeholderapi\_guilds\_id} |  |
| %guilds\_code\_amount% | {placeholderapi\_guilds\_code\_amount} |  |
| %guilds\_max\_members% | {placeholderapi\_guilds\_max\_members} |  |
| %guilds\_max\_balance% | {placeholderapi\_guilds\_max\_blanace} |  |
| %guilds\_formatted% | {placeholderapi\_guilds\_formatted} | {GUILD\_FORMATTED} |
| %guilds\_challenge\_wins% | {placeholderapi\_guilds\_challenge\_wins} | {GUILD\_CHALLENGE\_WINS} |
| %guilds\_challenge\_loses% | {placeholderapi\_guilds\_challenge\_loses} | {GUILD\_CHALLENGE\_LOSES} |
| %guilds\_motd% | {placeholderapi\_guilds\_motd} |  |



