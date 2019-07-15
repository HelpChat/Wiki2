# Item

As a reminder, Here is what your syntax should look like with items. Be aware this varies depending on the amount of items and options:

> ```yaml
>    items:
>     'ItemName':
>       material: TEXT
>       slot: #
> ```

**Note:** Be aware that the **'ItemName':** can be anything you want, and does not effect the configuration at all. It is for you to have identifiers. It could be a simple number \(like in the default config\) or it could be a random string of text.  
If you want to use a number as name, make sure, to have it in `''` \(Example: `'1':`\).  
Each item-name NEEDS to be unique! You can't have two items with the same name.

### Navigation

* [Material](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#material)
* [Data](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#data)
* [Amount](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#amount)
* [Dynamic\_amount](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#dynamic_amount)
* [RGB](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#rgb)
* [Slot](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#slot)
* [Priority](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#priority)
* [View Requirement](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#view-requirement)
* [Update](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#update)
* [Banner Meta](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#banner-meta)
* [Enchantments](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#enchantments)
* [Hide Enchantments](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#hide-enchantments)
* [Hide Attributes](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#hide-attributes)
* [Hide Effects](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#hide-effects)
* [Display Name](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#display-name)
* [Lore](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#lore)
* [\(Shift\) Left/Middle/Right click Commands](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#shift-leftmiddleright-click-commands)
* [\(Shift\) Left/Middle/Right click Requirements](https://github.com/help-chat/Wiki2/tree/65338947e0f3c92e111d8f5ec8d111bd6852b3a0/clips-plugins/deluxemenus/Item.md#shift-leftmiddleright-click-requirement)

#### Material

> ```yaml
> material: TEXT
> ```

This option tells what material should be used for the item \(The list of valid materials is available at the top of this page\). This corresponds directly with the "data" tag \(If you have something like potions or wool that have data\). It can also interact with the `banner-meta` tag if you use a banner material. You can also use a player head by doing `head;username`. The default config shows how you can use a player placeholder to create a dynamic item \(`head;%player_name%`\). Examples:

> `material: WOOL`  
> `material: head;extended_clip`  
> `material: head;%player_name%`  
> `material: basehead-eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvNjIxNjY4ZWY3Y2I3OWRkOWMyMmNlM2QxZjNmNGNiNmUyNTU5ODkzYjZkZjRhNDY5NTE0ZTY2N2MxNmFhNCJ9fX0=` \(The code afer `basehead-` can be found [here](https://minecraft-heads.com) on the `Value` field of each head\) `material: heads-123` \(Require [EpicHeads](https://www.spigotmc.org/resources/13402/)\) [![](https://img.shields.io/badge/Ver-1.10.2+-brightgreen.svg)](https://www.spigotmc.org/resources/11734/update?update=192553)  
> `material: hdb-123` \(Require [HeadDatabase](https://www.spigotmc.org/resources/14280/)\) [![](https://img.shields.io/badge/Ver-1.9.2+-brightgreen.svg)](https://www.spigotmc.org/resources/11734/update?update=174476)  
> `material: 'placeholder-%player_item_in_hand%'` \(or any other placeholder that returns a valid item name\) [![](https://img.shields.io/badge/Ver-1.10.4+-brightgreen.svg)](https://www.spigotmc.org/resources/11734/update?update=221012)

#### Data

> ```yaml
> data: #
> ```

This corresponds with the material tag. It simply defines the data for any block or defines the damage value of an item. Wool is the most common example. You will need to find the data number using a page like [this](https://minecraft.gamepedia.com/Data_values). However, Doing a simple google search, you should easily find data values for anything you need. Examples:

> `data: 1`  
> `data: 'placeholder-%player_item_in_hand_data%'` \(or any other placeholder that returns a valid number\) [![](https://img.shields.io/badge/Ver-1.10.4+-brightgreen.svg)](https://www.spigotmc.org/resources/11734/update?update=221012) This option is used in MC version 1.13+ to defines the damage value ONLY.

#### Amount

> ```yaml
> amount: #
> ```

This tag defines the amount of the item \(for example 32\)

#### Dynamic\_amount

> ```yaml
> dynamic_amount: '%placeholder%'
> ```

To set the amount using a placeholder. This is useful for doing things like a lobby selector. [![](https://img.shields.io/badge/Ver-1.6.0+-brightgreen.svg)](https://www.spigotmc.org/resources/11734/update?update=93497)

#### RGB

> ```yaml
> rgb: #,#,#
> ```

To set the RGB \(Red, Green, Blue\) to a leather armor. [![](https://img.shields.io/badge/Ver-1.11.0+-brightgreen.svg)](https://www.spigotmc.org/resources/11734/update?update=279055)

For example:

> `rgb: 38,192,210`
>
> ![Image of what will be displayed](https://img.aboodyy.net/19.06.19_01-07.png)

#### Slot

> ```yaml
> slot: #
> ```

To put the same item in multiple slots use this:

> ```yaml
> slots:
> - #
> - #
> ```

This tag tells which slot\(s\) of the inventory the item should be in. Items can be put in the same slot, but you will need to use the priority and view\_requirement tags to make them work properly. Remember that an inventory can have up to 54 slots, but the first position \(from the top left\) starts at 0. So, The 9th slot is actually slot 8. This is how minecraft has things setup, and we can not change it. Here is an image to help explain it:

![CHEST](https://i.imgur.com//lr41ykP.png)

#### Priority

> ```yaml
> priority: #
> ```

This tag tells which item should have priority when in the same slot as another item \(Corresponds with the slot and view\_requirement tag\). The larger the number...the lower the priority. So, an item with a priority of 5 will not show if another item has a priority of 2, and both would be covered up by an item with a priority of 1.

#### View Requirement

> ```yaml
> view_requirement: 'EXPRESSION'
> ```

This tag corresponds with the priority and slot tag. This feature give you able to view the item if player have for example a specific permission, amount of money, etc. See \[\[this page\|Requirements\]\] for more information about it.

#### Update

> ```yaml
> update: BOOLEAN # true or false
> ```

If this is set to true it will update any placeholders in the item display name and lore. The frequency of updates is determined by the GUI Option "update\_interval". This is especially useful with statistics and cooldowns.  
**This does NOT switch the item if for example view requirements are \(not\) met!**

Here is an example image showing how the update works in placeholders:

![UPDATE](https://i.imgur.com/iOKtT2A.gif)

#### Banner Meta

> ```yaml
> banner_meta:
> - <dyecolor>;<patterntype>
> - <dyecolor>;<patterntype>
> ```

This tag will only be used if the material tag is set as a banner. It allows you to create your own patterns using the [dye colors](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/DyeColor.html) and [pattern types](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/block/banner/PatternType.html). You can stack them to create unique designs. It is very important that you use a semi-colon \(`;`\) and not a regular colon as the divider in these lines.

#### Enchantments

> ```yaml
> enchantments:
> - enchantmentid;level
> - enchantmentid;level
> ```

This tag is used to define [enchantments](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html) on the item. Be aware that some items/blocks can not be enchanted, and others can only use certain enchantments. If you wish to hide the text and just have the effect you can use the **hide\_enchantments:** tag.

#### Hide Enchantments

> ```yaml
> hide_enchantments: BOOLEAN # true or false
> ```

This tag corresponds with the enchantments tag. If set to true it will hide the enchantment list on an item. This is useful for if you want an item to have the enchanted effect, but not the annoying text that is added.

#### Hide Attributes

> ```yaml
> hide_attributes: BOOLEAN # true or false
> ```

This tag will hide any vanilla attributes of an item. All tools \(Swords, Picks, Axes, ETC.\) show things like "+5 Attack" on them. \(Since 1.9+\) This tag \(when set to true\) will hide those things.

#### Hide Effects

> ```yaml
> hide_effects: BOOLEAN # true or false
> ```

Very similar to the **hide\_attributes** tag, except that it works with things like potions which have an effect listed beneath the name. Useful when you need a potion \(rather than just a bottle of water\), but none of the added text.

#### Display Name

> ```yaml
> display_name: 'TEXT'
> ```

This tag will be the display name for the item. You can use [placeholders](https://helpch.at/placeholders) and color/format codes.

#### Lore

> ```yaml
> lore:
> - 'TEXT'
> - 'TEXT'
> ```

This tag defines what will be shown in the lore area of the item. You can use [placeholders](https://helpch.at/placeholders) and color/format codes in this area. You can add as many lines as minecraft allows.

#### \(Shift\) Left/Middle/Right click Commands

> \`\`\`yaml
>
> ## left\_click\_commands: or
>
> ## right\_click\_commands: or
>
> ## middle\_click\_commands: or
>
> ## shift\_left\_click\_commands: or
>
> shift\_right\_click\_commands:
>
> * '\[player\] COMMAND'
> * '\[console\] COMMAND'
> * '\[commandevent\] COMMAND'
> * '\[message\] TEXT'
> * '\[openguimenu\] MenuName'
> * '\[connect\] ServerName'
> * '\[close\]'
> * '\[json\] {"text":"message"}'
> * '\[refresh\]'
> * '\[broadcastsound\] SOUND'
> * '\[sound\] SOUND'
> * '\[takemoney\] \#'

These tags are fairly self explanatory. left\_click\_commands controls what happens if a player left clicks an item, and right\_click\_commands controls what happens if they right click the item, and middle\_click\_commands controls what happens if they click the middle button on the mouse, and shift\_left\_click\_commands controls what happens if they left click with clicking shift key, and shift\_right\_click\_commands controls what happens if they right click with clicking shift key. You can have as many lines as you want. Commands execute in order from top to bottom. There are several available types of commands. Here they are listed below \(Be aware that all tags should have a space before the text or commands\):

**Normal tags**

| Tag | Description |
| :--- | :--- |
| `[player] <command>` | Executes a command as a player |
| `[console] <command>` | Executes a command as the console |
| `[commandevent] <command>` | Executes a special command event like the ones used by MyCommand Aliases |
| `[message] <text>` | Sends a message to the player. You can use placeholders and color/format codes here |
| `[openguimenu] <menu>` | Opens another GUI from DeluxeMenus. Just add the correct menu title |
| `[connect] <server>` | Connects the player to a Server on the same BungeeCord. |
| `[close]` | Closes the currently open GUI |
| `[json] <JSON-text>` | Send a json message to the menu viewer |
| `[refresh]` | Refresh items in the current menu view. This updates the shown Items itself |
| `[broadcastsound] <sound>` | Broadcast a sound to all players on the server |
| `[sound] <sound>` | Play a sound for a the viewer of the menu |
| `[takemoney] <amount>` | Take a certain amount of money from the menu viewer. Vault is required |

**Special tags**

Those tags are used TOGETHER with a normal tag, to change the behaviour of the command, like f.e. delay the execution. \(eg. `[message] 1 second later<delay=20>`\)

| Tag | Description |
| :--- | :--- |
| `<delay=<time>>` | Sets a delay \(in ticks\) after which the action will be executed. |
| `<chance=<chance>>` | set a chance to run the command. |

#### \(Shift\) Left/Middle/Right click Requirement

> ```yaml
> # left_click_requirement: or
> # right_click_requirement: or
> # middle_click_requirement: or
> # shift_left_click_requirement: or
> shift_right_click_requirement:
>   requirements: 'EXPRESSION'
>   deny_commands:
>   - '[player] COMMAND'
>   - '[console] COMMAND'
>   - '[commandevent] COMMAND'
>   - '[message] TEXT'
>   - '[openguimenu] MenuName'
>   - '[connect] ServerName'
>   - '[close]'
>   - '[json] {"text":"message"}'
>   - '[refresh]'
>   - '[broadcastsound] SOUND'
>   - '[sound] SOUND'
>   - '[takemoney] #'
> ```

Checks a requirement using a java/placeholder expression/comparison using the same format as the \[\[view_requirement\|Item\#view-requirement\]\] tag. Except in this case the player can see the item, but it checks if \(s\)he can left, middle, right, shift + left or shift + right click it.  
Deny commands are completely optional, but if you use them they work exactly the same as the normal \(shift_\)left_click\_commands, middle\_click\_commands and \(shift_\)right_click\_commands tag. If the requirement is met they will execute the commands defined under the \(shift_\)left/middle/right\_click\_commands. If the requirement is not met it will instead execute the deny commands \(or no commands if you did not define any\).

