---
description: The plugin's configuration files
---

# Plugin's files

## Config

{% code title="config.yml" %}
```yaml
# DeluxeChat version 1.15.0 config file
# Created by extended_clip
# List as many format configurations you in the formats: config section.
# Each format configuration requires a specific layout which can be seen below.
# Format priority must be specified per format and each priority must be unique.
# higher value = lower priority
# ex: guest-100, owner-1
#   YOU MUST KEEP A 'default' TEMPLATE! 
#   
# Social Spy only allows %player% and %recipient% as placeholders
# 
# You must download the placeholder expansion through PlaceholderAPI for which
# placeholders you want to use. The example below uses Player placeholders, so
# we need to download the player expansion: /papi ecloud download Player, /papi reload
# 
# [URL] and [EXECUTE] are actions you can add to your click commands.
# [URL] will open the link after the action name.
# [EXECUTE] will execute the command that comes after the action name.
# 
# example format template:
# formats: 
#   default:
#     priority: 2147483647
#     channel: ''
#     prefix: '&8[&7Guest&8] '
#     name_color: '&7'
#     name: '%player_name%'
#     suffix: '&7> '
#     chat_color: '&f'
#     channel_tooltip:
#     - '&7%player_name% &bis a Guest'
#     prefix_tooltip:
#     - '&7%player_name% &bis a Guest'
#     name_tooltip:
#     - ''
#     suffix_tooltip:
#     - ''
#     channel_click_command: '
#     prefix_click_command: '/ranks
#     name_click_command: '/msg %player_name% 
#     suffix_click_command: '
#   Member:
#     priority: 100
#     channel: ''
#     prefix: '&8[&aMember&8] '
#     name_color: '&7'
#     name: '%player_name%'
#     suffix: '&7> '
#     chat_color: '&f'
#     channel_tooltip:
#     - '[URL]https://www.spigotmc.org/resources/deluxetags.4390/'
#     prefix_tooltip:
#     - '&7%player_name% &bis a Member'
#     name_tooltip:
#     - '[EXECUTE]/msg %player_name%'
#     suffix_tooltip:
#     - ''
#     channel_click_command: '
#     prefix_click_command: '/ranks
#     name_click_command: '/msg %player_name% 
#     suffix_click_command: '
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

## Messages

{% code title="messages.yml" %}
```yaml
# DeluxeChat language file
# You can edit all the messages here!
# You must restart for changes to take affect when editing this file!
no_permission: '&cYou don''t have permission to do that!'
msg_incorrect_usage: '&cIncorrect usage! &7/msg <player> <message>'
msg_recipient_not_online: '&c{0} &cis not online!'
msg_recipient_ignoring_sender: '&c{0} &cdoes not wish to speak to you!'
msg_recipient_is_sender: '&cYou can''t message yourself!'
reply_incorrect_usage: '&cIncorrect usage! &7/r <message>'
reply_no_recipient: '&cYou don''t have a recipient to reply to!'
socialspy_toggle_on: '&aSocialspy toggled on!'
socialspy_toggle_off: '&7Socialspy toggled off!'
bungee_global_toggle_on: '&aChat set to global'
bungee_global_toggle_off: '&aChat set to local'
pm_toggle_on: '&aPrivate messaging toggled on.'
pm_toggle_off: '&7Private messaging toggled off.'
pm_toggled_sender: '&7You can not send pm''s with private messages turned off.'
pm_toggled_recipient: '{0} &7has private messages turned off.'
url_incorrect_usage: Hover for url command usage info!
url_incorrect_usage_tooltip_1: '&7/url <link>'
url_incorrect_usage_tooltip_2: '&7/url <link> <message>'
chat_illegal_characters: You can't use special characters in chat!
```
{% endcode %}

