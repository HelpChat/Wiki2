---
description: All item related options & configurations
---

# Item

## Syntax

> ```yaml
> items:
>   "ItemName":
>     material: TEXT
>     slot: #
> ```

**Note:**\
Each item will have a name, in this example our item is called **`ItemName`.** This name **should** be unique, so there won't be two or more items with the same name.

## Material

> ```yaml
> material: TEXT
> ```
>
> > **Supported material values:**
> >
> > * [Material name](./#useful-links) (`STONE`).
> > * Player head (`head-extended_clip`).
> >   * Placeholder head (`head-%player_name%`, `basehead-%player_basehead_placeholder%`, etc.).
> > * Argument placeholder head (`head-{target}`).
> > * [BaseHead](https://minecraft-heads.com) (`basehead-<base64 (Value field in the head's give command)>`).
> > * Minecraft Texture (`texture-<id>`)\
> >   \- The `id` is what's after `https://textures.minecraft.net/textures/`
> > * [HeadDatabase](https://www.spigotmc.org/resources/14280/) (`hdb-<ID>`).
> > * [ItemsAdder](https://www.spigotmc.org/resources/%E2%9C%A8itemsadder%E2%AD%90emotes-mobs-items-armors-hud-gui-emojis-blocks-wings-hats-liquids.73355/) material (`itemsadder-namespace:name`)
> > * [Oraxen](https://www.spigotmc.org/resources/72448/) material (`oraxen-oraxen_item_id`)
> > * [ExecutableItems](https://www.spigotmc.org/resources/custom-items-plugin-executable-items.77578/) material (`executableitems-item_id`)
> > * [ExecutableBlocks](https://www.spigotmc.org/resources/custom-blocks-plugin-executable-blocks.93406/) material (`executableblocks-item_id`)
> > * [MMOItems] (https://www.spigotmc.org/resources/mmoitems.39267/) material (`mmoitems-item_id`)
> > * [Placeholder](https://helpch.at/placeholders) material (`placeholder-%player_item_in_hand%`).
> > * Item in main hand (`main_hand`).
> > * Item in off hand (`off_hand`).
> > * Items in armor equipment slots (`armor_helmet`, `armor_chestplate`, `armor_leggings` and `armor_boots`)
> > * Water bottle material is: `water_bottle`
> > * Air material is: `air`

Sets the material of the item in the menu.

{% hint style="success" %}
AIR is a valid material. The item will be an empty slot with click commands and click requirements working.
{% endhint %}

{% hint style="success" %}
Placeholders are supported for head, basehead, texture, hdb, itemsadder, oraxen and placeholder materials!
{% endhint %}

{% hint style="warning" %}
For version 1.12.2 or older:\
Check [Data](item.md#data) option to specify the data of the item (the number after the colon `:`). e.g. Lime Wool would be

```yaml
material: WOOL
data: 5
```
{% endhint %}

## Data

> ```yaml
> data: #
> ```
>
> > **Supported data values:**
> >
> > * Number (`1`).
> > * Placeholder that returns a number (`placeholder-%player_item_in_hand_data%`).

Sets the durability of the item (depends on the [Material](item.md#material) option).

{% hint style="info" %}
For version 1.12.2 or older:\
This option will specify the [data value](https://minecraft-el.gamepedia.com/Data\_values) (the number after the colon `:`) of the item or the item's durability (depends on the [Material](item.md#material) option).
{% endhint %}

## Amount

> ```yaml
> amount: #
> ```

Sets the item's amount in the menu.

### Dynamic Amount

> ```yaml
> dynamic_amount: '%placeholder%'
> ```

Sets the item's amount in the menu using a [placeholder](https://helpch.at/placeholders).

## Model Data

> ```yaml
> model_data: #
> ```

Allows you to set a CustomModelData for your item. Example of usage:\
`model_data: 14` (Can also support negative value)

## NBT Tags

> ```yaml
> nbt_string: '<Key>:<StringValue>'
> nbt_strings:
> - '<Key>:<StringValue>'
> - '<Key>:<StringValue>'
> nbt_int: '<Key>:<IntegerValue>'
> nbt_ints:
> - '<Key>:<IntegerValue>'
> - '<Key>:<IntegerValue>'
> ```

Allows you to add custom NBT tags to your items like model data.

{% hint style="danger" %}
Deprecated! Should use the new [model\_data](item.md#model-data) option instead for CustomModelData. You can still use it for other tags tho.
{% endhint %}

{% hint style="success" %}
The nbt tags options support PlaceholderAPI placeholders now!
{% endhint %}

## Banner Meta

> ```yaml
> banner_meta:
> - <dyecolor>;<patterntype>
> - <dyecolor>;<patterntype>
> ```
>
> > * [Dye colors list](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/DyeColor.html).
> > * [Pattern types list](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/block/banner/PatternType.html).

Allows you to create your custom banners and shields.

{% hint style="success" %}
Now with support for SHIELDS! Make sure to also check the new [base\_color](item.md#base-color) option.
{% endhint %}

## Base Color

> ```yaml
> base_color: <dyecolor>
> ```
>
> > * [Dye colors list](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/DyeColor.html).

Allows you to specify base colors for shields and also for banners on 1.12.2 and lower versions.

## Armor Trims

> ```yaml
> trim_material: <trim>
> trim_pattern: <pattern>
> ```
>
> > * [Trim material list](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/meta/trim/TrimMaterial.html).
> > * [Trim pattern list](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/meta/trim/TrimPattern.html).

Allows you to set a trim and a pattern to an armor piece

{% hint style="success" %}
These options are case-sensitive and support placeholders and arguments.
{% endhint %}

## Item Flags

> ```yaml
> item_flags:
> - <ItemFlag>
> - <ItemFlag>
> ```
>
> > * [Item Flags list.](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/inventory/ItemFlag.html)

Allows you to set item flags.

## Potion Effects

> ```yaml
> potion_effects:
> - <PotionEffectType>;<duration>;<amplifier>
> - <PotionEffectType>;<duration>;<amplifier>
> ```
>
> > * [Potion effects list.](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/potion/PotionEffectType.html)

Allows you to set effects (Used if the [material](item.md#material) is a potion, splash\_potion and tipped arrows).

{% hint style="success" %}
Potion Effects no longer require the [RGB](item.md#rgb) option to be set to work!
{% endhint %}

## Entity Type

> ```yaml
> entity_type: <entitytype>
> ```
>
> > * [Entity types list.](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html)

This is mainly targeted for 1.12.2 and lower server versions and allows you to specify monster egg types and monster spawner types.

{% hint style="danger" %}
Option was removed in versions 1.14.0 and newer of the plugin due to versions 1.13.1 and lower of Minecraft no longer being supported.
{% endhint %}

## RGB <a href="#rgb" id="rgb"></a>

> ```yaml
> rgb: #, #, #
> ```
>
> > **Example:**
> >
> > ```yaml
> > rgb: 38, 192, 210
> > ```

Sets the RGB (Red, Green, Blue) color for leather armor, potions, splash potions, tipped arrows and firework stars

{% hint style="info" %}
For RGB option to work on potions and tipped arrows you also need to give it at least one  [potion\_effect](item.md#potion-effects).
{% endhint %}

{% hint style="success" %}
You can find a list of default potion colors [`HERE`](https://minecraft.fandom.com/wiki/Effect\_colors/Potions\_table). You will have to use an online converter to convert the hex values to rgb.
{% endhint %}

## Display Name

> ```yaml
> display_name: "TEXT"
> ```

Sets the item's display name. You can use [placeholders](https://helpch.at/placeholders) and color/format codes.

## Lore

> ```yaml
> lore:
>   - "TEXT"
>   - "TEXT"
> ```

Sets the item's lore (the text shown under the item's name). You can use [placeholders](https://helpch.at/placeholders) and color/format codes and the new line character (`\n`) in this option.

## Slot

> ```yaml
> slot: #
> ```
>
> > **Multiple slots:**
> >
> > ```yaml
> > slots:
> >   - #
> >   - #
> >   - #
> >   
> > # OR
> >   
> > slots:
> >   - #-#
> >   - #-#
> > ```

Sets in which slot the item should be inside the menu.

{% hint style="info" %}
* Slots start at 0.
* Multiple items can be in the same slot, but you'll have to use [view requirement](item.md#view-requirement) and [priority](item.md#priority) options to work properly.
{% endhint %}

![Slots number in a chest](https://i.imgur.com/lr41ykP.png)

## Priority

> ```yaml
> priority: #
> ```

Sets the item priority. It's used if you want different items in the same slot (by using the [view requirement ](item.md#view-requirement)option).\
The item that has the highest priority will be checked first if the player has the required view requirement. It will display the item if they have the requirements and if not, it will check the next item and so on.

{% hint style="info" %}
* The highest priority is 0.
* The lowest priority is 2147483647.
{% endhint %}

## View Requirement

> ```yaml
> view_requirement: 'EXPRESSION'
> ```

Sets the requirements the player should have to see the item. (Check [priority](item.md#priority) option for setting up multiple items in the same slot).\
Check the [Requirements](requirements.md) page for more info about this option's value and how to use it.

## Update

> ```yaml
> update: BOOLEAN # true or false
> ```

If set to true, it will update the placeholders in the item's [display name](item.md#display-name) and [lore](item.md#lore) **only**.\
Check the [update interval](gui.md#update-interval) GUI option to set the update speed.

![An example showing how the update option works in placeholders](https://i.imgur.com/iOKtT2A.gif)

## Enchantments

> ```yaml
> enchantments:
>   - enchantmentid;level
>   - enchantmentid;level
> ```
>
> > * [Enchantments list](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html).

Enchants the item with the specified enchantments. (Check the [hide enchantments](item.md#hide-enchantments) option to hide the enchantments)

{% hint style="warning" %}
Some items cannot have the enchanting glow effect
{% endhint %}

## Hide Enchantments

> ```yaml
> hide_enchantments: BOOLEAN # true or false
> ```

If set to true, it will hide the enchantments you set for the item using the [enchantments](item.md#enchantments) option from the item's tooltip (lore).\
Used to add the enchanting glow effect to the item without showing the enchantments text.

## Hide Attributes

> ```yaml
> hide_attributes: BOOLEAN # true or false
> ```

If set to true, it will hide the vanilla attributes of an item/armor (e.g. **7 Attack Damage**).

## Hide Effects

> ```yaml
> hide_effects: BOOLEAN # true or false
> ```

If set to true, it will hide the potion's effect text beneath the item name.

## Hide Unbreakable

> ```yaml
> hide_unbreakable: BOOLEAN # true or false
> ```

If set to true, it will hide the unbreakable tag if the "unbreakable:" option is enabled.

## Unbreakable

> ```yaml
> unbreakable: BOOLEAN # true or false
> ```

If set to true, it will show the item to be at full durability.

## (Shift) Left/Middle/Right click Commands

> ```yaml
> # click_commands: or
> # left_click_commands: or
> # right_click_commands: or
> # middle_click_commands: or
> # shift_left_click_commands: or
> shift_right_click_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> ```

Sets the actions/commands that should be executed once the player clicks the item. they get executed in order from top to bottom.\
Check [this](./#action-types) for all action types and action tags.

{% hint style="danger" %}
Middle clicking was removed by Mojang in 1.18 and newer!
{% endhint %}

## (Shift) Left/Middle/Right click Requirement

> ```yaml
> # click_requirement: or
> # left_click_requirement: or
> # right_click_requirement: or
> # middle_click_requirement: or
> # shift_left_click_requirement: or
> shift_right_click_requirement:
>   requirements: 'EXPRESSION'
>   deny_commands:
>     - "[ACTIONTYPE] ACTION"
>     - "[ACTIONTYPE] ACTION"
> ```

Sets the requirements the player should have to click the item (Check the [Requirements](requirements.md) page for more info about the `EXPRESSION` value).\
Deny commands (optional) are the actions that are going to be executed if the player doesn't have the required requirements. But if (s)he does, it will execute the actions specified in the [click commands](item.md#shift-left-middle-right-click-commands) option.

{% hint style="info" %}
You can have deny commands per requirement. Check [this page](requirements.md#syntax) for more information.
{% endhint %}

Check [this](./#action-types) for all action types and action tags.
