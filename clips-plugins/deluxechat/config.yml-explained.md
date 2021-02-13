---
description: Explanation of most options in config.yml
---

# Config.yml explained

| Option | Explanation |
| :--- | :--- |
| check\_updates | Allow plugin to check spigot for updates and announce you. |
| relation\_placeholders\_enabled | Enable PlaceholderAPI relation placeholders. |
| timestamp\_format | Sets the way time is formatted. |
| boolean | Chose what the boolean messages will look like. |
| ops\_use\_group\_format | If this option is disabled, OP players will need permissions for formats to work. |

| Chat Filter Options | Explanation |
| :--- | :--- |
| enabled | Enable or disable the chat filter option. This is to stop people from using certain words or phrases like swears. |
| ignore\_case | If this option is enabled then the filter will ignore the case for the filtered words. |
| list | List the words and phrases that will be filtered and what they will be filtered with. It works like this: `word-to-be-filtered;word-it-will-be-filtered-with` so for example `fuck;***` will replace the word fuck from chat with 3 asterisks. |

| BungeeCord Options | Explanation |
| :--- | :--- |
| enabled | Enable bungeecord option. Requires DeluxeChat on BungeeCord and backend servers. |
| server\_name | The server name that will be used for bungeecord.server\_whitelist. |
| server\_prefix | The name of the server that will be displayed when using the placeholder %server% in global chat. |
| join\_global | If this option is enabled all players will be put in the global chat when they join the server. |
| use\_server\_whitelist | This option will enable bungeecord.server\_whitelist. |
| server\_whitelist | List the servers which will have global chat linked to current serve |

