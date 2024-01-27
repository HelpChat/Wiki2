---
description: The plugin's configuration files
---

# Plugin's files

## Config

{% code title="config.yml" %}
```yaml
# DeluxeTags version: 1.8.2-Release Main Configuration
#
# Create your tags using the following format:
#
# deluxetags:
#   VIP: 
#     order: 1
#     tag: '&7[&eVIP&7]'
#     description: 'This tag is awarded by getting VIP'
#
# Placeholders for your chat plugin that supports PlaceholderAPI (Including DeluxeChat)
#
# %deluxetags_identifier% - display the players active tag identifier
# %deluxetags_tag% - display the players active tag
# %deluxetags_description% - display the players active tag description
# %deluxetags_amount% - display the amount of tags a player has access to
#
# Placeholders for your essentials/chat handling formats config:
#
# {deluxetags_identifier} - display the players active tag identifier
# {deluxetags_tag} - display the players active tag
# {deluxetags_description} - display the players active tag description
# {deluxetags_amount} - display the amount of tags a player has access to

force_tags: false
check_updates: true
legacy_hex: false
papi_chat: true
format_chat:
  enabled: false
  format: '{deluxetags_tag} <%1$s> %2$s'
load_tag_on_join: true
gui:
  name: '&6Available tags&f: &6%deluxetags_amount%'
  tag_select_item:
    material: NAME_TAG
    data: 0
    displayname: '&6Tag&f: &6%deluxetags_identifier%'
    lore:
    - '%deluxetags_tag%'
    - '%deluxetags_description%'
  divider_item:
    material: BLACK_STAINED_GLASS_PANE
    data: 0
    displayname: ''
    lore: []
  has_tag_item:
    material: PLAYER_HEAD
    data: 0
    displayname: '&eCurrent tag&f: &6%deluxetags_identifier%'
    lore:
    - '%deluxetags_tag%'
    - Click to remove your current tag
  no_tag_item:
    material: PLAYER_HEAD
    data: 0
    displayname: '&cYou don''t have a tag set!'
    lore:
    - '&7Click a tag above to select one!'
  exit_item:
    material: IRON_DOOR
    data: 0
    displayname: '&cClick to exit'
    lore:
    - '&7Exit the tags menu'
  next_page:
    material: PAPER
    data: 0
    displayname: '&6Next page: %page%'
    lore:
    - '&7Move to the next page'
  previous_page:
    material: PAPER
    data: 0
    displayname: '&6Previous page: %page%'
    lore:
    - '&7Move to the previous page'
deluxetags:
  example:
    order: 1
    tag: '&8[&bDeluxeTags&8]'
    description: '&cAwarded for using DeluxeTags!'
    permission: deluxetags.tag.example

```
{% endcode %}

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
