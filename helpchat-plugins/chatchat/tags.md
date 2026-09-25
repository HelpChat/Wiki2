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
| `<lang>` / `<lang_or>` | `chatchat.tag.translatable` | Operator |
| `<obfuscated>` | `chatchat.tag.obfuscated` | Operator |
| `<bold>` | `chatchat.tag.bold` | Operator |
| `<strikethrough>` | `chatchat.tag.strikethrough` | Operator |
| `<underlined>` | `chatchat.tag.underlined` | Operator |
| `<italic>` | `chatchat.tag.italic` | Operator |
| `<item>` | `chatchat.tag.item` | Operator |

The MiniMessage tag syntax is documented in the [MiniMessage reference](https://docs.papermc.io/adventure/minimessage/format/). The tag syntax is `<insert>`; its permission is named `chatchat.tag.insertion`. The `chatchat.tag.translatable` permission enables `<lang>` and `<lang_or>`.

## URLs and item display

`chatchat.url` automatically makes URLs in chat messages clickable. It defaults to operators.

The `<item>` tag displays the item in the sender's main hand in a chat message. `item-format` and `item-format-info` in `settings.yml` control its display and hover text. The item format must include `<item>`; `<amount>` is also available inside that format.

## Configured tags

Custom tags can be defined in `placeholders.yml`. Players need `chatchat.tag.placeholder.<name>` to use those tags in their own messages; this permission defaults to operators. See [Placeholders](placeholders.md).
