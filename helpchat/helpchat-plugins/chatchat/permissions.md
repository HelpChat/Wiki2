---
description: ChatChat permissions and their default access.
---

# Permissions

All ChatChat permissions default to operators. This includes channel, format, and custom-placeholder permissions, whose exact names depend on your configuration. Grant individual nodes to non-operators with your permissions plugin as needed.

## Commands and player controls

| Permission | Default | Grants |
| --- | --- | --- |
| `chatchat.admin` | Operator | `/chatchat reload`. |
| `chatchat.dump` | Operator | `/chatdump`. |
| `chatchat.test.format` | Operator | `/chatchat test`. |
| `chatchat.togglechat` | Operator | `/togglechat`. |
| `chatchat.rangedchat` | Operator | `/rangedchat`. |
| `chatchat.pm` | Operator | Send and reply to private messages. |
| `chatchat.pm.toggle` | Operator | `/togglemsg`. |
| `chatchat.socialspy` | Operator | `/socialspy`. |
| `chatchat.ignore` | Operator | `/ignore` and `/unignore`. |
| `chatchat.ignorelist` | Operator | `/ignorelist`. |
| `chatchat.ignore.bypass` | Operator | Bypass a recipient's ignore list when sending chat or a private message. |
| `chatchat.separate` | Operator | `/separate`. |
| `chatchat.unseparate` | Operator | `/unseparate`. |

## Channels and formats

| Permission | Default | Grants |
| --- | --- | --- |
| `chatchat.channel.use.<channel-name>` | Operator | Send messages in the named channel and switch to it. |
| `chatchat.channel.see.<channel-name>` | Operator | Receive messages from the named channel. |
| `chatchat.channel.bypass-radius` | Operator | Receive radius-limited messages from any distance unless you enable ranged chat with `/rangedchat`. |
| `chatchat.format.<format-name>` | Operator | Use the named global format from `formats.yml`. |
| `chatchat.channel.format.<channel-name>.<format-name>` | Operator | Use the named format configured for that channel. |

The configured default channel is available without channel-use or channel-see permissions. See [Channels](channels.md) and [Formats](formats.md).

## Mentions

| Permission | Default | Grants |
| --- | --- | --- |
| `chatchat.mention.personal` | Operator | Mention an online player by name. |
| `chatchat.mention.everyone` | Operator | Use `@here`, `@everyone`, or `@channel` mentions in the current channel. |
| `chatchat.mention.personal.block` | Operator | Use `/togglemention personal` to opt out of personal mentions. |
| `chatchat.mention.everyone.block` | Operator | Use `/togglemention channel` to opt out of channel mentions. |
| `chatchat.mention.personal.block.override` | Operator | Mention players who opted out of personal mentions. |
| `chatchat.mention.everyone.block.override` | Operator | Include players who opted out of channel mentions. |

The permission node uses `everyone` for channel-wide mentions, even though the toggle command calls them `channel` mentions. See [Mentions](mentions.md).

## Message formatting and links

| Permission | Default | Grants |
| --- | --- | --- |
| `chatchat.utf` | Operator | Use otherwise restricted Unicode characters in public and private messages when the corresponding DeluxeChat Unicode rule is enabled. The character ø (code point 248) is allowed without this permission. |
| `chatchat.url` | Operator | Automatically turn URLs in chat messages into clickable links. |
| `chatchat.tag.item` | Operator | Use the `<item>` tag in chat messages. |
| `chatchat.tag.click` | Operator | Use MiniMessage click tags. |
| `chatchat.tag.color` | Operator | Use color tags. |
| `chatchat.tag.font` | Operator | Use font tags. |
| `chatchat.tag.gradient` | Operator | Use gradient tags. |
| `chatchat.tag.hover` | Operator | Use hover tags. |
| `chatchat.tag.insertion` | Operator | Use insertion tags. |
| `chatchat.tag.keybind` | Operator | Use keybind tags. |
| `chatchat.tag.newline` | Operator | Use newline tags. |
| `chatchat.tag.rainbow` | Operator | Use rainbow tags. |
| `chatchat.tag.reset` | Operator | Use reset tags. |
| `chatchat.tag.translatable` | Operator | Use translatable tags. |
| `chatchat.tag.translatable-fallback` | Operator | Use the translatable fallback tag `<lang_or>`. |
| `chatchat.tag.head` | Operator | Use the `<head>` tag. |
| `chatchat.tag.shadow` | Operator | Use the `<shadow>` tag. |
| `chatchat.tag.transition` | Operator | Use the `<transition>` tag. |
| `chatchat.tag.pride` | Operator | Use the `<pride>` tag. |
| `chatchat.tag.selector` | Operator | Use the `<selector>` tag. |
| `chatchat.tag.score` | Operator | Use the `<score>` tag. |
| `chatchat.tag.nbt` | Operator | Use the `<nbt>` tag. |
| `chatchat.tag.sprite` | Operator | Use the `<sprite>` tag. |
| `chatchat.tag.obfuscated` | Operator | Use obfuscated text. |
| `chatchat.tag.bold` | Operator | Use bold text. |
| `chatchat.tag.strikethrough` | Operator | Use strikethrough text. |
| `chatchat.tag.underlined` | Operator | Use underlined text. |
| `chatchat.tag.italic` | Operator | Use italic text. |
| `chatchat.tag.placeholder.<name>` | Operator | Use the configured MiniMessage placeholder named `<name>` in your own messages. |

See [MiniMessage tags in chat](tags.md) for examples and [Placeholders](placeholders.md) for configured placeholders.
