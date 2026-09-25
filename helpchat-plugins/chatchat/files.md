---
description: ChatChat configuration files and the settings each file controls.
---

# Configuration files

ChatChat creates and loads these files from its plugin folder.

| File | Purpose |
| --- | --- |
| `settings.yml` | Private-message settings and formats, mention settings and formats, item display, default locale, and reply-target cache duration. |
| `channels.yml` | The default public channel and channel definitions, routing, radius, channel formats, and cross-server forwarding. |
| `formats.yml` | Global public-chat formats, default format, and console format. |
| `placeholders.yml` | Custom MiniMessage placeholders available in formats and, with permission, player messages. |
| `extensions.yml` | Optional integrations and DeluxeChat compatibility settings. Changes require a restart. |
| `locales/en_us.yml` | Bundled English messages. Add other locale files beside it in `locales/`. |

## Reloading configuration

Use `/chatchat reload` after changing ordinary settings, formats, channels, placeholders, or locale files. Restart after changing `extensions.yml` or channel `toggle-command` values.

See the linked configuration guides for [channels](channels.md), [formats](formats.md), [private messaging](private-messaging.md), [mentions](mentions.md), [placeholders](placeholders.md), and [optional integrations](extensions.md).

## Locale files

Locale files use a locale name for the file name, such as `en_us.yml` or `es_es.yml`. ChatChat uses the player's client locale when a matching file exists. Otherwise it checks `default-locale` from `settings.yml`, then falls back to the bundled English messages. Missing message entries also fall back through those defaults.
