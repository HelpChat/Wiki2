---
description: Everything about DeluxeMenus requirements!
---

# Requirements

{% hint style="danger" %}
**IMPORTANT!**

**Click requirements do not work without their click commands counterparts! Having success\_commands set up will not be enough!**
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
* Placeholders and [arguments](gui.md#args) can be used in the requirements.
* If you set multiple requirements, all of them should be met (Use [JavaScript type](requirements.md#javascript) or minimum\_requirements to add optional requirements).
{% endhint %}

## Deny Commands

Deny commands are used to execute actions when players don't meet requirements. These actions can be set per requirement or per requirement list.

> ```yaml
> click_requirement:
>   requirements:
>     requirement_name:
>       type: TYPE
>       deny_commands:
>       - "[message] This is a deny command per requirement"
>   deny_commands:
>     - "[message] This is deny command per requirements list"
> ```

## Success Commands

Similar to deny commands, Success commands are used to execute actions when players meet requirements. These actions can be set per requirement or per requirement list.

> ```yaml
> click_requirement:
>   requirements:
>     requirement_name:
>       type: TYPE
>       success_commands:
>       - "[message] This is a success command per requirement"
>   success_commands:
>     - "[message] This is success command per requirements list"
> ```

{% hint style="danger" %}
For click requirements, having success\_commands is not enough! Click commands are also needed.
{% endhint %}

## Minimum Requirements

If this option is used, not all requirements that have `optional: true` will be checked. Instead, it will stop when enough requirements are met.

> ```yaml
> minimum_requirements: # Number
> ```

{% hint style="success" %}
This option only works for requirements that have `optional: true`. All the other requirements will still be checked
{% endhint %}

## Stop At Success

When mimimum requirements is used, the requirement validation will not stop when enough requirements are met. Instead it will continue with all requirements check. If this option is enabled, when the number of minimum requirements is met, validation for all remaining requirements will stop.

> ```yaml
> stop_at_success: # TRUE or FALSE
> ```

## Requirement types

{% hint style="warning" %}
When inverting requirements, make sure you put the type in quotation marks. This is because "!" is a special symbol in YAML so it will break the syntax.

ex: `type: "!has permission"`
{% endhint %}

### **Has permission**

> ```yaml
> type: has permission
> permission: TEXT
> ```

Checks if the player has the specified permission ([Vault](https://www.spigotmc.org/resources/34315/) is required).

To invert the requirement (Check if the player doesn't have the permission) you can simply add the exclamation mark before the type name (like this `type: "!has permission"`).

### **Has permissions**

> ```yaml
> type: has permissions
> permissions:
> - TEXT
> - TEXT
> minimum: # Number
> ```

Checks if the player has all the specified permissions ([Vault](https://www.spigotmc.org/resources/34315/) is required). If `minimum: #` is specified, it checks if the player has at least # permissions from the list.

To invert the requirement (Check if the player doesn't have the permissions) you can simply add the exclamation mark before the type name (like this `type: "!has permissions"`).

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
> # material option supports material names, placeholders and arguments.
> material: "TEXT"
> data: #
> # represents the CustomModelData the item should have.
> modeldata: #
> amount: #
> name: "TEXT"
> # lore can also be one single string: lore: "TEXT"
> lore:
>   - "TEXT"
> # if this is enabled then the plugin will look for items that contain the value
> # set at the option "name" in their name and not for the exact value
> name_contains: boolean
> # if this option is enabled then the plugin will check for the item name,
> # without caring about the case.
> name_ignorecase: boolean
> # if this is enabled then the plugin will look for items that contain the value
> # set at the option "lore" in their lore and not for the exact value
> lore_contains: boolean
> # if this option is enabled then the plugin will check for the item lore,
> # without caring about the case.
> name_ignorecase: boolean
> # if this option is enabled, the plugin will consider only the items that 
> # have no custom model data, no display name and no lore.
> strict: boolean
> # decides if the plugin should also check the armor slots of the player when
> # looking for items
> armor: boolean
> # decides if the plugin should also check the off hand of the player when
> # looking for items
> offhand: boolean
> ```
>
> > **Required fields:**
> >
> > * Material

Checks if the player has the specified item in the inventory.

To invert the requirement (Check if the player doesn't have the item) you can simply add the exclamation mark before the type name (like this `type: "!has item"`).

{% hint style="success" %}
Has support for custom materials. Please [see here](item.md#material) for a list of supported custom materials.
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

### **String Length**

> ```yaml
> type: string length
> input: "TEXT"
> min: # Number
> max: # Number
> ```
>
> > **Example:**
> >
> > ```yaml
> > type: string length
> > input: "%player_name%"
> > min: 3
> > max: 14
> > ```

Checks if `input:` is longer than or equal to `min:` and shorter than or equal to `max:`.

{% hint style="danger" %}
This requirement does not have a negative counterpart: `!string length`&#x20;
{% endhint %}

### **Is Object**

> ```yaml
> type: is object
> input: "TEXT"
> object: # INT, DOUBLE, PLAYER or UUID
> ```
>
> > **Example:**
> >
> > ```yaml
> > type: string length
> > input: "Notch"
> > object: player
> > ```

Checks if `input:` can be mapped to the Java Object you specified.

* INT - checks if the input can be mapped to an integer
* DOUBLE - checks if the input can be mapped to a double-precision floating point number
* UUID - checks if the input can be mapped to a UUID
* PLAYER - checks if the input matches a player's name or a player's uuid

{% hint style="danger" %}
This requirement does not have a negative counterpart: `!string length`&#x20;
{% endhint %}

### Regex matches

> ```yaml
> type: regex matches
> input: "TEXT"
> regex: "EXPRESSION"
> ```

Checks if `input:` contains the regular expression in `regex:`.\
Visit [this site](https://regexr.com/) to create regular expressions easily.

To invert the requirement (Check if the input doesn't contain the regular expression) you can simply add the exclamation mark before the type name (like this `type: "!regex matches"`).

### **Comparators**

> ```yaml
> type: (==, >=, <=, !=, >, <)
> input: #
> output: #
> ```

Compares `input:` with `output:`.

{% hint style="success" %}
Now both the input and the output support floating point values.
{% endhint %}

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
