---
description: Configure legacy colors, hex colors, and MiniMessage formatting
---

# Formatting

DeluxeTags supports legacy ampersand color codes, hex colors, and MiniMessage formatting in tags, messages, and GUI text.

## Legacy colors

Legacy color and style codes continue to work:

```yaml
tag: '&7[&e&lVIP&7]'
```

## Hex colors

With `legacy_hex: false`, use the standard `#RRGGBB` format:

```yaml
legacy_hex: false

deluxetags:
  vip:
    tag: '#ffaa00[VIP]'
```

With `legacy_hex: true`, use the legacy `&#RRGGBB` format instead:

```yaml
legacy_hex: true

deluxetags:
  vip:
    tag: '&#ffaa00[VIP]'
```

Hex colors require a server version that supports RGB chat colors. On older versions, unsupported hex values are removed.

## MiniMessage

MiniMessage is disabled by default. Enable it with:

```yaml
use_minimessage: true
```

You can then use MiniMessage tags in tag values, GUI text, and messages:

```yaml
deluxetags:
  vip:
    order: 1
    category: general
    tag: '<gradient:#ff0000:#ffaa00><bold>[VIP]</bold></gradient>'
    displayname: '<gold>Tag: <yellow>%deluxetags_identifier%'
    description:
      - '<gray>A gradient VIP tag'
      - '%deluxetags_available%'
    item: NAME_TAG
    data: 0
```

Legacy `&` codes and configured hex colors remain supported when MiniMessage is enabled, which allows existing formatting to be migrated gradually.

{% hint style="warning" %}
Quote MiniMessage strings in YAML. This prevents characters such as `:` and `#` from being interpreted as YAML syntax.
{% endhint %}

Run `/tags reload` after changing `use_minimessage` or `legacy_hex`.
