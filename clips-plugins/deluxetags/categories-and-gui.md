---
description: Configure tag categories, per-tag items, and the DeluxeTags GUI
---

# Categories & GUI

## Categories

DeluxeTags 1.9 can group tags into categories. Each category controls its selector item and the title of its tag menu.

```yaml
categories:
  all:
    order: 0
    item: BOOK
    name: '&3All Tags'
    lore:
      - '&7Click to view all available tags'
    gui_name: '&3All Tags &8%deluxetags_category_amount% available'
  general:
    order: 1
    item: NAME_TAG
    name: '&6General'
    lore:
      - '&7Click to view general tags'
    gui_name: '&6General Tags &8%deluxetags_category_amount% available'
  donor:
    order: 2
    item: DIAMOND
    name: '&bDonor Tags'
    lore:
      - '&7Click to view donor tags'
    gui_name: '&bDonor Tags &8%deluxetags_category_amount% available'
```

Assign each tag with its `category` option:

```yaml
deluxetags:
  vip:
    order: 1
    category: donor
    tag: '&7[&eVIP&7]'
    displayname: '&6Tag&f: &6%deluxetags_identifier%'
    description:
      - '&7A donor tag'
      - '%deluxetags_available%'
    item: GOLD_INGOT
    data: 0
    permission: deluxetags.tag.vip
```

The `all` identifier is reserved for the automatic all-tags selector. Do not assign a tag to `all`; DeluxeTags will place it in `general`. A tag with no category is also assigned to `general`. If a configured category cannot be found, the tag falls back to `general` and a warning is logged.

### Permission-aware category selection

A category is visible to a player when it contains at least one tag they can either select or see. This includes tags granted through the tag's configured permission, `deluxetags.see.<identifier>`, or `deluxetags.see.all`.

The category selection page is shown only when the player can see tags in two or more real categories. When only one category is available, the selector is skipped and that category opens directly. When the selector is shown, the reserved `all` category is included automatically.

## Per-tag GUI items

Every tag now controls its own GUI item.

| Option | Description |
| --- | --- |
| `order` | The tag's unique display order. Lower values appear first. |
| `category` | Category identifier. Defaults to `general`. |
| `tag` | The tag value displayed through `%deluxetags_tag%`. |
| `displayname` | GUI item display name. |
| `description` | GUI lore. Use a YAML list for multiple lines. |
| `item` | Bukkit material used when the player may select the tag. |
| `data` | Legacy durability/data value. |
| `permission` | Permission required to select the tag. Defaults to `deluxetags.tag.<identifier>`. |

Players who may see but not select a tag see the material configured at `gui.tag_visible_item.material`. The tag's own display name and description are retained, so `%deluxetags_available%` can explain whether the tag is unlocked. The selected tag receives an enchantment glow.

{% hint style="info" %}
When upgrading, the old `gui.tag_select_item` display name, lore, material, and data are copied onto existing tags that do not already define those values. Tag descriptions are migrated to multi-line lore, and uncategorized tags are placed in `general`.
{% endhint %}

## GUI layout and buttons

`gui.size` controls the inventory size and must be a multiple of 9 from 9 to 54. `gui.tag_slots` controls where categories and tags are placed and accepts individual slots or ranges such as `0-35`.

The following GUI sections can be customized:

* `gui.tag_visible_item` - fallback material for visible-only tags.
* `gui.divider_item` - decorative filler items.
* `gui.has_tag_item` - current-tag item. When it uses `PLAYER_HEAD`, it displays the viewing player's skin.
* `gui.no_tag_item` - shown when the player has no active tag. `PLAYER_HEAD` also displays the viewing player's skin.
* `gui.exit_item` - closes the GUI.
* `gui.category_back_item` - returns from a tag menu to the category selector.
* `gui.next_page` and `gui.previous_page` - page navigation.

Use `slot` for one position or `slots` for a list of positions. Both forms are supported for configurable buttons.

```yaml
gui:
  size: 54
  tag_slots:
    - 0-35
  category_back_item:
    material: ARROW
    displayname: '&6Back to categories'
    lore:
      - '&7Return to category selection'
    slot: 47
  exit_item:
    material: IRON_DOOR
    displayname: '&cClick to exit'
    lore:
      - '&7Exit the tags menu'
    slots:
      - 48
      - 50
```

See [Placeholders](placeholders.md) for category-count and page placeholders.

## Modern item models

Static GUI items support modern resource-pack data. Add the relevant options to sections such as `gui.exit_item`, `gui.category_back_item`, or `gui.next_page`.

```yaml
gui:
  exit_item:
    material: PAPER
    item_model: mypack:gui/close
    model_data: 1001
    model_data_component:
      colors:
        - '255, 0, 0'
      flags:
        - 'true'
      floats:
        - '1.0'
      strings:
        - close_button
    displayname: '&cClose'
    slot: 49
```

| Option | Supported server versions | Description |
| --- | --- | --- |
| `model_data` | 1.14+ | Legacy integer custom model data. |
| `item_model` | 1.21.2+ | Namespaced item-model key such as `mypack:gui/close`. |
| `model_data_component` | 1.21.4+ | Component values using `colors`, `flags`, `floats`, and `strings` lists. Colors use `red, green, blue` values. |

Options that are not supported by the running server version are ignored.
