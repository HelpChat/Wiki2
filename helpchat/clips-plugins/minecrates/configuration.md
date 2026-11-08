# Configuration

## Config

{% code title="config.yml" %}
```yaml
# MineCrates 2.10.0 configuration file
# Created by: extended_clip
# 
# 
# area_handler: World / WorldGuard / MRL / PrisonMines
# area_handler is the name of the hook you want to define crate areas for
# Crate areas are tied to the name of the world / mine / region you choose
# depending on the hook you use.
# 
# crate_despawn_time: <time in seconds that crates will despawn after spawning>
# 
# crate_material: <Material or ID of the crate block that is spawned>
# 
# crate_inventory_name: <name of the inventory shown when the crate is opened>
# 
# ==================================================
# 
# Crate area configuration:
# 
# Almost all entries in areas are optional
# although you must have a drop_counter and drop_chance entry.
# You must also have a rewards section with at least 1 valid reward list for the area to be loaded.
# 
# areas:
#   (region, mine, or world name): 
#     permission: (if you want players to have a certain permission to obtain crates in this area, add the permission node here)
#     drop_counter: (how many blocks need to be broken before a crate has a chance to spawn)
#     drop_chance: (what is the chance out of 100.0 that a crate will spawn when the counter reaches 0)
#     alternate_areas:
#     - (if you would like to allow this area options to be used for other areas)
#     - (that way all rewards and options are shared, you can list the alternate area names here)
#     - world_nether
#     - world_the_end
#     counted_materials:
#     - (if you only want to have certain materials count towards the counter)
#     - (you can list them here, otherwise don't add this option)
#     - DIAMOND_ORE
#     - EMERALD_ORE
#     reward_on_break: <true/false> should rewards be given on break of the block instead of spawning a crate
#     rewards: (this section holds all reward related options specific to this area)
#       (name of this reward list):
#         priority: (if you have multiple lists, the lowest priority list will be applied if player has multiple list permissions)
#         permission: (optional if you require players have certain permission to obtain rewards in this list)
#         max_rewards_per_crate: (max amount of rewards a player can get in a crate from this list)
#         only_owner_can_open: (should only the person this crate spawned for be allowed to open it)
#         crate_spawn_actions: (these actions are performed when a crate holding this reward list is spawned)
#         - [msg] You found a crate
#         - [broadcast] @p found a crate
#         - [command] eco give @p 100
#         - [playersound] ANVIL_LAND 10 1
#         - [worldsound] ANVIL_BREAK 10 1
#         - [effect] helix
#         crate_open_actions: (these actions are performed when a crate holding this reward list is opened)
#         - [msg] You opened a MineCrate!
#         - [broadcast] @p opened a crate
#         - [playersound] CHEST_OPEN 10 1
#         - [effect] atom
#         crate_despawn_actions: (these actions are performed when a crate holding this reward list is despawned if it was not opened)
#         - [msg] You missed your crate
#         - [worldsound] ANVIL_BREAK 10 1
#         - [effect] heart
#         items: (this section holds all of the actual commands / items given as rewards)
#           (unique name for this item reward):
#             chance: (chance this reward will be selected) the chance system is explained below...
#             item: (if this reward is an itemstack, you must specify 'item:' here, otherwise you will specify 'commands:')
#               material: (if this is an item, these are the item options you can use)
#               data: (data value if needed)
#               amount: (amount of this item to give)
#               name: (display name to set on this item)
#               lore:
#               - (add your lore here if you want)
#               - (supports multiple lines)
#               enchantments:
#               - <ENCHANTMENT NAME>,<LEVEL>
#           (unique name for this command reward):
#             chance: 50.0
#             commands:
#             - (list all your commands here, they must start with a valid action identifier)
#             - [command] eco give @p 100
#             - [msg] you got 100 bucks!
# ==================================================
# 
# CRATE SPAWN CHANCE INFORMATION
# 
# This chance can be any double value from 0.01 to 100.0
# it is percentage based, so if you set the chance to 10.0
# there will be a 10% chance a crate will spawn when the break
# counter reaches 0. If you set it to 99.0, there will be a 99% chance
# that a crate will spawn when the counter rewaches 0.
# 
# ==================================================
# 
# REWARD CHANCE INFORMATION
# 
# All rewards in a specific reward list have a chance associated with the item/commands that are executed for that reward.
# All reward chances in a list must add up to or be less than 100.0
# Example:
# 
#     rewards:
#       VIP_REWARDS:
#         priority: 1
#         permission: vip.rewards
#         max_rewards_per_crate: 1
#         only_owner_can_open: true
#         items:
#           item_1:
#             chance: 10.0
#             item:
#               material: DIAMOND
#               amount: 128
#           item_2:
#             chance: 15.0
#             item:
#               material: IRON_INGOT
#               amount: 64
#           item_3:
#             chance: 25.0
#             item:
#               material: DIRT
#               amount: 64
#           command_1:
#             chance: 25.0
#             commands:
#             - [command] eco give @p 25
#             - [msg] You got 25 bucks
# 
# With this example, all of our chances add up to 75.0,
# This means that there is a 25% chance that we get nothing each time a reward is
# being selected. If we want to make sure players always get a reward, we could
# simply add one more reward item or command with the remainder percentage for all of our
# chances to equal 100.0, which would be 25.0.
# This system allows you to set what items are rare, and which items are going to be
# more commonly selected when the plugin chooses rewards.
# Always keep in mind that all reward chances must be less than, or add up to 100.0
# If your combined chance exceeds 100.0, the rewards that are being checked after 100.0 has
# been reached will not be loaded. Also remember, to make it where a player has a chance to get
# no reward, always leave the total chance less than 100.0 as all chance remaining will
# be the chance amount that no reward is chosen.
# 
# ==================================================
# 
# CRATE SPAWN/DESPAWN/OPEN/COMMANDS ACTION IDENTIFIERS
# 
# Any action added to these lists must contain a specific identifier
# as there are more actions than just commands to be executed.
# These actions are as follows:
# 
# [msg] <message>
# This will send a raw message to the target player
# 
# [broadcast] <message>
# This will broadcast a message to the entire server
# 
# [command] <command here>
# This will execute a command in the console
# 
# [worldsound] <sound> <volume> <pitch>
# This will play a sound to the entire world at the crate location
# 
# [playersound] <sound> <volume> <pitch>
# This will play a sound to the target player
# 
# [effect] <effectName>
# This will play a preset effect at the crate location
# 
# effect names:
#   animatedball
#   arc
#   atom
#   bleed
#   circle
#   cloud
#   cone
#   cube
#   cylinder
#   disco
#   dna
#   donut
#   dragon
#   earth
#   explode
#   flame
#   fountain
#   grid
#   heart
#   helix
#   hill
#   icon
#   love
#   music
#   shield
#   smoke
#   sphere
#   star
#   tornado
#   vortex
#   warp
#   wave
#   
# ==================================================
# 
# Optional: display a temporary hologram above the MineCrate when it is spawned.
# 
# To enable this feature, add the following entry to the top of your config file:
# 
# You can either use HolographicDisplays API to display the hologram, or the internal
# hologram mechanics. Set handler: none to disable holograms
# 
# Note: the internal hologram handler is only available for 1.8.8
# More hologram handlers will be coming soon.
# 
# crate_hologram:
#   handler: none/internal/holographicdisplays
#   message:
#   - '%player%s MineCrate'
#   - '(Right click to open)
#   height: 2'
# 
# Inside of the message, you can use the following placeholders:
#  %player% - shows players name who MineCrate is for
#  %area% - name of the area the crate spawned in
#  %rewardlist% - name of the list the rewards were chosen from
#  %rewards% - amount of rewards inside of the MineCrate
# 
# ==================================================

crate_hologram:
  handler: none
  message:
  - '&f%player%''s &aMineCrate'
  - '&e(&7Right click to open&e)'
  height: 2.2
check_updates: true
area_handler: World
ignore_silk_touch: true
crate_despawn_time: 30
crate_material: ENDER_CHEST
crate_inventory_name: '%reward_list_name% &aMineCrate'
messages:
  help:
  - '&aMineCrates &fhelp'
  - '&a/minecrates reload &7- &freload the plugin'
  - '&a/minecrates info &7- &fView minecrates information for the area you are standing'
  - '&a/minecrates ignore &7- &ftoggle on/off ignoring minecrates for yourself'
  ignore_toggle_on: '&aYou are now ignoring MineCrates!'
  ignore_toggle_off: '&fYou are no longer ignoring MineCrates!'
  only_owner_can_open_crate: '&cOnly &f@p &ccan open this &aMineCrate!'
  no_permission: '&cYou don''t have permission to do that!'
areas:
  world:
    permission: minecrates.getcrates.world
    drop_counter: 100
    drop_chance: 50.0
    cooldown: 30
    counted_materials:
    - COAL_ORE
    - IRON_ORE
    - GOLD_ORE
    - DIAMOND_ORE
    rewards:
      vip:
        priority: 1
        permission: minecrates.rewards.world.vip
        max_rewards_per_crate: 1
        only_owner_can_open: true
        crate_spawn_actions:
        - '[message] &aYou found a VIP MineCrate!'
        - '[command] eco give @p 100'
        - '[broadcast] &f@p &afound a MineCrate!'
        - '[effect] helix'
        crate_despawn_actions:
        - '[message] &7Your crate has despawned!'
        - '[effect] helix'
        items:
          example_item:
            chance: 20.0
            item:
              material: DIAMOND
              data: 0
              amount: 64
              name: '&bVIP &3Diamonds'
              lore:
              - This item is only available to players who
              - have permission for this vip reward list!
              enchantments:
              - LUCK,1
          example_command_1:
            chance: 1.0
            commands:
            - '[command] eco give @p 1000000'
            - '[msg] You got 1000000 dollars!'
          example_command_2:
            chance: 30.0
            commands:
            - '[command] eco give @p 500'
            - '[msg] You got 500 dollars!'
          example_command_3:
            chance: 49.0
            commands:
            - '[command] eco give @p 1000'
            - '[msg] You got 1000 dollars!'
      default:
        priority: 2
        max_rewards_per_crate: 1
        only_owner_can_open: false
        crate_spawn_actions:
        - '[message] &aYou found a regular MineCrate!'
        - '[command] eco give @p 100'
        - '[broadcast] &f@p &afound a MineCrate!'
        - '[effect] helix'
        items:
          example_item_1:
            chance: 5.0
            item:
              material: DIAMOND
              amount: 16
          example_item_2:
            chance: 10.0
            item:
              material: IRON_INGOT
              amount: 32
          example_command:
            chance: 85.0
            commands:
            - '[command] eco give @p 250'
            - '[msg] You got 250 dollars!'
```
{% endcode %}

