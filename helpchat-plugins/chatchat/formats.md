---
description: Configure global and channel-specific ChatChat message formats.
---

# Formats

ChatChat formats public messages with MiniMessage, PlaceholderAPI, and ChatChat's internal tags. Global priority formats live in `formats.yml`; a channel can also define its own formats in `channels.yml`.

## Format structure

Each priority format has a name, a numeric `priority`, and a `parts` mapping. Every part is a list of strings; ChatChat joins the strings and renders the result as one message. Use `<message>` where the player's processed message should appear.

```yaml
default-format: default

formats:
  default:
    priority: 1
    parts:
      channel:
        - '%chatchat_channel_prefix% '
      name:
        - '<white>%player_displayname%'
      divider:
        - ' <gray>» '
      message:
        - '<message>'
```

The `default-format` is used when a player has no permission for another available format. The console uses the separate `console-format`.

## Priority and permissions

Players with more than one eligible format use the one with the highest priority according to `extensions.yml`:

- `addons.deluxechat.inverse_priorities: false` (default): the larger number wins.
- `addons.deluxechat.inverse_priorities: true`: the smaller number wins, matching DeluxeChat's priority direction.

A channel format with a matching permission is selected before any global format, regardless of global format priority.

| Format type | Permission |
| --- | --- |
| Global format named `staff` | `chatchat.format.staff` |
| `staff` format on channel `team` | `chatchat.channel.format.team.staff` |

The configured default format needs no permission. See [Permissions](permissions.md).

## Placeholders and tags

Formats support PlaceholderAPI placeholders in percent form, such as `%player_name%`, and the `<papi:...>` and `<recipient:...>` tags. `<message>` inserts the processed player message. For private-message formats, the sender and recipient contexts are available.

ChatChat also supports MiniMessage formatting tags and configured MiniPlaceholders. See [Placeholders](placeholders.md) and [MiniMessage tags in chat](tags.md).

`console-format` uses a limited parser on Spigot. Tags such as keybind, translation, fonts, and selectors may not work there, and extra percent signs can break the format. Paper handles these console-format limitations more reliably. Avoid tags that need a player recipient context.
