---
description: The plugin's configuration files
---

# Plugin's files

## Config

{% code title="config.yml" %}
```yaml
# DeluxeTags version: 1.9.0-Release Main Configuration
#
# Formatting options:
# legacy_hex: false # Use '#RRGGBB' for raw hex colors
# legacy_hex: true  # Use '&#RRGGBB' for raw hex colors
# use_minimessage: false # Enable tags such as <red> and <gradient:#ff0000:#00ff00>
#
# Create your tags using the following format:
#
# deluxetags:
#   VIP:
#     order: 1
#     category: general
#     tag: '&7[&eVIP&7]'
#     displayname: '&6Tag&f: &6%deluxetags_identifier%'
#     description:
#       - 'This tag is awarded by getting VIP'
#       - '%deluxetags_available%'
#     item: NAME_TAG
#     data: 0
#
# Create categories using the following format:
#
# categories:
#   general:
#     order: 1
#     item: NAME_TAG
#     name: '&6General'
#     lore:
#       - '&7Click to view general tags'
#     gui_name: '&6General tags &8%deluxetags_category_amount% available'
#
# The reserved 'all' category configures the automatic all-tags selector item.
#
# Placeholders for your chat plugin that supports PlaceholderAPI:
#
# %deluxetags_identifier% - display the players active tag identifier
# %deluxetags_tag% - display the players active tag
# %deluxetags_description% - display the players active tag description
# %deluxetags_amount% - display the amount of tags a player has access to
#
# Placeholders for the tags GUI:
#
# %deluxetags_available% - display whether the player can select the displayed tag
# %deluxetags_category_amount% - display the amount of tags the player can select in the current category

use_minimessage: false
force_tags: false
check_updates: true
legacy_hex: false
papi_chat: true
format_chat:
  enabled: false
  format: '{deluxetags_tag} <%1$s> %2$s'
load_tag_on_join: true
gui:
  tag_availability_placeholder:
    has_permission: '&aTag unlocked! Click to select'
    no_permission: '&cTag locked '
  name: '&3Select a category:'
  size: 54
  tag_slots:
  - 0-35
  tag_visible_item:
    material: BARRIER
    data: 0
  divider_item:
    material: BLACK_STAINED_GLASS_PANE
    data: 0
    displayname: '&0'
    lore: []
    slots:
    - 36-44
  has_tag_item:
    material: PLAYER_HEAD
    data: 0
    displayname: '&eCurrent tag&f: &6%deluxetags_identifier%'
    lore:
    - '%deluxetags_tag%'
    - Click to remove your current tag
    slot: 49
  no_tag_item:
    material: PLAYER_HEAD
    data: 0
    displayname: '&cYou don''t have a tag set!'
    lore:
    - '&7Click a tag above to select one!'
    slot: 49
  exit_item:
    material: IRON_DOOR
    data: 0
    displayname: '&cClick to exit'
    lore:
    - '&7Exit the tags menu'
    slots:
    - 48
    - 50
  category_back_item:
    material: ARROW
    data: 0
    displayname: '&6Back to categories'
    lore:
    - '&7Return to category selection'
    slot: 47
  next_page:
    material: PAPER
    data: 0
    displayname: '&6Next page: %page%'
    lore:
    - '&7Move to the next page'
    slot: 53
  previous_page:
    material: PAPER
    data: 0
    displayname: '&6Previous page: %page%'
    lore:
    - '&7Move to the previous page'
    slot: 45
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
    gui_name: '&6General tags &8%deluxetags_category_amount% available'
  epic:
    order: 2
    item: BLAZE_POWDER
    name: '&3Epic Tags'
    lore:
    - '&9Click to view epic tags'
    gui_name: '&3Epic Tags &8%deluxetags_category_amount% available'
deluxetags:
  example:
    order: 1
    category: general
    tag: '&8[&bDeluxeTags&8]'
    displayname: '&6Tag&f: &6%deluxetags_identifier%'
    description:
    - '&cAwarded for using DeluxeTags!'
    - '%deluxetags_available%'
    item: NAME_TAG
    data: 0
    permission: deluxetags.tag.example
  epic:
    order: 2
    category: epic
    tag: '&8[&3Epic&8]'
    displayname: '&6Tag&f: &6%deluxetags_identifier%'
    description:
    - '&9Awarded for using categories'
    - '%deluxetags_available%'
    item: BLAZE_POWDER
    data: 0
    permission: deluxetags.tag.epic

```
{% endcode %}

For detailed explanations and additional examples, see [Categories & GUI](categories-and-gui.md) and [Formatting](formatting.md).

When `check_updates: true`, DeluxeTags checks Modrinth for new releases and notifies players with `deluxetags.updates`.

{% hint style="warning" %}
Back up `config.yml` before upgrading. DeluxeTags 1.9 automatically migrates `gui.tag_select_item` values to individual tags, converts tag descriptions to lore lists, moves the legacy `tag_availability_placeholder` section under `gui`, and assigns uncategorized tags to `general`.
{% endhint %}

## Messages

{% code title="messages.yml" %}
```yaml
# DeluxeTags messages.yml
# Edit the plugin messages to your liking!

cmd:
  no_permission: '&cYou don''t have &7{0} &cto do that!'
  target_not_online: '&f{0} &cis not online!'
  no_tags_loaded: '&cThere are no tags loaded!'
  no_tags_available: '&cYou don''t have any tags available!'
  no_tags_available_target: '&f{0} &cdon''t have any tags available!'
  tag_list_fail: '&cYou don''t have any tags loaded.'
  tag_list_fail_target: '&c{0} has no tags loaded.'
  tags_list: '&f{0} &aavailable tags: &f{1}'
  tags_list_all: '&f{0} &atotal tags loaded: &f{1}'
  tags_list_others: '&f{0} &ahas &f{1} &atotal tags loaded: &f{2}'
  tag_select_incorrect_usage: '&cIncorrect usage! &7/tags select <tagname>'
  tag_select_success: '&7Your tag was set to: &r{1}'
  tag_select_invalid_name: '&f{0} &cis not a valid tag name!'
  tag_select_already_set: '&f{0} &cis already set as your current tag!'
  help_title: '&5&lDeluxeTags &f&oHelp'
  help_color: '&8> &d&l'
  help_tags: '&f&oOpen your tags GUI'
  help_list: '&f&oView tags available to you'
  help_select: '&f&oSelect a tag as your active tag'
  help_admin_set: '&f&oSet a players tag'
  help_admin_clear: '&f&oClear a players tag'
  help_admin_create: '&f&oCreate a new tag'
  help_admin_delete: '&f&oDelete an existing tag'
  help_admin_setdesc: '&f&oSet a description for a tag'
  help_admin_setorder: '&f&oChange the order for a tag'
  help_admin_setdisplay: '&f&oChange a tag''s display'
  help_version: '&f&oView DeluxeTags version and author information'
  help_reload: '&f&oReload the tags config'
  admin_set_incorrect_usage: '&cIncorrect usage! &7/tags set <player> <tag>'
  admin_set_no_tags_avail: '&f{0} &cdoesn''t have any tags available!'
  admin_set_success: '&f{0}s &atag has been set to: {1} &7({2}&7)'
  admin_set_success_to_target: '&7Your tag has been set to &f{1} &aby &f{2}'
  admin_set_success_fail: '&f{0} &cis not a valid tag for &f{1}&c!'
  admin_clear_incorrect_usage: '&cIncorrect usage! &7/tags clear <player>'
  admin_clear_no_tag_set: '&f{0} &cdoesn''t have a tag set!'
  admin_clear_success: '&f{0}s &atag has been cleared!'
  admin_clear_success_to_target: '&7Your tag has been cleared &aby &f{0}'
  admin_create_tag_incorrect_usage: '&cIncorrect usage! &7/tags create <identifier>
    <tag>'
  admin_create_tag_success: '&aTag created&7: &f{0}&7:&f{1}'
  admin_create_tag_fail: '&f{0} &cis already a loaded tag name!'
  admin_delete_tag_incorrect_usage: '&cIncorrect usage! &7/tags delete <identifier>'
  admin_delete_tag_success: '&7Tag &f{0} &7has been deleted!'
  admin_delete_tag_fail: '&f{0} &cis not a loaded tag name!'
  admin_set_description_incorrect_usage: '&cIncorrect usage! &7/tags setdesc <identifier>
    <description>'
  admin_set_description_success: '{0} &adescription set to &7: &f{2}'
  admin_set_description_fail: '&f{0} &cis not a loaded tag name!'
  admin_set_order_incorrect_usage: '&cIncorrect usage! &7/tags setorder <identifier>
    <order>'
  admin_set_order_success: '&aOrder &f{0}&a set for &7: &f{1}'
  admin_set_order_fail: '&f{0} &cis not a loaded tag name!'
  admin_set_order_not_a_number: '&f{0} &cis not a valid order! It should be a number.'
  admin_set_order_already_exists: '&cOrder &f{0}&c is already in use.'
  admin_set_display_incorrect_usage: '&cIncorrect usage! &7/tags setdisplay <identifier>
    <display>'
  admin_set_display_success: '{0} &adisplay set to &7: &f{1}'
  admin_set_display_fail: '&f{0} &cis not a loaded tag name!'
  admin_reload: '&aConfiguration successfully reloaded! &f{0} &atags loaded!'
  incorrect_usage: '&cIncorrect usage! Use &7/tags help'
gui:
  placeholders:
    tag:
      available: '&aAvailable'
      unavailable: '&cUnavailable'
  tag_selected: '&aYour tag has been set to &f{0} &7({1}&7)'
  tag_disabled: '&7Your tag has been disabled!'
  page_error: '&cThere was a problem getting the previous page number!'

```
{% endcode %}

## Storage

{% hint style="warning" %}
Storage selection is available only in DeluxeTags v1.10.0 and newer.
{% endhint %}

`mysql.yml` controls where player tag selections are stored. YAML is the default and stores selections locally in `userdata/player_tags.yml`. MySQL stores them in a shared database, allowing servers using the same database and table prefix to share selections. Tag definitions and permissions remain local to each server.

{% code title="mysql.yml" %}
    storage:
      type: yaml # yaml or mysql
      sync-interval-seconds: 5
      mysql:
        host: localhost
        port: 3306
        database: deluxetags
        username: deluxetags
        password: 'your-password'
        table-prefix: deluxetags_
{% endcode %}

Create the database before selecting MySQL. Restart the server after changing storage settings.

### Storage files

| File | Purpose |
| --- | --- |
| `mysql.yml` | Selects YAML or MySQL and contains the storage settings. |
| `userdata/player_tags.yml` | Stores local selections with YAML; valid selections are imported once when MySQL is first initialized. |
| `storage-installation-id` | Generated for each MySQL installation. Keep it across restarts and use a unique ID for each server. |
