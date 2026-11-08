---
description: ChatChat commands, aliases, permissions, and channel command setup.
---

# Commands

## Plugin commands

| Command | Aliases | Permission | Description |
| --- | --- | --- | --- |
| `/chatchat` | — | None | Shows the plugin name and version. |
| `/chatchat reload` | — | `chatchat.admin` | Reloads ChatChat configuration and locale files. |
| `/chatchat test <format> <message>` | — | `chatchat.test.format` | Previews a configured global format. |
| `/chatdump [file]` | — | `chatchat.dump` | Creates and uploads a diagnostic dump, optionally limited to one file. |
| `/togglechat` | — | `chatchat.togglechat` | Toggles your ability to send and receive public chat. |
| `/rangedchat` | — | `chatchat.rangedchat` | Toggles radius filtering for your own reception when you have radius bypass. |
| `/separate <player1> <player2>` | — | `chatchat.separate` | Prevents two players from seeing one another in public chat and private messages. |
| `/unseparate <player1> <player2>` | — | `chatchat.unseparate` | Removes a staff-enforced separation. |
| `/ignore <player>` | — | `chatchat.ignore` | Adds a player to your ignore list. |
| `/unignore <player>` | — | `chatchat.ignore` | Removes a player from your ignore list. |
| `/ignorelist` | — | `chatchat.ignorelist` | Lists players you ignore and players separated from you by staff. |

## Private messaging commands

These commands are registered only when `private-messages.enabled` is `true`. See [Private messaging](private-messaging.md).

| Command | Aliases | Permission | Description |
| --- | --- | --- | --- |
| `/whisper <player> <message>` | `/tell`, `/w`, `/msg`, `/message`, `/pm` | `chatchat.pm` | Sends a private message. |
| `/reply <message>` | `/r` | `chatchat.pm` | Replies to the most recent private conversation. |
| `/togglemsg` | `/toggledms`, `/togglepms` | `chatchat.pm.toggle` | Toggles whether you can receive private messages. |
| `/socialspy [on\|off]` | `/sspy`, `/pmspy`, `/spy` | `chatchat.socialspy` | Enables or disables private-message social spy. |

## Mention command

| Command | Alias | Permission | Description |
| --- | --- | --- | --- |
| `/togglemention <personal\|channel>` | `/toggleping` | `chatchat.mention.personal.block` or `chatchat.mention.everyone.block` | Toggles the selected kind of mention. |

## Channel commands

Each channel can register one or more commands through its `toggle-command` list in `channels.yml`. For a channel named `staff`, a configured command such as `staffchat` lets a player use `/staffchat` to switch channels or `/staffchat <message>` to send a message directly. The default channel does not require a channel-use permission; other channels require `chatchat.channel.use.<channel-name>`.

Channel command names are registered when ChatChat starts. Restart the server after changing `toggle-command`.

A `message-prefix` is a separate quick-send option. For example, with `message-prefix: '#'`, a player can type `#message` without switching channels.

## Command conflicts

If another plugin owns an alias such as `/msg`, use Bukkit's `commands.yml` to route it to ChatChat. For example:

```yaml
aliases:
  msg:
    - chatchat:msg $1-
```

Restart after editing `commands.yml`.
