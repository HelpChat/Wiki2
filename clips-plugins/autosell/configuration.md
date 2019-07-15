# Configuration

> ```
> # AutoSell version: 1.1 Main Configuration
> #
> # A fully customizable automatic toggleable shop/mining utility system where players can type /autosell to toggle
> # automatic selling while mining if in mines/regions that have shops associated with them.
> # If no mine/region integration is enabled, players will be able to autosell in any enabled worlds if they have permission to access a > shop
> # playe.
> # You can create as many shop lists you want. Each shop must have a unique priority set
> # with 1 being the highest priority (if permissions are used). You can also configure if players can only get paid in certain
> # mines/regions!
> hooks:
>   mine_reset_lite:
>     enabled: true
>   worldguard:
>     enabled: false
> tools_never_break: true
> autosell:
>   allow_creative: false
>   require_tools: true
>   take_sold_items: true
>   disabled_worlds:
>   - someworld
>   - someotherworld
>   multipliers_enabled: true
>   interval_announcements:
>     enabled: true
>     interval: 60
>     has_multiplier_message:
>     - '&8&m-----------------------------------------------------'
>     - '&eYour AutoSell stats...'
>     - '&bItems Sold&7: &f%items%'
>     - '&bAmount&7: &a$&f%amount%'
>     - '&bMultiplier: &f%multiplier%'
>     - '&8&m-----------------------------------------------------'
>     no_multiplier_message:
>     - '&8&m-----------------------------------------------------'
>     - '&eYour AutoSell stats...'
>     - '&bItems Sold&7: &f%items%'
>     - '&bAmount&7: &a$&f%amount%'
>     - '&8&m-----------------------------------------------------'
> signsell:
>   has_multiplier_message:
>   - '&8&m-----------------------------------------------------'
>   - '&bItems Sold&7: &f%items%'
>   - '&bAmount&7: &a$&f%amount%'
>   - '&bMultiplier: &f%multiplier%'
>   - '&8&m-----------------------------------------------------'
>   no_multiplier_message:
>   - '&8&m-----------------------------------------------------'
>   - '&bItems Sold&7: &f%items%'
>   - '&bAmount&7: &a$&f%amount%'
>   - '&8&m-----------------------------------------------------'
> sellall:
>   enabled: true
>   use_perm_shop_when_no_shop_is_at_location: true
>   has_multiplier_message:
>   - '&8&m-----------------------------------------------------'
>   - '&bItems Sold&7: &f%items%'
>   - '&bAmount&7: &a$&f%amount%'
>   - '&bMultiplier: &f%multiplier%'
>   - '&8&m-----------------------------------------------------'
>   no_multiplier_message:
>   - '&8&m-----------------------------------------------------'
>   - '&bItems Sold&7: &f%items%'
>   - '&bAmount&7: &a$&f%amount%'
>   - '&8&m-----------------------------------------------------'
> item_drops:
>   drops2inv:
>     enabled: true
>     autosell_areas_only: false
>     disabled_worlds:
>     - someworld
>     - someotherworld
>   silk_touch:
>     enabled: true
>   auto_smelt:
>     enabled: true
>     toggle_on_join: true
>     disabled_worlds:
>     - someworld
>     - someotherworld
>     smelt_list:
>     - GOLD_ORE,GOLD_INGOT
>     - IRON_ORE,IRON_INGOT
>     - WOOL;3,WOOL;5
>     - STONE,STONE
>   fortune:
>     enabled: true
>     max_fortune_drops: 100
>     disabled_worlds:
>     - someworld
>     - someotherworld
>     fortune_blocks:
>     - DIAMOND_ORE
>     - EMERALD_ORE
>     - GOLD_ORE
>     - IRON_ORE
>     - LAPIS_ORE
>     - REDSTONE_ORE
>     - QUARTZ_ORE
>     - COAL_ORE
>     - DIAMOND_BLOCK
>     - EMERALD_BLOCK
>     - GOLD_BLOCK
>     - IRON_BLOCK
>     - LAPIS_BLOCK
>     - REDSTONE_BLOCK
>     - QUARTZ_BLOCK
>     - COAL_BLOCK
>   ingot_to_block:
>     enabled: true
>     toggle_on_join: true
> shops:
>   Shop1:
>     priority: 1
>     shop_list:
>     - STONE,0.50
>     - COBBLESTONE,0.20
>     - IRON_ORE,0.35
>     - COAL_ORE,0.20
> ```
