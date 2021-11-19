---
description: Everything about DeluxeMenus requirements!
---

# Requirements

{% hint style="warning" %}
**IMPORTANT!**\
**`left/right/shift_left/shift_right/middle` **click requirements won't work unless you also have their respective click commands. This is true even if you have set the **`success_commands`** option
{% endhint %}

## Syntax

> ```yaml
> # Other available requirement types:
> # open_requirement:
> # view_requirement:
> # left_click_requirement:
> # right_click_requirement:
> # shift_left_click_requirement:
> # shift_right_click_requirement:
> click_requirement:
>   # Minimum requirements are optional.
>   # If they are not set, then all
>   # requirements will be needed for the
>   # click commands to be executed.
>   # In this example, only one of the
>   # requirements will be needed.
>   minimum_requirements: 1
>   # This option is good for when you use minimum_requirements.
>   # Instead of the plugin checking all the requirements,
>   # it will stop when it has enough.
>   stop_at_success: true
>   requirements:
>     # You can define multiple requirements.
>     # Each requiremnt should have a unique name.
>     requirement_name:
>       type: TYPE
>       # These commands will be exeucted if
>       # the requirement they're set for is
>       # met even if the others are not.
>       # You should be careful and not confuse
>       # these with click_commands: !!!
>       success_commands:
>       - "[ACTIONTYPE] ACTION"
>       - "[ACTIONTYPE] ACTION"
>       # These commands will be executed if
>       # the requirement they're set for is
>       # not met even if the others are.
>       deny_commands:
>       - "[ACTIONTYPE] ACTION"
>       - "[ACTIONTYPE] ACTION"
>       # This option is only required if you
>       # want ot use minimum_requirements:
>       # Minimum requirements will only work
>       # for the optional requirements
>       optional: true
>   # This can only be defined for open and
>   # left/right click requirement
>   deny_commands:
>     - "[ACTIONTYPE] ACTION"
>     - "[ACTIONTYPE] ACTION"
> ```

Requirements allow you to restrict certain actions or even an entire menu and only allow certain players to see and/or use the menu.

## Requirements

| Type                                                                                       | Description                                                   |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------- |
| [Open Requirement](gui.md#open-requirements)                                               | Defines the requirements to open the menu.                    |
| [View Requirement](item.md#view-requirement)                                               | Defines the requirements to see an item in the menu.          |
| [(Shift) Left/Right Click Requirements](item.md#shift-left-middle-right-click-requirement) | Defines the requirements to (shift) left/right click an item. |

{% hint style="info" %}
* Placeholders can be used in the requirements.
* If you set multiple requirements, all of them should be met (Use [JavaScript type](requirements.md#javascript) or minimum\_requirements to add optional requirements).
{% endhint %}

## Requirement types

### **Has permission**

> ```yaml
> type: has permission
> permission: TEXT
> ```

Checks if the player has the specified permission.

To invert the requirement (Check if the player doesn't have the permission) you can simply add the exclamation mark before the type name (like this `type: "!has permission"`).

### **Has money**

> ```yaml
> type: has money
> amount: #
> ```

Checks if the player has the specified amount of money ([Vault](https://www.spigotmc.org/resources/34315/) is required).

To invert the requirement (Check if the player doesn't have the amount of money) you can simply add the exclamation mark before the type name (like this `type: "!has money"`).

{% hint style="info" %}
To use a placeholder as a value for the amount, replace the `amount:` field with `placeholder:`.
{% endhint %}

### **Has Item**

> ```yaml
> type: has item
> material: "TEXT"
> data: #
> amount: #
> name: "TEXT"
> lore:
>   - "TEXT"
> ```
>
> > **Required fields:**
> >
> > * Material
> > * Amount

Checks if the player has the specified item in the inventory.

To invert the requirement (Check if the player doesn't have the item) you can simply add the exclamation mark before the type name (like this `type: "!has item"`).

{% hint style="info" %}
You can use color/format codes in name and lore fields, but using `§` character instead of `&` character.
{% endhint %}

### **Has Meta**

{% hint style="warning" %}
Meta uses Persistent Data Containers which means this feature will only work on servers that are 1.14 or newer!
{% endhint %}

> ```yaml
> type: has meta
> key: "TEXT"
> meta_type: <STRING, BOOLEAN, DOUBLE, LONG, INTEGER>
> value: EXPECTED VALUE
> ```
>
> > **Required fields:**
> >
> > * key
> > * meta\_type
> > * value

Checks if the player has the specified meta.

If the `meta_type` is a number format (DOUBLE, LONG, INTEGER) it will check if the player's meta value is greater than or equal to the `value`

To invert the requirement (Check if the input doesn't match the output) you can simply add the exclamation mark before the type name (like this `type: "!has meta"`).

### **Has Exp**

> ```yaml
> type: has exp
> amount: #
> level: boolean # true if you want to check for exp levels, false for exp points
> ```
>
> > **Required fields:**
> >
> > * amount

Checks if the player has the exp level or points.

If the `level` option does not exist, it will check for exp points by default

To invert the requirement (Check if the input doesn't match the output) you can simply add the exclamation mark before the type name (like this `type: "!has exp"`).

### **Is Near**

> ```yaml
> type: is near
> location: "WORLDNAME,X,Y,Z"
> distance: #
> ```
>
> > **Required fields:**
> >
> > * location
> > * distance

Checks if the player is within `distance` of `location`.

To invert the requirement (Check if the input doesn't match the output) you can simply add the exclamation mark before the type name (like this `type: "!is near"`).

### **JavaScript**

> ```yaml
> type: javascript
> expression: 'EXPRESSION'
> ```
>
> > **Example:**
> >
> > ```yaml
> > type: javascript
> > expression: '%vault_eco_balance% >= 100'
> > ```

Evaluates a JavaScript expression that must return true or false.

### **String Equals**

> ```yaml
> type: string equals
> input: "TEXT"
> output: "TEXT"
> ```
>
> > **Example:**
> >
> > ```yaml
> > type: string equals
> > input: "%server_name%"
> > output: "HelpChat"
> > ```

Checks if `input:` matches `output:` (Case sensitive).

To invert the requirement (Check if the input doesn't match the output) you can simply add the exclamation mark before the type name (like this `type: "!string equals"`).

### **String Equals Ignore Case**

> ```yaml
> type: string equals ignorecase
> input: "TEXT"
> output: "TEXT"
> ```
>
> > **Example:**
> >
> > ```yaml
> > type: string equals ignorecase
> > input: "%server_name%"
> > output: "helpchat"
> > ```

Checks if `input:` matches `output:` (Case insensitive).

To invert the requirement (Check if the input doesn't match the output) you can simply add the exclamation mark before the type name (like this `type: "!string equals ignorecase"`).

### **String Contains**

> ```yaml
> type: string contains
> input: "TEXT"
> output: "TEXT"
> ```
>
> > **Example:**
> >
> > ```yaml
> > type: string contains
> > input: "%server_name%"
> > output: "chat"
> > ```

Checks if `input:` contains `output:` (Case sensitive).

To invert the requirement (Check if the input doesn't contain the output) you can simply add the exclamation mark before the type name (like this `type: "!string contains"`).

### Regex matches

> ```yaml
> type: regex matches
> input: "TEXT"
> regex: "EXPRESSION"
> ```

Checks if `input:` contains the regular expression in `regex:`.\
Visit [this site](https://regexr.com) to create regular expressions easily.

To invert the requirement (Check if the input doesn't contain the regular expression) you can simply add the exclamation mark before the type name (like this `type: "!regex matches"`).

### **Comparators**

> ```yaml
> type: (==, >=, <=, !=, >, <)
> input: #
> output: #
> ```

Compares `input:` with `output:`.

#### Available options

| Comparator | Description                                  |
| ---------- | -------------------------------------------- |
| `==`       | `input:` equals to `output:`                 |
| `>=`       | `input:` greater than or equals to `output:` |
| `<=`       | `input:` less than or equals to `output:`    |
| `!=`       | `input:` not equals to `output:`             |
| `>`        | `input:` greater than `output:`              |
| `<`        | `input:` less than `output:`                 |

## Examples

### Open Requirement

```yaml
open_requirement:
  requirements:
    example_1:
      type: has permission
      permission: open.menu.one
  deny_commands:
    - "[message] &cYou don't have the permission."
```

### View Requirement

```yaml
view_requirement:
  requirements:
    example_2:
      type: string equals
      input: "%player_is_op%"
      output: "yes"
```

### Left/Right Click Requirement

```yaml
# left_click_requirement: or
right_click_requirement:
  requirements:
    example_3:
      type: has money
      amount: 100
  deny_commands:
    - "[message] &7You don't have enough money."
```

### Minimum Requirements

```yaml
click_requirement:
  minimum_requirements: 1
  stop_at_success: true
  deny_commands:
    - "[message] &7You don't have 1 of the 2 permissions required."
  requirements:
    perm1:
      type: has permission
      permission: perm.1
    perm2:
      type: has permission
      permission: perm.2
click_commands:
- "[message] &7You have 1 of the 2 permissions required."
```
