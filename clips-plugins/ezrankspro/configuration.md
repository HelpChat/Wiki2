---
description: The plugin's configuration files
---

# Configuration

## Config 

{% code title="config.yml" %}
```yaml
# EZRanksPro 1.9.0 main configuration file
# Created by extended_clip
check_updates: true
debug: false
check_primary_group_for_available_rankup: false
chat_prefix_enabled: false
log_rankups_to_file: false
confirm_to_rankup:
  enabled: true
  time: 10
rankup_cooldown:
  enabled: true
  time: 30
ranks_command_enabled: true
ranks:
  use_custom_message: true
  custom_message:
  - '&8&m----------'
  - '&aA&f: &a$&f100'
  - '&bB&f: &a$&f200'
  - '&cC&f: &a$&f300'
  - '&8&m----------'
  header:
  - '&8&m----------'
  format_previous_ranks: '&8%rank% to %rankto%: Completed'
  format_current_rank: '&f%rank% to %rankto%: &a$&f%cost%'
  format_incomplete_ranks: '&7%rank% to %rankto%: &a$&f%cost%'
  format_last_rank: '&f%lastrank%: &cLast rank!'
  format_is_last_rank: '&f%lastrank%: &aYou are the last rank!'
  footer:
  - '&8&m----------'
money:
  use_custom_format: false
  custom_format: '#,###.00'
  thousands_format: k
  millions_format: M
  billions_format: B
  trillions_format: T
  quadrillions_format: Q
progress_bar:
  has_color: '&a'
  needs_color: '&8'
  end_color: '&e'
  left_character: '['
  bar_character: ':'
  right_character: ']'
  is_full: '&a/rankup'
placeholders:
  rank_completed: completed
  rank_not_completed: incompleted
autorankup:
  enabled: true
  check_interval: 60
```
{% endcode %}

## Multipliers

{% code title="multipliers.yml" %}
```yaml
# EZRanksPro multiplier.yml file
# This file allows you to create custom cost multipliers and discounts
# Discounts need to be listed in the rankup_cost_discounts: section
# Multipliers need to be listed in the rankup_cost_multipliers section
# 
# The format for a multiplier and discount is the same:
# <unique identifier>:
#   priority: <unique number>
#   permission: <your custom permission for this multiplier/discount>
#   percentage: <your percentage to add on/take off of the cost>
# 
# You can list as many multipliers/discounts you like for each section.
# Each multiplier/discount must have a unique priority set!!!
# The priority determines what multiplier comes first in your list
# If a player happens to have multiple discount or multiplier
# permissions, the lowest priority will always be applied
# 
# The percentage system works just like a discount at a store...
# If you set a discount percentage to 99.0 for a rank that cost 100 dollarsanyone with that discount permission will only pay 1 dollar
# The format for percentage can include a decimal ex: 1.25, 99.9, 1, 1.05
# DO NOT INCLUDE A % SYMBOL!!!
# Discounts can not exceed a 100% percentage, 
# if your discount makes the rankup cost negative
# the price will default to 1
# You can set multipliers to any percentage: 400.0, 200.0 etc 
# If a player has permission for a cost multiplier and discount, the multiplier will always be applied before the discount
# is applied. Meaning: player has a multiplier to make ranking up cost twice as much and has perm for discount
# The discount will be applied to the new cost AFTER the multiplier is applied.
rankup_cost_discounts:
  example:
    priority: 1
    permission: some.discount.permission
    percentage: 0.0
rankup_cost_multipliers:
  example:
    priority: 1
    permission: some.multiplier.permission
    percentage: 0.0
```
{% endcode %}

## Rankups

{% code title="rankups.yml" %}
```yaml
# EZRanksPro rankups.yml file
# Create your rankups in this file.
# If you need a default template, delete the rankups: section and
# let it regenerate an example rankup.
# 
# rankup_actions are a list of 
# actions which will be executed
# when a player successfully ranks up
# 
# You must include required arguments
# <required>, (optional)
# rankup_action list:
# [consolecommand] <command> - perform a console command
# [playercommand] <command> - make the player perform a command
# [message] <message> - send the player a message
# [broadcast] <message> - send the server a message
# [jsonmessage] <json>- send the player a json message
# [jsonbroadcast] <json> - send the server a json message
# [actionbarmessage] <message> - send the player an actionbar message
# [actionbarbroadcast] <message> - send the server an actionbar message
# [addgroup] <group> (world) - add the player to a permissions group
# [removegroup] <group> (world) - remove the player from a permissions group
# [addpermission] <permission> (world) - add a permission node to the player
# [removepermission] <permission> (world) - remove a permission node from a player
# [setprefix] <prefix> - set the players prefix
# [setsuffix] <suffix> - set the players suffix
# [effect] <effect> - play an effect at the players location
# [sound] <sound> <volume> <pitch> - play a sound at the players location
# 
# You can delay any of the rankup actions being performed by ending the action with
# <delay=(time in seconds)>
# example:
# [consolecommand] eco give %player% 100 <delay=10>
# 
# Placeholders can be used in your rankup actions and messages:
# 
# %player% - players name
# %displayname% - players displayname
# %world% - players current world
# %rank% - players current rank
# %rankup% - players next rank (if they have one)
# %cost% - cost to rankup
# %cost_formatted% - formatted cost to rankup
# %balance% - players balance
# %balance_formatted% - players formatted balance
# %difference% - amount still needed
# %difference_formatted% - formatted amount still needede
# %progress% - rounded progress % based on cost - balance
# %progressexact% - exact progress % based on cost - balance
# %progressbar% - custom progressbar based on cost - balance
# %rankprefix% - players current rank prefix defined in this file
# %rankupprefix% - players next rank prefix defined in this file
# %lastrank% - last rank available
# %lastrankprefix% - last rank available prefix
# %rankup_cost_<rankname>% - show the cost for a specific rank
# %rankup_cost_formatted_<rankname>% - show the formatted cost for a specific rank
# %rankup_is_completed_<rankname>% - show if a player has completed the specified rank

last_rank:
  rank: Z
  prefix: '&8[&bZ&8]'
requirement_message:
- '&8&m------------'
- '&cYou need &a$&f%cost% &cto rankup to %rankupprefix%'
- '&8&m------------'
rankups:
  A:
    order: 1
    prefix: '[A]'
    rankup_to: B
    cost: 1000.0
    rankup_actions:
    - '[broadcast] &6&l>&b&l> &6%player% &eranked up to &7[&e&l%rankup%&7]'
    - '[addgroup] %rankup%'
    - '[removegroup] %rank%'
```
{% endcode %}


## Messages

{% code title="messages.yml" %}
```yaml
# EZRanksPro messages file
no_permission: '&cYou don''t have the permission node &f{0} &cto do that!'
rankup_last_rank: '&7You are at the last rank and have no more rankups.'
rankup_no_rankups: '&cYou don''t have any rankups available at your current rank.'
rankup_confirm_message: |-
  &aAre you sure you want to rankup to &f%rankup% for &a$&f%cost%?
  &aType &7/rankup &ato confirm.
rankup_on_cooldown: '&cYou need to wait %time% more seconds until you can rankup again!'
ranks_no_ranks_loaded: '&cThere are no ranks loaded!'
target_not_online: '&f{0} &cis not online!'
force_rankup_no_rankup: '&f{0} &cdoes not have any rankups available at rank &f{1}&c!'
force_rankup_success: '&f{0} &awas successfully ranked up from &f{1} &ato &f{2}&a!'
autorankup_toggle_on: '&aAutoRankup toggled on.'
autorankup_toggle_off: '&7AutoRankup toggled off.'
autorankup_last_rank: '&cYou are at the last rank and have no need to autorankup!'
autorankup_no_rankups: '&cYou do not have a rankup at your current rank and will not
  be able to autorankup!'
```
{% endcode %}
