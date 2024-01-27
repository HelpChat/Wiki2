---
description: The plugin's configuration files
---

# Plugin's files

## Config

{% code title="config.yml" %}
```yaml
# DeluxeMenus 1.13.1-Release main configuration file
# 
# A full wiki on how to use this plugin can be found at:
# https://github.com/help-chat/DeluxeMenus/wiki

debug: HIGHEST
check_updates: true
gui_menus:
  basics_menu:
    file: basics_menu.yml
  advanced_menu:
    file: advanced_menu.yml
  requirements_menu:
    file: requirements_menu.yml
```
{% endcode %}

## Basics Menu

{% code title="basics_menu.yml" %}
```yaml
#  A DeluxeMenus basic configuration guide for beginners
#=========================================================
#
# This note will help you understand the basic functions and configuring of DeluxeMenus: commands, requirements, items and others, and from then on you can start to work with more advanced stuff. You can delete this note or any note below at any time. But if you are still here anyway, then let's move down below
#

# Open Command
#
# This setting is the command that will be used to open this menu. Supports normal String or a String List
# NOTE: Use "open_command: []" to create a menu with no commands needed
#
# open_command: <command>
# open_command:
#   - <command1>
#   - <command2>
#
open_command: basicsmenu

# Size
#
# This allows you to set the size of the menu inventory. Range from 9-54.
# If this option is not present in the menu configuration, it will default to 54.
#
size: 9

# Menu title
#
# This is the title of the menu. You can change it with your custom name
# Color codes and placeholders are supported
#
menu_title: 'Basics Menu'

# Open requirement
#
# This setting section allows you to define requirements the menu viewer must meet
# to be allowed to open this menu in game.
#
# Any menu you want to restrict access to based on permission
# should have a basic "has permission" requirement
#
# This setting and requirements can be explained more in depth by checking out
# the requirements_menu.yml file in your menus folder.
# For full reference, check https://github.com/help-chat/DeluxeMenus/wiki/Requirements
#
open_requirement:
  requirements:
    permission:
      type: has permission
      permission: deluxemenus.admin
      deny_commands:
        - '[message] &cYou don''t have permission to do that!'

# Item section. This is where you can start add items into menu, and add functions into each items that you did.
# For depth explanation on the functions, you can check on the note given from config.yml
# For full reference, check https://github.com/help-chat/DeluxeMenus/wiki/Item
#
items:
  # Here you need to set the name ID of the item. This name however, does not display on the menu. Every item must have a unique name ID.
  # In this example, we will call this item name ID: "teststone"
  'teststone':
    #We will start to create a STONE item,
    material: STONE
    # with a Block data set to 1, so that you can change stone type from STONE to GRANITE. More informations about the block data can be checked through each items from Minecraft Wikipedia
    data: 1
    # Slots that you want to put the item. Starts from 0
    slot: 0
    # Here we will name this item. You can change this at anytime. PlaceholderAPI & Color codes supported
    display_name: "&aThis is a special stone"
    # This is the lore setting. Referrence of this same with display_name.
    # You can create multiple lines of lores like this
    lore:
      - "&aTest1"
      - "&cTest2"
      - "&eTest3"


# ==============================================================
#
# Random tips, tricks, and useful info below
#
# ==============================================================
#
# PER ITEM PERMISSION AND PRIORITY INFO:
#
# Per item permissions and priorities are optional.
# High priority = 1, Lowest priority = 2147483647.
# This allows you to show different items for a specific menu slot depending on the highest priority
# item permission a player has. This makes your menus very dynamic :)
#
# You CAN NOT specify a permission without a priority!
# You CAN specify a priority without a permission.
# You should always create a low priority item without a permission which will act as the no permission
# item if a player does not have permission for any of the items that require permission, otherwise
# no item will be set in the slot if a player does not have permission for any of the permission items.
#
# ==============================================================
#
# You specify the command which opens the menu. Make sure this command
# does not conflict with any existing commands on your server!
# A GUI menu without an open command specified will not be loaded!
#
# Menus configuration layout:
# menu_title: '<title of menu goes here>'
# command: <command to open this menu goes here>
# inventory_type: '<add this option if you want to create a menu of a different InventoryType aside from chest>'
# open_requirement:
#   requirements:
#     <unique name for this requirement>:
#    type: <type for this requirement>
#    <unique options per requirement type would go here>
#    deny_commands:
#    - '[message] you do not meet requirements to open this menu'
#   size: <size of this menu, increments of 9, max size is 54>
#   update_interval: <time in seconds this gui should update for a player if an item is set to uodate placeholders>
#   items:
#     <item identifier>:
#       material: <name or id>
#       material: head-<name of player>
#       material: hdb-<HeadDatabase id> (requires plugin HeadDatabase)
#       data: <integer, used for data values for wool etc>
#       amount: <amount of this item to show>
#       slot: <slot number to put this item, slots start at 0 and end at 53 for a size 54 inventory>
#       priority: <this is used if you have multiple items set for the same slot>
#       view_requirement: <see view requirement info below. The lowest priority item a player meets all view requirements for will be shown>
#       update: <true/false if this item should update placeholders on the interval set for the gui menu this item is in>
#       hide_attributes: <true/false if this item should display item attributes>
#       hide_enchantments: <true/false if this item should display item enchantment / level> (useful for 'enchantment glow' items)
#       hide_effects: <true/false if this item should display item effect attributes>
#       hide_unbreakable: <true/false if this item should display item unbreakable attributes>
#       banner_meta: (this is used if you want to display a custom banner with specific patterns)
#       - <dyecolor>;<PatternType> (more information on where to find DyeColor and PatternType names below)
#       - 'RED;BASE'
#       - 'WHITE;CREEPER'
#       display_name: <display name to show for this item>
#       lore:
#       - 'This is the lore of the itemm'
#       - 'placeholders can be used in the display_name or lore.'
#       enchantments: valid enchantment names can be found here: https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html
#       - '<ENCHANTMENT>;<LEVEL>'
#       - 'SILK_TOUCH;1'
#       left_click_commands:
#       right_click_commands:
#       shift_left_click_commands:
#       shift_right_click_commands:
#       middle_click_commands:
#       left_click_requirement: <Learn how to use this option in the requirements_menu.yml>
#       right_click_requirement: <Learn how to use this option in the requirements_menu.yml>
#       shift_left_click_requirement: <Learn how to use this option in the requirements_menu.yml>
#       shift_right_click_requirement: <Learn how to use this option in the requirements_menu.yml>
#       middle_click_requirement: <Learn how to use this option in the requirements_menu.yml>
#
#
# You can specify if a GUI menu should be loaded from another file:
#
# gui_menus:
#   <menuName>:
#     file: 'menuName.yml'
#
# This allows you to keep your config clean and not have tons of GUI menus cluttering it.
# The file format the GUI menu is loaded from must end in .yml
# GUI menus loaded from other configuration files must follow a specific format as well...
# To get started loading GUI menus from different files, simply create a GUI menu in this config and specify the file it will load from.
# After that is done, use /dm reload and DeluxeMenus will create a folder and file specific to the GUI menu you specified.
# If the file specified is created by DeluxeMenus (because it did not exist), a default GUI menu layout will be saved to that file.
# From here you can edit it to your liking and use /dm reload to update your GUI menu!
#
# This loading from external config files is only available for gui menus and will not work for click menus yet....
#
# banner_meta must be listed with a specific format:
# banner_meta:
# - <DyeColor>;<PatternType>
#
# Valid DyeColor names can be found here: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/DyeColor.html
# Valid PatternTypes can be found here: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/block/banner/PatternType.html
# ==============================================================
#
# Requirement information
#
# Requirements can be set as the following:
#
# open_requirement: This requirement is checked when a menu is opened
# view_requirement: This requirement determines if an item should be set in a menu slot
# left_click_requirement: This requirement is checked when an item is left clicked
# right_click_requirement: This requirement is checked when an item is right clicked
#
# Requirement types:
#   javascript - Evaluates a javascript expression that must return true or false
#     configuration options:
#       expression
#
#   has item - Checks if a player has a specific item
#     configuration options:
#       material
#       amount
#       data
#       name
#       lore
#
#   has money - Checks if a player has enough money (Vault required)
#     configuration options:
#       amount
#
#   has permission - Checks if a player has a specific permission
#     configuration options:
#       permission
#
#   string contains - Checks if a string contains another string
#     configuration options:
#       input
#       output
#
#   string equals - Checks if a string equals another string
#     configuration options:
#       input
#       output
#
#   string equals ignorecase - Checks if a string equals another string ignoring case
#     configuration options:
#       input
#       output
#
#   > - Checks if a number is greater than another number
#     configuration options:
#       input
#       output
#
#   >= - Checks if a number is greater than or equal to another number
#     configuration options:
#       input
#       output
#
#   == - Checks if a number is equal to another number
#     configuration options:
#       input
#       output
#
#   <= - Checks if a number is less than or equal to another number
#     configuration options:
#       input
#       output
#
#   < - Checks if a number is less than another number
#     configuration options:
#       input
#       output
#
#   regex matches - Checks if a placeholder parsed string matches a regex pattern
#     configuration options:
#       input
#       regex
#
#
#
# So why would we want to use requirements?
# By default, DeluxeMenus does not require a player meet any conditions to open your menu.
# If you want to require a menu need a certain permission node for it to be accessed, or a certain amount of money
# for a menu to be opened, You do that with an 'open_requirement'.
# Below is an example of how you would deny opening a menu if the viewer does not have permission:
#
# menu_title: 'Menu that requires permission to open'
# open_command: testmenu
# size: 9
# open_requirement:
#   requirements:
#     this_requirement_name:
#       type: has permission
#       permission: 'testmenu.open'
#       deny_commands:
#       - '[message] you do not have permission to open testmenu'
#
# ==============================================================
#
# Every item in the items list must have a unique <item identifier>
#
# If you choose to update placeholders for a specific item, you must specify update_interval: <time>
# in the menu options for the specific menu.
#
# Every click_command must start with a specific identifier to know what to do for the execution.
# Valid click_command identifiers:
#
# [console] - Execute a command from the console
# Usage: - '[console] <command with no slash>'
#
# [player] - Execute a command for the menu viewer
# Usage: - '[player] <command with no slash>'
#
# [commandevent] - Fire a PlayerCommandPreprocessEvent for commands that do not use the bukkit command system
# Usage: - '[commandevent] <command with no slash>'
#
# [message] - Send a message to the menu viewer
# Usage: - [message] <message to send to the player
#
# [openguimenu] - Open a GUI menu (can only be used in GUI menu click_commands)
# Usage: - '[openguimenu] <guiMenuName>'
#
# [connect] - Connect to the specified bungee server
# Usage: - '[connect] <serverName>'
#
# [close] - Close the viewers open menu
# Usage: - '[close]
#
# [refresh] - Refresh items in the current menu view
# Usage: - '[refresh]
#
# [broadcastsound] - Broadcast a sound to the server
# Usage: - '[broadcastsound]
#
# [sound] - Play a sound for a the specific player
# Usage: - '[sound]
#
# [json] - Send a json message to the menu viewer
# Usage: - '[json] {"text":"message"}'
#
#
#
# You can delay any of the click command being performed by ending the command with
# <delay=(time in TICKS)>
# example:
#     - '[close]'
#     - '[message] it has been 5 seconds since the menu closed!<delay=100>'
#     - '[message] it has been 10 seconds since the menu closed!<delay=200>'
#
```
{% endcode %}

## Advanced Menu

{% code title="advanced_menu.yml" %}
```yaml
#  A DeluxeMenus advanced configuration guide
#=========================================================
menu_title: '&8> &6&lD&eM &bAdvanced Example'
open_command:
  - advancedmenu
  - advancedexamplemenu
  - themostadvancedmenuintheworld
open_commands:
  - '[sound] BLOCK_BEACON_ACTIVATE'
  - '[message] &7Opening Advanced example menu, Plugin created by &bextended_clip&7!'
size: 27
# as always, only cool people can open this menu :)
open_requirement:
  requirements:
    permission:
      type: has permission
      permission: deluxemenus.admin
      deny_commands:
        - "[message] &8[&bDeluxe&eMenus&8] &cYou don't have perms for this!"
items:
  'example':
    material: LIME_DYE
    slot: 11
    priority: 1
    update: true
    hide_attributes:  true
    display_name: '&bExample Kit'
    lore:
      - ''
      - '&7Cooldown : &f3 Days'
      - '&7Left Click to Redeem'
    view_requirement:
      requirements:
        kit_requirement:
          type: string equals
          input: '%essentials_kit_is_available_example%'
          output: 'yes'
        kit_perm:
          type: has permission
          permission: essentials.kits.example
    left_click_commands:
      - '[player] kit example'
      - '[close]'
  'examplecd':
    material: GRAY_DYE
    slot: 11
    priority: 2
    update: true
    hide_attributes:  true
    display_name: '&cExample Kit Unavailable'
    lore:
      - '&7This kit is on cooldown!'
      - '&7You must wait : &f%essentials_kit_time_until_available_example%'
      - '&7Before using this kit again.'
    view_requirement:
      requirements:
        kit_perm:
          type: has permission
          permission: essentials.kits.example
  'examplenoperm':
    material: GRAY_DYE
    slot: 11
    priority: 3
    update: true
    hide_attributes:  true
    display_name: '&7Example Kit'
    lore:
      - '&7You do not have permission for this kit!'
  'shopexample':
    material: head-extended_clip
    slot: 12
    display_name: '&r'
    lore:
      - '&7Shop example using'
      - '&7view requirements!'
      - '&fLeft click to purchase.'
    priority: 1
    view_requirement:
      requirements:
        shop_perm:
          type: has permission
          permission: deluxemenus.shopexample
    left_click_commands:
      - '[sound] ENTITY_FIREWORK_ROCKET_BLAST'
      - '[console] give %player_name% skull 1 player:extended_clip name:&bExtended_Clip lore:&8<lore>|&7Example_Shop_Item|&8<lore>'
      - '[message] &8[&6&lDeluxeShop&8] &fYou have succesfully purchased &7extended_clips &fhead!'
      - '[console] eco take %player_name% 666'
      - '[close]'
    left_click_requirement:
      requirements:
        balance_check:
          type: has money
          amount: 666
  'shopnoperm':
    material: head-extended_clip
    slot: 12
    display_name: '&7No permission'
    lore:
      - '&8You are missing the &bdeluxemenus.shopexample'
      - '&8permission which is required to view the item!'
      - '&fLeft click to close the menu.'
    left_click_commands:
      - '[sound] ENTITY_SNOW_GOLEM_DEATH'
      - '[close]'
      - '[message] &8[&6&lDeluxeShop&8] &fYou have closed the menu! &7(1 Second message delay!) <delay=20>'
  'filler_item':
    material: GRAY_STAINED_GLASS_PANE
    slots:
      - 0
      - 1
      - 2
      - 3
      - 4
      - 5
      - 6
      - 7
      - 8
    display_name: ' '
```
{% endcode %}

## Requirements Menu

{% code title="requirements_menu.yml" %}
```yaml
#
# Requirements tutorial menu v1.0
# authors: clip
#
# contributor: Andre_601
#
# In this tutorial you will learn all about menu requirements
# Requirements allow you to restrict actions or even an entire menu to specific players.
#
# You can read more about requirements here:
#   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/requirements
#
menu_title: 'Requirements Menu'
open_command: requirementsmenu
size: 9
#
# as always, only cool people can open this menu :)
#
open_requirement:
  requirements:
    permission:
      #
      # "has permission" checks if a player has the required permission
      #
      # Read more:
      #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/requirements#has-permission
      #
      type: has permission
      permission: deluxemenus.shop
      deny_commands:
        - '[message] &cYou don''t have permission to do that!'
items:
  #
  # Example 1: Shop Item
  #
  # This is a gold block, which allows you to buy or sell gold blocks for money.
  #
  'gold_block':
    material: GOLD_BLOCK
    slot: 0
    lore:
    - '&7Buy/Sell GOLD_BLOCK'
    - ''
    - '&7- Left-click: &bBuy 1 &7for &a$100'
    - '&7- Right-click: &bSell 1 &7for &a$50'
    - '&7- Shift-left-click: &bBuy 64 &7for &a6,400'
    - '&7- Shift-right-click: &bSell 64 &7for &a$3,200'
    #
    # Requirement(s) when left-clicking an item.
    #
    left_click_requirement:
      requirements:
        #
        # "has money" checks if the player has enough money. Requires Vault.
        # "amount" defines how much the player needs to at least have.
        #
        # Read more:
        #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/requirements#has-money
        #
        has_money:
          type: has money
          amount: 100
      deny_commands:
      - '[message] &cYou don''t have enough money for this!'
    #
    # Command(s) to execute when left-clicking the item.
    # Those commands won't be executed when the above requirements aren't met.
    #
    # Read more:
    #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/item#shift-left-middle-right-click-commands
    #
    left_click_commands:
    - '[console] give %player_name% GOLD_BLOCK 1'
    - '[takemoney] 100'
    - '[message] &aYou bought 1 &6GOLD_BLOCK &afor $100'
    #
    # Requirement(s) for right-clicking an item.
    #
    right_click_requirement:
      requirements:
        #
        # "has item" checks if the player has the specified item in their inventory.
        # Except for "material" and "amount" are all other values optional and will default to a specific value.
        # We check for if the player has 1 gold block.
        #
        # Read more:
        #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/requirements#has-item
        #
        has_item:
          type: has item
          material: 'GOLD_BLOCK'
          amount: 1
        deny_commands:
        - '[message] &cYou don''t have enough &6GOLD_BLOCK &cto sell! Required: 1'
    #
    # Command(s) to execute when right-clicking the item.
    # Those commands won't be executed when the above requirements aren't met.
    #
    # Read more:
    #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/item#shift-left-middle-right-click-commands
    # 
    right_click_commands:
    - '[console] clear %player_name% GOLD_BLOCK 1'
    - '[console] eco give %player_name% 50'
    - '[message] &aYou sold 1 &6GOLD_BLOCK &afor $50'
    #
    # Requirement(s) when left-clicking an item while holding shift on the keyboard.
    #
    shift_left_click_requirement:
      requirements:
        #
        # "has money" checks if the player has enough money. Requires Vault.
        # "amount" defines how much the player needs to at least have.
        #
        # Read more:
        #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/requirements#has-money
        #
        has_money:
          type: has money
          amount: 6400
        deny_commands:
        - '[message] &cYou don''t have enough money for this!'
    #
    # Command(s) to execute when left-clicking the item while holding shift.
    # Those commands won't be executed when the above requirements aren't met.
    #
    # Read more:
    #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/item#shift-left-middle-right-click-commands
    # 
    shift_left_click_commands:
    - '[console] give %player_name% GOLD_BLOCK 64'
    - '[takemoney] 6400'
    - '[message] &aYou bought 64 &6GOLD_BLOCK &afor $6400'
    #
    # Requirement(s) when right-clicking an item while holding shift on the keyboard.
    #
    shift_right_click_requirement:
      requirements:
        #
        # "has item" checks if the player has the specified item in their inventory.
        # Except for "material" are all other values optional and will default to a specific value
        # which is either nothing (name) or 1 (amount).
        # We check for if the player has 64 gold blocks.
        #
        # Read more:
        #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/requirements#has-item
        #
        has_item:
          type: has item
          material: GOLD_BLOCK
          amount: 64
        deny_commands:
        - '[message] &cYou don''t have enough &6GOLD_BLOCK &cto sell! Required: 64'
    #
    # Command(s) to execute when right-clicking the item while holding shift.
    # Those commands won't be executed when the above requirements aren't met.
    #
    # Read more:
    #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/item#shift-left-middle-right-click-commands
    # 
    shift_right_click_commands:
    - '[console] clear %player_name% GOLD_BLOCK 64'
    - '[console] eco give %player_name% 3200'
    - '[message] &aYou sold 64 &6GOLD_BLOCK &afor $3200'
  #
  # Example 2: Free diamonds!
  #
  # This is a diamond, which will only be visible for people, that don't have the permission deluxemenus.free_diamonds.cooldown
  # When you click the item will you get a diamond and a permission is set (using LuckPerms) temporary (acts as cooldown) before
  # refreshing the GUI to update the displayed item.
  #
  'free_diamonds':
    material: DIAMOND
    slot: 1
    lore:
    - '&aFREE DIAMOND! [1/day]'
    - ''
    - '&7Click to get 1 free &bdiamond&7!'
    #
    # "priority" is used in case you have multiple items on the same slot.
    # A lower number equals a higher priority.
    #
    priority: 0
    #
    # view_requirement makes it possible to only display the item when the requirements are met.
    # When the requirements aren't met and a item with lower priority occupies the same slot, will it be displayed instead.
    #
    # Read more:
    #   https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations/item#view-requirement
    #
    view_requirement:
      requirements:
        has_not_perm:
          #
          # "!has permission" checks if the player does NOT have the specified permission.
          #
          type: "!has permission"
          permission: deluxemenus.free_diamonds.cooldown
    #
    # We give the item, set the permission with it expiring in 1 day and refresh the GUI to update the item.
    #
    left_click_commands:
    - '[console] give %player_name% DIAMOND 1'
    - '[console] lp user %player_name% permission settemp deluxemenus.free_diamonds.cooldown true 1d'
    - '[refresh]'
    #
    # We give the item, set the permission with it expiring in 1 day and refresh the GUI to update the item.
    #
    right_click_commands:
    - '[console] give %player_name% DIAMOND 1'
    - '[console] lp user %player_name% permission settemp deluxemenus.free_diamonds.cooldown true 1d'
    - '[refresh]'
  #
  # Example 3: Placeholder item
  #
  # This is a stone, that will be displayed as long as the player has the permission deluxemenus.free_diamonds.cooldown
  #
  'free_diamonds_cooldown':
    material: STONE
    slot: 1
    lore:
    - '&aFREE DIAMOND! [1/day]'
    - ''
    - '&cYou''re currently on cooldown. Click to refresh.'
    #
    # Higher number equals lower priority, meaning this item will only be displayed once the view_requirement of the
    # above isn't met anymore.
    #
    priority: 1
    #
    # We refresh the GUI to update the item, if the view_requirement no longer matches.
    #
    left_click_commands:
    - '[refresh]'
    #
    # We refresh the GUI to update the item, if the view_requirement no longer matches.
    #
    right_click_commands:
    - '[refresh]'
```
{% endcode %}
