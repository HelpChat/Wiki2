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

{% code title="config.yml" %}
```yaml
check_updates: true
bungeecord:
  enabled: false
  server_name: Server
  server_prefix: '&8[&cServer&8]'
  join_global: true
  use_server_whitelist: true
  server_whitelist:
  - Server2
  - Server3
relation_placeholders_enabled: true
timestamp_format: MM/dd/yy HH:mm:ss
boolean:
  'true': '&atrue'
  'false': '&cfalse'
ops_use_group_format: false
chat_filter:
  enabled: false
  ignore_case: true
  list:
  - '.; '
  - fuck;fuck
private_message:
  enabled: true
  bungeecord: false
private_message_formats:
  to_sender:
    format: '&7you &e-> &7%recipient_player_name% &7:'
    tooltip:
    - '%player_name%'
    click_command: '/r '
    chat_color: '&f'
  to_recipient:
    format: '&7%player_name% &e-> &7you &7:'
    tooltip:
    - '%player_name%'
    click_command: '/r '
    chat_color: '&f'
  social_spy: '&8[&cspy&8] &f%player% &e-> &f%recipient%&7:'
formats:
  default:
    priority: 2147483647
    channel: ''
    prefix: '&7[%vault_group%&7] '
    name_color: '&b'
    name: '%player_name%'
    suffix: '&7> '
    chat_color: '&f'
    channel_tooltip:
    - ''
    prefix_tooltip:
    - '%player_name%'
    - '&bRank: %vault_group%'
    name_tooltip:
    - ''
    suffix_tooltip:
    - ''
    channel_click_command: /ranks
    prefix_click_command: /ranks
    name_click_command: '/msg %player_name% '
    suffix_click_command: ''
```
{% endcode %}

