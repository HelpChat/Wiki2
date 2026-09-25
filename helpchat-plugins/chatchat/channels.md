---
description: Configure ChatChat channels, message routing, channel permissions, and cross-server chat.
---

# Channels

Channels control who can send and receive a public message, how players switch channels, and how messages are displayed. Channels are defined in `channels.yml`. The channel map key is its identifier and the suffix used in channel permissions; give each channel a unique name.

## Channel options

| Option | Purpose |
| --- | --- |
| `default-channel` | Channel selected for new players and used as the fallback channel. The named channel must exist. |
| `channels.<name>.toggle-command` | Command names and aliases that switch to the channel. A command can also send a message directly. |
| `channels.<name>.message-prefix` | Prefix typed before a message to send it to this channel without switching. Leave empty to disable. |
| `channels.<name>.channel-prefix` | Display text for the channel. Use `%chatchat_channel_prefix%` in a format to show it. |
| `channels.<name>.radius` | Maximum horizontal distance in blocks between sender and receiver. Use `-1` for no radius limit. Radius channels only reach players in the same world. |
| `channels.<name>.type` | Channel implementation. Defaults to `default`; optional Towny types are `TOWNY_TOWN` and `TOWNY_NATION` when enabled. |
| `channels.<name>.cross-server` | Forwards this channel's public messages to ChatChat on other servers connected to the same supported proxy. Defaults to false. |
| `channels.<name>.formats` | Optional priority formats for this channel. A matching channel format takes precedence over global formats. |

Example:

```yaml
default-channel: global

channels:
  global:
    toggle-command:
      - global
    message-prefix: ''
    channel-prefix: '[global]'
    radius: -1

  staff:
    toggle-command:
      - staffchat
      - sc
    message-prefix: '#'
    channel-prefix: '[STAFF]'
    radius: -1
```

Using `/staffchat` switches to the staff channel. `/staffchat Hello` sends `Hello` there immediately. Typing `#Hello` also sends to the channel while leaving the player's selected channel unchanged.

Channel commands are registered at startup, so restart after editing `toggle-command`. Other changes can be loaded with `/chatchat reload`.

## Send and receive permissions

| Permission | Grants |
| --- | --- |
| `chatchat.channel.use.<channel-name>` | Send messages in the channel and switch to it. |
| `chatchat.channel.see.<channel-name>` | Receive messages from the channel. |
| `chatchat.channel.bypass-radius` | Receive radius-limited channel messages outside the radius. `/rangedchat` opts the holder back into radius checks. |

The configured default channel does not require channel-use or channel-see permissions. Other channels require the corresponding permission for each action.

## Cross-server public chat

Set `cross-server: true` on the channel in `channels.yml` on every backend server that should exchange its messages. Use the same channel name on those servers. Cross-server channels must use the `default` channel type and `radius: -1`; ChatChat rejects other combinations.

ChatChat sends these messages across the supported BungeeCord/Velocity proxy messaging connection. Each receiving server still applies its own channel recipients and local ChatChat behavior. Personal and channel mentions in forwarded messages are processed for recipients on each receiving server.

For proxy-wide private messages, see [Private messaging](private-messaging.md).

## Towny channel types

Towny channels are optional. Set `addons.towny.channels: true` in `extensions.yml`, restart, then define a channel using `type: TOWNY_TOWN` or `type: TOWNY_NATION`. Players must belong to the relevant Towny group to use its channel. Other plugins can register channel types through the [API](api/README.md). See [Optional integrations](extensions.md).
