---
description: The plugin's configuration files
---

# Plugin's files

## Config

{% code title="config.yml" %}
```yaml
# DeluxeCommands v1.9.0 Main configuration
# Created by extended_clip
# 
# Create commands below!
# Command format is as follows:
# 
# commands:
#   <command_with_no_slash>:
#     permission: <permission to use the command>
#     no_permission_message: <message to send when players do not have permission>
#     message:
#     - '[text]<regular text here if you start the line with the [text] identifier'
#     - '[playercommand] spawn'
#     - '[consolecommand] eco give %executor% 100'
#     - '{"text": "JSON text here"}'
#     - '{"text": "To have multiple JSON components in the same line"}&&{"text": "you must use the && operator between them!"}'
#     target_permission: <permission to use the command with a player argument at the end: /<command> (player)>
#     target_no_permission_message: <message to send when players do not have permission to specify a target to set placeholders for>
#     target_message:
#     - '[text]<You do not have to specify this option, only if you want separate messages when a target is defined>'
#     - '{"text": "%player_name%'s stats:"}'
#     - '{"text": "This message is only if you want a separate message defined when a"}&&{"text": " target player is specified in the command!"}'
#     aliases:
#     - 'somealiasforthiscommand'
# 
# You can now add a new entry to define different aliases per command!
#  simply add the "aliases" option to the commands you would like to define aliases for!
# DeluxeCommands will detect if you have DeluxeChat or PlaceholderAPI installed! You can use any placeholders you have enabled!
# Note: To use %player_name% you need the Player expansion. This can be download via PlaceholderAPI with /papi ecloud download Player
commands:
  somecustomcommand:
    permission: some.custom.permission
    no_permission_message: '&cYou don''t have permission to use this command!'
    target_permission: some.custom.target_permission
    target_no_permission_message: '&cYou don''t have permission to view this command
      with a target player argument!'
    message:
    - '{"text": "--------"}'
    - '{"text": "This is your "}&&{"text": "custom JSON text command showing placeholders
      specific to you!!"}'
    - '{"text": "--------"}'
    target_message:
    - '{"text": "--------"}'
    - '{"text": "This message is optional if you want to show a different message
      when"}&&{"text": " %player_name% is specified at the end of the command"}'
    - '{"text": "--------"}'
```
{% endcode %}

