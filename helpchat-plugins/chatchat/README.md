---
description: ChatChat feature overview and setup guide.
---

# ChatChat

ChatChat is a configurable chat plugin for Paper servers. It provides public chat channels, message formats, private messages, mentions, chat controls, and an API for integrations.

ChatChat requires Paper 1.21.9 or later and Adventure 4.25.0. The `<sprite>` and `<head>` player-message tags also require Paper 1.21.9 or later.

## Features

- Public channels with permissions, optional chat radius, quick message prefixes, channel commands, and proxy-wide forwarding.
- Global and per-channel formats built with MiniMessage and PlaceholderAPI.
- Local and proxy-wide private messages, replies, social spy, ignore lists, and staff-enforced separations.
- Personal mentions and channel mentions with configurable formats and sounds.
- Player controls for public chat and ranged channel messages.
- Configurable MiniMessage placeholders and permission-controlled message tags.
- Optional integrations for Towny, DiscordSRV, vanish plugins, GriefPrevention, and DeluxeChat compatibility.
- An API for custom channel types, hooks, rules, mentions, placeholders, and event listeners.

## Getting started

1. Install ChatChat and its required dependency, PlaceholderAPI.
2. Configure `channels.yml` and `formats.yml` for your server.
3. Give players the permissions for the channels and formats they should use.
4. Use `/chatchat reload` after ordinary configuration changes. Restart after changing channel commands or `extensions.yml`.

## Documentation

- [Commands](commands.md)
- [Permissions](permissions.md)
- [Channels](channels.md)
- [Formats](formats.md)
- [Private messaging](private-messaging.md)
- [Mentions](mentions.md)
- [Placeholders](placeholders.md)
- [MiniMessage tags in chat](tags.md)
- [Optional integrations](extensions.md)
- [Configuration files](files.md)
- [Developer API](api/README.md)
