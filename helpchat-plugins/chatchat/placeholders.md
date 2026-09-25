---
description: ChatChat PlaceholderAPI placeholders, internal tags, and configurable MiniPlaceholders.
---

# Placeholders

ChatChat provides a PlaceholderAPI expansion and internal MiniMessage tags for use in formats and configured placeholders.

## PlaceholderAPI placeholders

ChatChat registers its own `chatchat` expansion. No separate eCloud download is needed.

| Placeholder | Return value | Description |
| --- | --- | --- |
| `%chatchat_channel_name%` | Text | The player's current channel name. |
| `%chatchat_channel_prefix%` | Text | The display prefix of the player's current channel. |
| `%chatchat_channel_message_prefix%` | Text | The quick-send prefix of the player's current channel. |
| `%chatchat_social_spy_enabled%` | Boolean | Whether social spy is enabled for the player. |
| `%chatchat_private_messages_enabled%` | Boolean | Whether the player accepts private messages. |
| `%chatchat_private_messages_recipient%` | Text | Name of the last private-message conversation target, or an empty string when there is none. |
| `%chatchat_ranged_chat_enabled%` | Boolean | Whether the player has ranged-chat filtering enabled. |

The last-message target expires after `last-messaged-cache-duration` seconds by default. A negative value disables expiration.

## Tags for formats

These tags are available in ChatChat formats. MiniMessage tag names are case-insensitive.

| Tag | Example | Result |
| --- | --- | --- |
| `<papi:...>` | `<papi:player_name>` | Parses a PlaceholderAPI placeholder for the sender. |
| `<papi:closing:...>` | `<papi:closing:player_displayname>` | Parses a sender placeholder without allowing legacy color formatting to continue past the inserted value. |
| `<papi:inserting:...>` | `<papi:inserting:player_displayname>` | Parses a sender placeholder and lets its formatting continue after the inserted value. |
| `<papi-rel:...>` | `<papi-rel:rel_factionsuuid_relation>` | Parses a relational PlaceholderAPI placeholder for the sender and recipient. The placeholder name must begin with `rel_`. |
| `<recipient:...>` | `<recipient:player_name>` | Parses a PlaceholderAPI placeholder for the message recipient. |
| `<message>` | `<message>` | Inserts the processed chat or private message into a format. |

Use the PAPI placeholder name without `%` inside these tags. The regular `%placeholder%` syntax is also available in configured formats. Recipient and relational tags need a recipient context, such as a private-message format or a per-recipient public format. Cross-server private-message formats support `<recipient:player_name>` for the remote recipient.

## Configured MiniPlaceholders

Define custom tags in `placeholders.yml`. A configured tag named `greeting` is used as `<greeting>`. The tag name must match `[!?#]?[a-z0-9_-]*`. Players need `chatchat.tag.placeholder.greeting` to use it in their own messages; configured formats can use the tag without that player-message permission.

| Option | Purpose |
| --- | --- |
| `name` | Tag name used between angle brackets. |
| `message` | Text inserted by the tag. |
| `requires-recipient` | When `parse-mini` and `parse-papi` are enabled, allows recipient and relational placeholders and requires a player recipient context. |
| `parse-mini` | Parses MiniMessage tags inside the configured message. |
| `parse-papi` | Parses supported PlaceholderAPI tags when `parse-mini` is enabled. |
| `closing` | When true, closes formatting from the inserted content. When false, inserted formatting can continue into the surrounding format. |

See [MiniMessage tags in chat](tags.md) for the tags players can use in public messages.
