---
description: Private message commands, settings, formats, social spy, and proxy-wide messaging.
---

# Private messaging

ChatChat includes private messages, replies, player message toggles, and social spy.

## Commands

| Command | Aliases | Permission | Description |
| --- | --- | --- | --- |
| `/whisper <player> <message>` | `/tell`, `/w`, `/msg`, `/message`, `/pm` | `chatchat.pm` | Send a private message. |
| `/reply <message>` | `/r` | `chatchat.pm` | Reply to the most recent private conversation. |
| `/togglemsg` | `/toggledms`, `/togglepms` | `chatchat.pm.toggle` | Toggle whether you can receive private messages. |
| `/socialspy [on\|off]` | `/sspy`, `/pmspy`, `/spy` | `chatchat.socialspy` | Toggle visibility of private messages sent by players. |

When `private-messages.enabled` is `false`, ChatChat does not register these commands. Players can ignore a sender with `/ignore`; see [Commands](commands.md).

## Settings and formats

The private-message settings are in `settings.yml`:

| Setting | Default | Purpose |
| --- | --- | --- |
| `private-messages.enabled` | `true` | Enables private messaging commands and processing. |
| `private-messages.cross-server` | `false` | Allows messages and replies to players connected to another backend on the same proxy. |
| `private-messages.formats.sender-format` | Built in | Format shown to the sender. |
| `private-messages.formats.recipient-format` | Built in | Format shown to the recipient. |
| `private-messages.formats.social-spy-format` | Built in | Format shown to social-spy users. |
| `last-messaged-cache-duration` | `300` seconds | How long `/reply` and `%chatchat_private_messages_recipient%` retain the last conversation target. Set below `0` to disable expiration. |

These formats support MiniMessage, PlaceholderAPI, `<message>`, and recipient-aware tags. For example, `<recipient:player_name>` shows the other player in a private-message format.

## Cross-server private messages

Enable `private-messages.cross-server: true` in `settings.yml` on each backend server that should participate. ChatChat forwards private messages through the supported BungeeCord/Velocity proxy messaging connection. `/reply` can reply to a conversation with a player on another backend.

Private messages are separate from cross-server public channels. To forward public chat, configure `cross-server: true` on a global channel as described in [Channels](channels.md).
