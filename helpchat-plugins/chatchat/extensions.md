---
description: Optional ChatChat integrations and their extensions.yml settings.
---

# Optional integrations

`extensions.yml` controls optional integrations. Changes to this file require a server restart.

## Add-ons

| Setting | Default | Effect |
| --- | --- | --- |
| `addons.deluxechat.inverse_priorities` | `false` | Selects the direction of format priorities. When true, smaller numbers win; when false, larger numbers win. |
| `addons.deluxechat.unicode_permission.public_chat` | `true` | Requires `chatchat.utf` for non-ASCII characters other than ø in public messages. |
| `addons.deluxechat.unicode_permission.private_chat` | `true` | Requires `chatchat.utf` for non-ASCII characters other than ø in private messages. |
| `addons.towny.channels` | `false` | Enables the `TOWNY_TOWN` and `TOWNY_NATION` channel types. Requires Towny. |
| `addons.discordsrv.channels_bridging` | `false` | Bridges ChatChat and DiscordSRV channels with matching DiscordSRV configuration names. Requires DiscordSRV. |
| `addons.essentials.vanish` | `true` | Uses EssentialsX vanish state when deciding whether players can see one another. |
| `addons.supervanish.vanish` | `false` | Uses SuperVanish/PremiumVanish vanish state when deciding whether players can see one another. |
| `addons.griefprevention.soft_mute` | `false` | Applies GriefPrevention soft mutes to public chat. Requires GriefPrevention. |

Vanilla vanish support is built in. Optional integrations are only available when the corresponding plugin is installed.

## Integration notes

- Enable Towny channels before adding Towny channel types. See [Channels](channels.md).
- DiscordSRV channel names are the names from the DiscordSRV configuration, not the channel's display name in Discord.
- When either DeluxeChat Unicode setting is enabled, `chatchat.utf` grants permission to use otherwise restricted Unicode characters in that message type.
