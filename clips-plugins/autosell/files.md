---
description: The plugin's configuration files
---

# Plugin's files

## Config

{% code title="config.yml" %}
```yaml
# AutoSell version: 1.9.1 Main Configuration

check_updates: true
block_listener_priority: HIGHEST
hooks:
  mine_reset_lite:
    enabled: true
  worldguard:
    enabled: false
  prisonmines:
    enabled: false
  asylum_mines:
    enabled: false
  jets_prison_mines:
    enabled: false
tools_never_break: true
ignore_custom_items: true
multiplier_save_on_interval: true
multiplier_save_interval: 300
multiplier_default_limit: 100
autosell:
  allow_creative: false
  require_tools: true
  take_sold_items: true
  disabled_worlds:
  - someworld
  - someotherworld
  multipliers_enabled: true
  interval_announcements:
    enabled: true
    interval: 60
    has_multiplier_message:
    - '&8&m-----------------------------------------------------'
    - '&eYour AutoSell stats...'
    - '&bItems Sold&7: &f%items%'
    - '&bAmount&7: &a$&f%amount%'
    - '&bMultiplier: &f%multiplier%'
    - '&8&m-----------------------------------------------------'
    no_multiplier_message:
    - '&8&m-----------------------------------------------------'
    - '&eYour AutoSell stats...'
    - '&bItems Sold&7: &f%items%'
    - '&bAmount&7: &a$&f%amount%'
    - '&8&m-----------------------------------------------------'
signsell:
  per_shop_permissions: true
  has_multiplier_message:
  - '&8&m-----------------------------------------------------'
  - '&bItems Sold&7: &f%items%'
  - '&bAmount&7: &a$&f%amount%'
  - '&bMultiplier: &f%multiplier%'
  - '&8&m-----------------------------------------------------'
  no_multiplier_message:
  - '&8&m-----------------------------------------------------'
  - '&bItems Sold&7: &f%items%'
  - '&bAmount&7: &a$&f%amount%'
  - '&8&m-----------------------------------------------------'
sellall:
  enabled: true
  use_perm_shop_when_no_shop_is_at_location: true
  has_multiplier_message:
  - '&8&m-----------------------------------------------------'
  - '&bItems Sold&7: &f%items%'
  - '&bAmount&7: &a$&f%amount%'
  - '&bMultiplier: &f%multiplier%'
  - '&8&m-----------------------------------------------------'
  no_multiplier_message:
  - '&8&m-----------------------------------------------------'
  - '&bItems Sold&7: &f%items%'
  - '&bAmount&7: &a$&f%amount%'
  - '&8&m-----------------------------------------------------'
item_drops:
  drops2inv:
    enabled: true
    require_permission_node: false
    autosell_areas_only: false
    disabled_worlds:
    - someworld
    - someotherworld
    ignored_blocks:
    - SKULL_ITEM
    - SKULL
    allowed_instead_of_ignored: false
  silk_touch:
    enabled: true
  auto_smelt:
    enabled: true
    toggle_on_join: true
    disabled_worlds:
    - someworld
    - someotherworld
    smelt_list:
    - GOLD_ORE,GOLD_INGOT
    - IRON_ORE,IRON_INGOT
    - WOOL;3,WOOL;5
    - STONE,STONE
  fortune:
    enabled: true
    minimum_drops: 1
    maximum_drops: 1000
    multiplier: 1.2
    modifier: 1
    random_drop_amount: true
    disabled_worlds:
    - someworld
    - someotherworld
    fortune_blocks:
    - DIAMOND_ORE
    - EMERALD_ORE
    - GOLD_ORE
    - IRON_ORE
    - LAPIS_ORE
    - REDSTONE_ORE
    - QUARTZ_ORE
    - COAL_ORE
    - DIAMOND_BLOCK
    - EMERALD_BLOCK
    - GOLD_BLOCK
    - IRON_BLOCK
    - LAPIS_BLOCK
    - REDSTONE_BLOCK
    - QUARTZ_BLOCK
    - COAL_BLOCK
  ingot_to_block:
    enabled: true
    toggle_on_join: true
    auto_blocks_interval: 30
shop_items_info:
  use_gui: true
  message:
  - '&8&m-----------------------------------------------------'
  - '&aShop: &f%shop%'
  - '%items%'
  - '&8&m-----------------------------------------------------'
  item_format: '&7%material%&f:&7%data% &f- &a$&f%price_1%'
vkbackpack:
  bptoggle_on_join: true
shops:
  Shop1:
    priority: 1
    shop_list:
    - STONE,0.50
    - COBBLESTONE,0.20
    - IRON_ORE,0.35
    - COAL_ORE,0.20
money:
  fix_money: true
  use_custom_format: false
  custom_format: '#,###.00'
  thousands_format: k
  millions_format: M
  billions_format: B
  trillions_format: T
  quadrillions_format: Q
```
{% endcode %}

## Messages

{% code title="messages.yml" %}
```yaml
# AutoSell language file
# You can edit all the messages here!
# You must restart for changes to take affect when editing this file!
autosell_disabled_in_world: '&cAutoSell is disabled in your current world!'
autosell_no_permission: '&cYou don''t have &7{0} &cto use AutoSell!'
autosell_no_shop: '&cYou don''t have a shop to sell to!'
autosell_toggle_on: '&aAutoSell enabled'
autosell_toggle_off: '&7AutoSell disabled'
autosmelt_disabled: '&cAutoSmelt is currently disabled!'
autosmelt_disabled_in_world: '&cAutoSmelt is disabled in your current world!'
autosmelt_no_permission: '&cYou don''t have &7{0} &cto use AutoSmelt!'
autosmelt_toggle_on: '&aAutoSmelt enabled'
autosmelt_toggle_off: '&cAutoSmelt disabled'
multiplier_disabled: '&cMultipliers are currently disabled!'
multiplier_expired: '&7Your AutoSell multiplier has expired...'
multiplier_others_incorrect_usage: '&cIncorrect usage! Use &7/multiplier <player>'
multiplier_no_permission_self: '&cYou don''t have &7{0} &cto check your multiplier!'
multiplier_no_permission_others: '&cYou don''t have &7{0} &cto check another players
  multiplier!'
multiplier_no_multiplier_self: '&cYou don''t have a multiplier at the moment...'
multiplier_no_multiplier_others: '&7{0} &cdoesn''t have a multiplier at the moment...'
multiplier_has_multiplier_self: '&aYour current multiplier is &f{0} &aand will expire
  in &f{1}'
multiplier_has_multiplier_others: '&7{0}''s &acurrent multiplier is &f{1} &aand will
  expire in &f{2}'
global_multiplier_message: '&aGlobal multiplier: &f{0} &7expires in &f{1}'
global_multiplier_expired: '&7The global multiplier has expired!'
permission_multiplier_message: '&aYou have a permission based multiplier of &f{0}'
signs_no_break_permission: '&cYou don''t have permission to break that sign!'
signs_no_sell_permission: '&cYou don''t have &7{0} &cto sell at that sign!'
signs_no_shop_error: '&cThere is no shop associated with that sign! Please contact
  an admin.'
signs_no_shop_items_error: '&cThere are no items listed in the shop you are trying
  to sell to!'
signs_sold_with_multiplier: '&aYou sold &f{0} &aitems for $&f{1} &awith a multiplier
  of &f{2}&a!'
signs_sold_without_multiplier: '&aYou sold &f{0} &aitems for $&f{1}&a!'
signs_no_items_to_sell: '&cYou don''t have any items to sell to shop &f{0}&c!'
autoblocks_disabled: '&c/block is currently disabled!!'
autoblocks_no_permission: '&cYou don''t have &7{0} &cto use /blocks!'
autoblocks_toggle_on: '&aAuto ingots to blocks enabled!'
autoblocks_toggle_off: '&7Auto ingots to blocks disabled!'
autoblocks_help_1: '&7Ingots to blocks help'
autoblocks_help_2: '&7/autoblocks &c- &fconvert all ingots in your inventory to blocks'
autoblocks_help_3: '&7/autoblocks toggle &c- &ftoggle ingots to blocks on/off'
autoblocks_incorrect_command: '&cIncorrect usage! Use &7/autoblocks help'
sellall_disabled: '&c/sellall is currently disabled!!'
sellall_no_permission: '&cYou don''t have &7{0} &cto use /sellall'
sellall_no_shop_error: '&cYou don''t have a shop to sell to!.'
sellall_no_shop_items_error: '&cThere are no items listed in the shop you are trying
  to sell to!'
sellall_sold_with_multiplier: '&aYou sold &f{0} &aitems for $&f{1} &awith a multiplier
  of &f{2}&a!'
sellall_sold_without_multiplier: '&aYou sold &f{0} &aitems for $&f{1}&a!'
sellall_no_items_to_sell: '&cYou don''t have any items to sell at shop &f{0}&c!'
sellall_shop_incorrect_shopname: '&f{0} &cis not a valid shop!'
sellall_shop_no_permission: '&cYou don''t have &f{0} &cto use &f/sellall <shop>&c!'
items_no_permission: '&cYou don''t have &7{0} &cto use /items'
items_no_shop_at_location: '&cThere is not a shop at your location, use &7/items <shop>&c!'
items_incorrect_shop_name: '&cThere is no shop named &7{0}&c!'
items_no_shop_items_error: '&cThere are no items listed in the shop you are trying
  to view!'
items_lore_format: '&7Sell &f1 &7for: &a$&f{0}, &7Sell &f64 &7for: &a$&f{1}'
admin_addmultiplier_global_multiplier_set: '&aA &fGLOBAL &amultiplier of &f{0} &ahas
  been set!'
admin_addmultiplier_global_multiplier_set_no_expiry: '&aAnd will not expire!'
admin_addmultiplier_global_multiplier_set_has_expiry: '&aAnd will expire in &f{0}&a!'
admin_addmultiplier_player_multiplier_set: '&bYou now have a multiplier of &f{0}'
admin_addmultiplier_player_multiplier_set_no_expiry: '&aAnd will not expire!'
admin_addmultiplier_player_multiplier_set_has_expiry: '&aAnd will expire in &f{0}&a!'
player_not_online: '{0} &cis not online!'
vkbackpacks_no_permission: '&cYou don''t have &7{0} &cto toggle backpack selling on
  or off!'
vkbackpacks_no_backpacks: '&cYou don''t have any backpacks!'
vkbackpacks_toggle_on: '&aBackpack selling enabled'
vkbackpacks_toggle_off: '&cBackpack selling disabled'
worth_no_permission: '&cYou don''t have &7{0} &cto view the worth of an item!'
worth_no_shop: '&cNo shop found to check the worth of the item in your hand'
worth_no_item_in_hand: '&cYou must be holding an item to check the value'
worth_no_value: '&cNo price found for the item in your hand'
worth_has_value: '&7Worth for: &f%material% &ex1/&a$&f%price_1% &ex64/&a$&f%price_64%
  &7at shop: &f%shop%'
```
{% endcode %}

## Permission Multipliers

{% code title="permission\_multipliers.yml" %}
```yaml
# AutoSell permission_multipliers.yml file
# This file allows you to create custom multipliers that can be attached to players or groups by permission
# 
# The format for a multiplier must follow this format:
# <unique identifier>:
#   priority: <unique number>
#   permission: <your custom permission for this multiplier>
#   multiplier: <the multiplier amount>
# 
# You can list as many multipliers you like.
# Each multiplier must have a unique priority set!!!
# The priority determines what multiplier comes first in your list
# If a player happens to have permission for many multipliers
# the lowest number priority will always be applied


permission_multipliers:
  example:
    priority: 1
    permission: some.multiplier.permission
    multiplier: 1.5
```
{% endcode %}

## Shop Multipliers

{% code title="shop\_multipliers.yml" %}
```yaml
# AutoSell shop_multipliers.yml file
# This file allows you to create custom multipliers that can be attached to players or groups by permission
# 
# These multipliers will only take effect in the shops listed for the multiplierThe format for a multiplier must follow this format:
# <unique identifier>:
#   priority: <unique number>
#   permission: <your custom permission for this multiplier>
#   multiplier: <the multiplier amount>
#   shops:
#   - 'shop1'
#   - 'shop2'
# 
# You can list as many multipliers you like.
# Each multiplier must have a unique priority set!!!
# The priority determines what multiplier comes first in your list
# If a player happens to have permission for many multipliers
# the lowest number priority will always be applied if that multiplier has the shop listed the player
# is trying to sell to!


shop_multipliers:
  example:
    priority: 1
    permission: some.shopmultiplier.permission
    multiplier: 1.5
    shops:
    - shop1
    - shop2
```
{% endcode %}

