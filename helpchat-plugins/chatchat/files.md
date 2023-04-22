---
description: List of the default files the plugin contains.
---

# Files

## settings.yml

```yaml
# The format to send to the sender of a private message
# All formats can be formatted using MiniMessage: https://docs.adventure.kyori.net/minimessage/index.html

private-messages:
  enabled: true
  formats:
    sender-format:
      parts:
        sender:
          - '<gray>you'
        separator:
          - ' <color:#40c9ff>-> '
        recipient:
          - '<gray><recipient:player_name>'
        message:
          - ' <#e81cff>» <white><message>'
    # The format to send to the recipient of a private message
    recipient-format:
      parts:
        sender:
          - '<gray>%player_name%'
        separator:
          - ' <#40c9ff>-> '
        recipient:
          - '<gray>you'
        message:
          - ' <#e81cff>» <white><message>'

    # The format to send to any players with socialspy enabled
    social-spy-format:
      parts:
        prefix:
          - '<gray>(spy) '
        sender:
          - '%player_name%'
        separator:
          - ' <#40c9ff>-> '
        recipient:
          - '<gray><recipient:player_name>'
        message:
          - ' <#e81cff>» <white><message>'

# The format that the <item> placeholder will use in chat. Needs to contain <item>.
# Another available internal placeholder is <amount>.
item-format: '<gray>[</gray><item><gray> x <amount>]'

# Custom line that can show in the hover of the <item> placeholder displaying stuff like item's exact name and amount
# Set to empty string '' if you want to disable it from ever showing.
item-format-info: '<dark_gray><item> x <amount>'

# The prefix to use for mentioning players
mention-prefix: '@'

# The format to use for individual player mentions
mention-format:
  parts:
    name:
      - '<hover:show_text:"<gold>This is a mention!">'
      - '<yellow>@%player_name%'
      - '</hover>'

# The format to use for @channel/@here/@everyone
channel-mention-format: '<yellow>'

# The sound to play when a player is mentioned
# The sounds use the format of adventure sounds, which in turn use the original minecraft names, NOT spigot's.
# Name - Set the sound to play: names of all sounds can be found here: https://www.digminecraft.com/lists/sound_list_pc.php
# Source - set where the source can be played through, the list of all sources can also be found on the above website.
mention-sound:
  name: entity.experience_orb.pickup
  source: master
  pitch: 1
  volume: 1

# Whether to play the mention sound when a user receives a private message
mention-on-message: true

# After how many seconds should the last messaged user be cleared. Set to below 0 to disable expiration.
last-messaged-cache-duration: 300

```

## channels.yml

```yaml
# Set the default channel to talk in.
default-channel: 'global'

# Channels configuration
channels:
  global: # default channel as set in default-channel, no permission required.
    # command to switch channel
    # Changes to this setting REQUIRES a server restart
    toggle-command:
      - 'global'
    # prefix the message with this to automatically type the message in channel
    message-prefix: ''
    # pretty much a variable for the channel prefix, which can be accessed using the PAPI placeholder: %chatchat_channel_prefix%
    # Channel prefixes can be formatted using MiniMessage: https://docs.adventure.kyori.net/minimessage/index.html
    channel-prefix: '[global]'
    # radius from sender other players need to be in to see sender's message. -1 for no radius
    radius: -1
  staff: # permission node: chatchat.channel.see.staff to access this channel (or chatchat.channel.use.staff to talk)
    toggle-command:
      - 'staffchat'
    message-prefix: '#'
    channel-prefix: '[STAFF]'
    radius: -1

#  # this one's for towny, uncomment this section if you have towny installed
#  town:
#    # a special, optional value, indicating that this is a towny town chat
#    # valid options are 'TOWNY_TOWN', 'TOWNY_NATION'
#    # if the type is not valid, it falls back to a standard chat channel
#    type: 'TOWNY_TOWN'
#    toggle-command: 'townchat'
#    message-prefix: 't:'
#    channel-prefix: '[Town]'
#  # as above, but for nations instead of towns
#  nation:
#    type: 'TOWNY_NATION'
#    toggle-command: 'nationchat'
#    message-prefix: 'n:'
#    channel-prefix: '[Nation]'

```

## formats.yml

```yaml
# Set the default format. This will be used when players do not have any other format permissions
default-format: 'default'
# Set the console format. This is the format that will be seen from the console. You will have to use %s to specify
# the player name and the message location instead of <message>
console-format:
  parts:
    channel:
      - '%chatchat_channel_prefix% '
    prefix:
      - '<gray>[<color:#40c9ff>Chat<color:#e81cff>Chat<gray>] '
    name:
      - <white>%player_name%
    message:
      - ' <gray>» <white><message>'


formats:
  default: # this is the default format as set by default-format. No permission is needed.
    priority: 2 # lower number = higher priority
    # list of all the parts of the format, supports unlimited amount of parts.
    # Technically only 1 part is needed and every part only needs one line but to clean up the config, multiple parts
    # can be used and each part can have multiple lines.
    # These parts can be formatted using MiniMessage, which can be found here:
    # https://docs.adventure.kyori.net/minimessage/index.html
    parts:
      channel:
        - '<click:open_url:"https://google.com">'
        - '<hover:show_text:"I am chatting in the %channel_name% channel<newline>Some new line">'
        - '%chatchat_channel_prefix%'
        - '</hover>'
        - '</click>'
      group:
        - '<hover:show_text:"Hey look, i am in the %vault_group% permission group.<newline>Some new line">'
        - ' [%vault_group%]'
        - '</hover>'
      name:
        - '<hover:show_text:"Hey look, i am in the %vault_group% permission group.<newline>Some new line">'
        - ' %player_displayname%'
        - '</hover>'
      divider:
        - '<hover:show_text:"Cool diver tooltip here">'
        - ' > '
        - '</hover>'
      message:
        - '<message>'
        - '<hover:show_text:"This forces everyone to have a ! on the end. Haha">'
        - '!'
        - '</hover>'

  staff: # user needs 'chatchat.format.staff' permission
    priority: 1
    parts:
      channel:
        - '<click:open_url:"https://google.com">'
        - '<hover:show_text:"I am chatting in the %channel_name% channel<newline>Some new line">'
        - '%chatchat_channel_prefix%'
        - '</hover>'
        - '</click>'
      prefix:
        - '<hover:show_text:"Hey look, i am staff<newline>Some new line">'
        - ' [STAFF]'
        - '</hover>'
      name:
        - '<hover:show_text:"Hey look, i am in the %vault_group% permission group.<newline>Some new line">'
        - ' %player_displayname%'
        - '</hover>'
      message-and-divider:
        - '<hover:show_text:"Cool diver tooltip here"> ></hover>'
        - '<message>'

```

## messages.yml

```yaml
# https://wiki.helpch.at

console-only: <red>Only the console can do this!
players-only: <red>Only players can do this!
user-offline: <red>The user is not online!
user-no-town-found: <red>You are not in a town!
no-replies: <red>You have no one to reply to!
replies-disabled: You can't send private messages while they're disabled!
target-replies-disabled: <red>This user has their private messages disabled!
private-messages-enabled: <green>Your private messages have been enabled!
private-messages-disabled: <red>Your private messages have been disabled!
cant-message-yourself: <red>You can't message yourself!
empty-message: <red>You can't send an empty message!
special-characters-no-permission: <red>You do not have permission to use special characters!
social-spy-enabled: <green>Social spy enabled
social-spy-disabled: <red>Social spy disabled
channel-no-permission: <red>You do not have permission to use this channel!
dump-fail: <red>Failed to create dump!
dump-success: '<green>Dump created successfully! You can find it at: <url>'
channel-switched: <green>You have switched to the <channel> channel!
command-unknown-command: <red>Unknown Command.
command-invalid-usage: <red>Invalid usage.
command-invalid-argument: <red>Invalid argument.
command-no-permission: <red>No Permission.

```
