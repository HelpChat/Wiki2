---
description: All item related options & configurations
---

[Base64]: https://minecraft-heads.com
[EpicHeads]: https://songoda.com/marketplace/product/26
[HeadDatabase]: https://www.spigotmc.org/resources/14280/
[Placeholder]: https://helpch.at/placeholders
[Data]: https://minecraft-el.gamepedia.com/Data_values

[Colors]: https://hub.spigotmc.org/javadocs/spigot/org/bukkit/DyeColor.html
[Patterns]: https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html
[Enchantments]: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/enchantments/Enchantment.html

# Item

## Syntax

> ```yaml
> items:
>   "ItemName":
>     material: TEXT
>     slot: #
> ```

**Note:**  
Each item will have a name, in this example our item is called **`ItemName`**. This name **should** be unique, so there won't be two or more items with the same name.

## Material

> ```yaml
> material: TEXT
> ```
>
> > **Supported material values:**
> >
> > * [Material name](./#useful-links) (`STONE`).
> > * Player head (`head;extended_clip`).
> > * Placeholder head (`head;%player_name%`).
> > * Argument placeholder head (`head;{target}`).
> > * [Base64] head (`basehead-<base64 (Value field in the head's give command)>`).
> > * [EpicHeads] head (`heads-<ID>`).
> > * [HeadDatabase] head (`hdb-<ID>`).
> > * [Placeholder] material \(`placeholder-%player_item_in_hand%`\ [Placeholder needs to return a material name]).

Sets the material of the item in the menu.

{% hint style="info" %}
For version 1.12.2 or older:  
Check [Data](#data) option to specify the data of the item (the number after the colon `:`). e.g. Lime Wool would be

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
> > * [Placeholder] that returns a number (`placeholder-%player_item_in_hand_data%`).

Sets the durability of the item (depends on the [Material](#material) option).

{% hint style="info" %}
For version 1.12.2 or older:  
This option will specify the [data value][Data] (the number after the colon `:`) of the item or the item's durability (depends on the [Material](#material) option).
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

Sets the item's amount in the menu using a [placeholders][Placeholder].

## Banner Meta

> ```yaml
> banner_meta:
> - <dyecolor>;<patterntype>
> - <dyecolor>;<patterntype>
> ```
>
> > * [Dye colors][Colors]
> > * [Banner Patterns][Patterns]

Allows you to create your custom banner (Used if the [material](#material) is a banner).

## RGB <a id="rgb"></a>

> ```yaml
> rgb: #,#,#
> ```
>
> > **Example:**
> >
> > ```yaml
> > rgb: 38,192,210
> > ```
> >
> > ![Image of what will be displayed](https://img.aboodyy.net/19.06.19_01-07.png)

Sets the RGB (Red, Green, Blue) color for leather armor.

## Display Name

> ```yaml
> display_name: "TEXT"
> ```

Sets the item's display name. You can use [placeholders][Placeholder] and color/format codes.

## Lore

> ```yaml
> lore:
>   - "TEXT"
>   - "TEXT"
> ```

Sets the item's lore (the text shown under the item's name\). You can use [placeholders][Placeholder] and color/format codes in this area.

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
> > ```

Sets in which slot(s) the item should be inside the menu.

{% hint style="info" %}
* Slots start at 0.
* Multiple items can be in the same slot, but you'll have to use [view requirement](#view-requirement) and [priority](#priority) options to work properly.
{% endhint %}

![Slots number in a chest](https://i.imgur.com//lr41ykP.png)

## Priority

> ```yaml
> priority: #
> ```

Sets the item priority. It's used if you want different items in the same slot \(by using the [view requirement ](item.md#view-requirement)option\).  
The item that has the highest priority will be checked first if the player has the required view requirement. It will display the item if they have the requirements and if not, it will check the next item and so on.

{% hint style="info" %}
* The highest priority is 0.
* The lowest priority is 2147483647.
{% endhint %}

## View Requirement

> ```yaml
> view_requirement: 'EXPRESSION'
> ```

Sets the requirements the player should have to see the item. (Check [priority](#priority) option for setting up multiple items in the same slot).  
Check the [Requirements](requirements.md) page for more info about this option's value and how to use it.

## Update

> ```yaml
> update: BOOLEAN # true or false
> ```

If set to true, it will update the placeholders in the item's [display name](#display-name) and [lore](#lore) **only**.  
Check the [update interval](#update-interval) GUI option to set the update speed.  
**This won't update the displayed item itself! Use the [\[refresh\] command](#shift-leftmiddleright-click-commands) to update the item.**

![An example showing how the update option works in placeholders](https://i.imgur.com/iOKtT2A.gif)

## Enchantments

> ```yaml
> enchantments:
>   - enchantmentid;level
>   - enchantmentid;level
> ```
>
> > * [Enchantments list][Enchantments]

Enchants the item with the specified enchantments. (Check the [hide enchantments](#hide-enchantments) option to hide the enchantments)

{% hint style="warning" %}
Some items cannot have the enchanting glow effect
{% endhint %}

## Hide Enchantments

> ```yaml
> hide_enchantments: BOOLEAN # true or false
> ```

If set to true, it will hide the enchantments you set for the item using the [enchantments](#enchantments) option from the item's tooltip (lore).  
Used to add the enchanting glow effect to the item without showing the enchantments text.

## Hide Attributes

> ```yaml
> hide_attributes: BOOLEAN # true or false
> ```

If set to true, it will hide the vanilla attributes of an item/armor (e.g. **# Attack Damage**).

## Hide Effects

> ```yaml
> hide_effects: BOOLEAN # true or false
> ```

If set to true, it will hide the potion's effect text beneath the item name.

## (Shift) Left/Middle/Right click Commands

> ```yaml
> # left_click_commands: or
> # right_click_commands: or
> # middle_click_commands: or
> # shift_left_click_commands: or
> shift_right_click_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> ```

Sets the actions/commands that should be executed once the player clicks the item. they get executed in order from top to bottom.  
Check [this](./#action-tags) for all action types and action tags.

## (Shift) Left/Middle/Right click Requirement

> ```yaml
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

Sets the requirements the player should have to click the item (Check the [Requirements](requirements.md) page for more info about the `EXPRESSION` value).  
Deny commands (optional) are the actions that are going to be executed if the player doesn't have the required requirements. But if \(s\)he does, it will execute the actions specified in the [click commands](#shift-left-middle-right-click-commands) option.

Check [this](./#action-tags) for all action types and action tags.

