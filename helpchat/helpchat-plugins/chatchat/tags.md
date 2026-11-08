---
description: MiniMessage tags allowed in player messages and their permissions.
---

# MiniMessage tags in chat

ChatChat only parses the MiniMessage tags that the sender has permission to use. Grant the matching `chatchat.tag.<tag>` permission to enable each tag.

| Tag | Permission | Default |
| --- | --- | --- |
| `<click>` | `chatchat.tag.click` | Operator |
| `<color>` | `chatchat.tag.color` | Operator |
| `<font>` | `chatchat.tag.font` | Operator |
| `<gradient>` | `chatchat.tag.gradient` | Operator |
| `<hover>` | `chatchat.tag.hover` | Operator |
| `<insert>` | `chatchat.tag.insertion` | Operator |
| `<key>` | `chatchat.tag.keybind` | Operator |
| `<newline>` | `chatchat.tag.newline` | Operator |
| `<rainbow>` | `chatchat.tag.rainbow` | Operator |
| `<reset>` | `chatchat.tag.reset` | Operator |
| `<lang>` | `chatchat.tag.translatable` | Operator |
| `<lang_or>` | `chatchat.tag.translatable-fallback` | Operator |
| `<head>` | `chatchat.tag.head` | Operator |
| `<shadow>` | `chatchat.tag.shadow` | Operator |
| `<transition>` | `chatchat.tag.transition` | Operator |
| `<pride>` | `chatchat.tag.pride` | Operator |
| `<selector>` | `chatchat.tag.selector` | Operator |
| `<score>` | `chatchat.tag.score` | Operator |
| `<nbt>` | `chatchat.tag.nbt` | Operator |
| `<sprite>` | `chatchat.tag.sprite` | Operator |
| `<obfuscated>` | `chatchat.tag.obfuscated` | Operator |
| `<bold>` | `chatchat.tag.bold` | Operator |
| `<strikethrough>` | `chatchat.tag.strikethrough` | Operator |
| `<underlined>` | `chatchat.tag.underlined` | Operator |
| `<italic>` | `chatchat.tag.italic` | Operator |
| `<item>` | `chatchat.tag.item` | Operator |

The MiniMessage tag syntax and arguments are documented in the [MiniMessage reference](https://docs.papermc.io/adventure/minimessage/format/). For example, `<sprite:blocks:block/stone>` inserts a resource-pack sprite, and `<head:entity/player/wide/steve>` displays a player head. The `<sprite>` and `<head>` tags require Paper 1.21.9 or later (Adventure 4.25.0).

The tag syntax is `<insert>`; its permission is named `chatchat.tag.insertion`. The `chatchat.tag.translatable` permission enables `<lang>`, while `chatchat.tag.translatable-fallback` enables the `<lang_or>` fallback form.

## URLs and item display

`chatchat.url` automatically makes URLs in chat messages clickable. It defaults to operators.

The `<item>` tag displays the item in the sender's main hand in a chat message. `item-format` and `item-format-info` in `settings.yml` control its display and hover text. The item format must include `<item>`; `<amount>` is also available inside that format.

## Configured tags

Custom tags can be defined in `placeholders.yml`. Players need `chatchat.tag.placeholder.<name>` to use those tags in their own messages; this permission defaults to operators. See [Placeholders](placeholders.md).
