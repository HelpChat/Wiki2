---
description: Configure personal and channel mentions, mention formats, sounds, and permissions.
---

# Mentions

ChatChat can mention online players in public messages and notify the receivers with a sound. Mention settings and formats are in `settings.yml`.

## Mention types

| Type | Example | What it matches |
| --- | --- | --- |
| Personal | `@Alex` | The configured prefix followed by an online player's name. |
| Channel | `@here`, `@everyone`, `@channel` | A notice to eligible receivers of the current channel. |

Plugins can register additional mention types through the [API](api/README.md). The default prefix is `@`. Set `mentions.prefix` to a different string to change it; set it to an empty string to disable mentions.

Personal mentions require `chatchat.mention.personal`. Channel mentions require `chatchat.mention.everyone`. A receiver can opt out using `/togglemention personal` or `/togglemention channel` if they have the corresponding `.block` permission. The matching `.block.override` permission lets a sender mention opted-out users.

Mention visibility and sound are resolved for each eligible receiver, respecting the channel's recipient rules. Mention formatting uses `mentions.personal-format` or `mentions.channel-format`; each format can use `<mention>` for the matched text.

## Sound and private messages

The `mentions.sound` setting controls the sound for mentions. Configure the Adventure sound `name`, `source`, `pitch`, and `volume`. The `mentions.private-message` setting controls whether receiving a private message also plays this sound.

## Permissions

| Permission | Grants |
| --- | --- |
| `chatchat.mention.personal` | Use personal mentions. |
| `chatchat.mention.everyone` | Use `@here`, `@everyone`, and `@channel`. |
| `chatchat.mention.personal.block` | Toggle receiving personal mentions. |
| `chatchat.mention.everyone.block` | Toggle receiving channel mentions. |
| `chatchat.mention.personal.block.override` | Mention a player who opted out of personal mentions. |
| `chatchat.mention.everyone.block.override` | Include a player who opted out of channel mentions. |

The permission node contains `everyone` for channel mentions, while the toggle command uses the word `channel`. See [Permissions](permissions.md).
