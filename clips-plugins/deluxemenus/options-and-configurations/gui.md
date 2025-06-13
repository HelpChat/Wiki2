---
description: All GUI menu related options & configurations
---

# GUI

## Syntax

> <pre class="language-yaml"><code class="lang-yaml"><strong>menu_title: "TEXT"
> </strong>open_command: COMMAND
> open_requirement: EXPRESSION
> open_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> inventory_type: "TEXT"
> size: #
> update_interval: #
> items:
> </code></pre>

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

## Placeholders Support Arguments

> ```yaml
> arguments_support_placeholders: true
> ```

In version 1.14.1 of DeluxeMenus, the order of placeholders and arguments being parsed was changed for security reasons. If you know there is no security risk for you, the old order can be reverted by adding this option.

{% hint style="warning" %}
**Security Warning!**

Some placeholders do more than returning values. To prevent user input from being used directly into placeholders, this option is disabled by default. If you know the placeholders you use inside menus are not doing such things, feel free to enable this option!
{% endhint %}

## Open Commands

> ```yaml
> open_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> ```

Runs the command(s) you set when the player opens the menu.

## Close Commands

> ```yaml
> close_commands:
>   - "[ACTIONTYPE] ACTION"
>   - "[ACTIONTYPE] ACTION"
> ```

Runs the command(s) you set when the player close the menu by clicking an item that have the close action (`[close]`).

{% hint style="warning" %}
At the moment, it is not possible to run these actions when a menu is closed by other means such as pressing the "ESC" key.
{% endhint %}

## Inventory Type

> ```yaml
> inventory_type: "TEXT"
> ```
>
> > **Default value:** `CHEST`\
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
> > **Default value:** `54`\
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
Size option only works for CHEST [inventory types](gui.md#inventory-type). Even for that it is optional and will default to 54.
{% endhint %}

## Register Command

> ```yaml
> register_command: true
> ```

Registers the open command with the server.

{% hint style="info" %}
Must be manually added to the menu.
{% endhint %}

{% hint style="info" %}
Server will need to be restarted.
{% endhint %}

## Arguments <a href="#args" id="args"></a>

> ```yaml
> args:
> - "TEXT"
> - "TEXT"
> - "TEXT"
> ```
>
> > * **TEXT** The argument name (Should be unique).

Gives you the ability to set arguments after the [open command](gui.md#open-command), and use them inside the menu by adding the argument placeholder (the argument name inside curly braces `{TEXT}`).

Arguments can also be specified when the `[openguimenu]` action is used.

You can have multiple arguments, and they will be set in the same order in the open command.

```
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

{% hint style="success" %}
- It's highly recommended to add the [Args Usage Message](gui.md#args-usage-message) option.
- **Requires** [**Register Command**](gui.md#register-command) **to be enabled!**
{% endhint %}

## Arguments Wrong Usage Message

> ```yaml
> args_usage_message: "TEXT"
> ```

Custom message to be sent to a player when he uses a command to open a menu but does not specify the required arguments. Colors and formatters can be used in this message.

&#x20;Requires [Arguments](gui.md#args) to be defined.

## Update Interval

> ```yaml
> update_interval: #
> ```

This is for any items that use the `update:` option (Check it [here](item.md#update)).\
The number defines the delay (in seconds) between each refresh of the placeholders in an item's lore/display name.

**Note:** This refreshes/updates the placeholders only.

## Items

> ```yaml
> items:
> ```

This line should be left as is. It is merely telling the plugin you are about to begin defining items.\
Check the [**Item**](item.md) page for more information.
