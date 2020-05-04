---
description: All GUI menu related options & configurations
---

# GUI

## Syntax

> ```yaml
> gui_menus:
>   menuname:
>     menu_title: "TEXT"
>     open_command: COMMAND
>     open_requirement: EXPRESSION
>     open_commands:
>       - "[ACTIONTYPE] ACTION"
>       - "[ACTIONTYPE] ACTION"
>     inventory_type: "TEXT"
>     size: #
>     update_interval: #
>     items:
> ```

{% hint style="info" %}
If you're using an external GUI-file \(separate `.yml` file\) your configuration will start at the `menu_title:` option.
{% endhint %}

## Menu Title

> ```yaml
> menu_title: "TEXT"
> ```

The menu title that is shown at the top of the GUI. You can use color and formatting codes here, and PlaceholderAPI placeholders.

## Open Command

> ```yaml
> open_command: COMMAND
> ```
>
> > **Multiple open commands:**
> >
> > ```yaml
> > open_command:
> >   - COMMAND
> >   - COMMAND_2
> > ```

The command used to open the GUI menu. It can only be a single word.

{% hint style="info" %}
To disable the open command, simply delete the line of this option.
{% endhint %}

## Open Requirements

> ```yaml
> open_requirement:
>  requirements:
>    TEXT:
>      type: <type>
> ```

Sets requirements a player should have to open the GUI menu. Check the [Requirements](requirements.md) page for more info.

## Open Commands

> ```yaml
> open_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> ```

Runs the command\(s\) you set when the player opens the menu.

## Close Commands

> ```yaml
> close_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> ```

Runs the command\(s\) you set when the player close the menu by clicking an item with close action \(`[close]`\).

## Inventory Type

> ```yaml
> inventory_type: "TEXT"
> ```
>
> > **Default value:** `CHEST`  
> > **Supported types:**
> >
> > * `ANVIL`
> > * `BARREL`
> > * `BEACON`
> > * `BLAST_FURNACE`
> > * `BREWING`
> > * `CARTOGRAPHY`
> > * `DISPENSER`
> > * `DROPPER`
> > * `ENCHANTING`
> > * `ENDER_CHEST`
> > * `FURNACE`
> > * `GRINDSTONE`
> > * `HOPPER`
> > * `LOOM`
> > * `PLAYER`
> > * `SHULKER_BOX`
> > * `SMOKER`
> > * `WORKBENCH`

Allows you to define a different type of Inventory.

## Size

> ```yaml
> size: #
> ```
>
> > **Default value:** `54`  
> > **Supported values:**
> >
> > * `9`
> > * `18`
> > * `27`
> > * `36`
> > * `45`
> > * `54`

Sets the inventory size.

{% hint style="info" %}
Size option should be always set, but it doesn't work for all [inventory types](gui.md#inventory-type).
{% endhint %}

## Args \(Arguments\) <a id="args"></a>

> ```yaml
> args:
> - "TEXT"
> - "TEXT"
> - "TEXT"
> ```
>
> > * **TEXT** The argument name \(Should be unique\).

Gives you the ability to set arguments after the [open command](gui.md#open-command), and use them inside the menu by adding the argument placeholder \(the argument name inside curly braces `{TEXT}`\).

You can have multiple arguments, and they will be set in the same order in the open command.

```text
/COMMAND FirstArg SecondArg And the rest
```

```yaml
args:
- first
- second
- last
```

* `{first}` returns `FirstArg`
* `{second}` returns `SecondArg`
* `{last}` returns `And the rest`

{% hint style="info" %}
* Argument placeholders can be used in [Placeholder-Material](item.md#material), [Display Name](item.md#display-name), [Lore](item.md#lore), and [Actions](item.md#shift-left-middle-right-click-commands) only.
* It's highly recommended to add [Args Usage Message](gui.md#args-usage-message) option.

{% endhint %}

## Args Usage Message

> ```yaml
> args_usage_message: "TEXT"
> ```

Sets the usage message for the menu. If the player didn't set the required arguments. It will be sent to the player if he didn't set the arguments. You can use color and formatting codes here.

## Update Interval

> ```yaml
> update_interval: #
> ```

This is for any items that use the `update:` option \(Check it [here](item.md#update)\).  
The number defines the delay \(in seconds\) between each refresh of the placeholders in an item's lore/display name.

**Note:** This refreshes/updates the placeholders only.

## Items

> ```yaml
> items:
> ```

This line should be left as is. It is merely telling the plugin you are about to begin defining items.  
Check the [**Item**](item.md) page for more information.

