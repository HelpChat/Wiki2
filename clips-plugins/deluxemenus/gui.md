# GUI

> ```yaml
> gui_menus:
>   menuname:
>     menu_title: 'TEXT'
>     open_command: TEXT
>     open_requirement: EXPRESSION
>     open_commands:
>     - '[player] COMMAND'
>     - '[console] COMMAND'
>     - '[commandevent] COMMAND'
>     - '[message] TEXT'
>     - '[openguimenu] MenuName'
>     - '[connect] ServerName'
>     - '[json] {"text":"message"}'
>     - '[refresh]'
>     - '[broadcastsound] SOUND'
>     - '[sound] SOUND'
>     - '[takemoney] #'
>     inventory_type: 'TEXT'
>     size: #
>     update_interval: #
>     items:
> ```

**Note:** If you're using an external GUI-file \(seperate .yml file\) your configuration will start at the **menu\_title:** option!

## Navigation

* [Menu Title](gui.md#menu-title)
* [Open Command](gui.md#open-command)
* [Open Requirement](gui.md#open-requirement)
* [Open Commands](gui.md#open-commands) \(This is different from _open command_\)
* [Inventory Type](gui.md#inventory-type)
* [Size](gui.md#size)
* [Args](gui.md#args) \(This section is optional\) \(Version 1.12.0\)
* [Update Interval](gui.md#update-interval)
* [Items](gui.md#items)

### Menu Title

> ```yaml
> menu_title: 'TEXT'
> ```

This is the menu title that is shown at the top of the open GUI. You can use color and formatting codes in this area. You can also use Placeholders in this title \(Like %player\_name%\).

### Open Command

> ```yaml
> open_command: COMMAND
> ```

This defines the command used to open the GUI. This can only be a single word \(No commands with arguments\).

You can define multiple commands by putting each command on a separate line.  
**Example**:

> ```yaml
> open_command:
> - COMMAND
> - COMMAND
> ```

### Open Requirement

> ```yaml
> open_requirement:
>  requirements:
>    <TEXT>:
>      type: <type>
> ```

This allows you to restrict the inventory in a way to only let people open it, which match the defined \[\[requirements\]\].

### Open Commands

> ```yaml
> open_commands:
> - '[player] COMMAND'
> - '[console] COMMAND'
> - '[commandevent] COMMAND'
> - '[message] TEXT'
> - '[openguimenu] MenuName'
> - '[connect] ServerName'
> - '[json] {"text":"message"}'
> - '[refresh]'
> - '[broadcastsound] SOUND'
> - '[sound] SOUND'
> - '[takemoney] #'
> ```

This will run the command\(s\) you set when player open the the menu.

### Inventory Type

> ```yaml
> inventory_type: 'TEXT'
> ```

This is optional.

Allows you to define a different type of Inventory.  
Supported types are `CHEST` \(default\), `ANVIL`, `DISPENSER`, `DROPPER`, `FURNACE`, `HOPPER` and `WORKBENCH`.

**Important**: Only `CHEST` allows you to define a own [inventory size](gui.md#size). All other types have a set slot-size and format.

### Size

> ```yaml
> size: #
> ```

This option tells the plugin of how large the inventory should be.  
The size can be a multiple of 9 \(9, 18, 27, ...\) and be a max size of 54.

## This option is ignored if you use a different [Inventory Type](gui.md#inventory-type) that isn't `CHEST`.

### Args

> ```yaml
> args:
>   target: 1
>   time: 1
>   reason: -1
> args_usage_message: "Incorrect Usage! Usage:"
> ```

This should only be set when using the arguments, if you are not using the arguments in your menu:

> ```yaml
> {target}
> {time}
> {reason}
> ```

you should not include it. Arguments can be used to make custom displayable information menus for players. See the [Arguments](arguments.md) page for more information.

### Update Interval

> ```yaml
> update_interval: #
> ```

This is for any items that use the update: tag \(See \[\[Item\|Item\#update\]\]\). The number defines the delay \(in seconds\) between each refresh of the placeholders in an item's lore/display name.  
Note that DeluxeMenus **won't** update the item itself \(Change the item\). This is only possible by executing a `[refresh]` command in the items \[\[left/right-click commands\|Item\#leftright-click-commands\]\].

### Items

> ```yaml
> items:
> ```

This line should be left as is. It is merely telling the plugin you are about to begin defining items.  
See the \[\[Item\]\] page for more information.

