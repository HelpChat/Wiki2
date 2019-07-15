# Requirements

> ```yaml
> # This option can also be:
> # open_requirement
> # left_click_requirement
> # right_click_requirement
> view_requirement:
>   requirements:
>     # You can define multiple requirements.
>     # Each requiremnt needs a unique name.
>     requirement_name:
>       [requirement-type]
>   # This can only be defined in open and
>   # left/right_click_requirement
>   deny_commands:
>   - '[player] COMMAND'
>   - '[console] COMMAND'
>   - '[commandevent] COMMAND'
>   - '[message] TEXT'
>   - '[openguimenu] MenuName'
>   - '[connect] ServerName'
>   - '[json] {"text":"message"}'
>   - '[refresh]'
>   - '[broadcastsound] SOUND'
>   - '[sound] SOUND'
>   - '[takemoney] #'
> ```

Requirements allow you to restrict certain actions or even a entire menu and only allow certain players to see and/or use the menu.

It depends completely on what type of requirement you use:

* `open_requirement` defines requirements to open the menu.
* `view_requirement` are requirements for seeing an item.
* `right_click_requirement` is for when clicking an item. \(To allow the execution of commands\)
* `left_click_requirement` is the same as `right_click_requirement` but for left clicking an item.

You can define multiple requirements under `requirements:`  
If even just one requirement isn't met, then the entire check returns false and denies view of the menu/item or execution of the command\(s\).

> **Placeholders can be used in the requirements**

## Navigation

* [Has Permission](requirements.md#has-permission)
* [Has Money](requirements.md#has-money)
* [Has Item](requirements.md#has-item)
* [Javascript](requirements.md#javascript)
* [String Equals](requirements.md#string-equals)
* [String Equals Ignore case](requirements.md#string-equals-ignore-case)
* [Comparators](requirements.md#comparators)

### **Has permission**

> ```yaml
> type: has permission
> permission: 'TEXT'
> ```

Checks if the player has the required permission.

### **Has money**

> ```yaml
> type: has money
> amount: #
> ```

Checks if the player has enough money \([Vault](https://www.spigotmc.org/resources/34315/) required\)

### **Has item**

> ```yaml
> type: has item
> material: 'TEXT'
> data: #
> amount: #
> name: 'TEXT'
> lore:
> - 'TEXT'
> ```

Checks if the player has a certain item in its inventory.

### **Javascript**

> ```yaml
> type: javascript
> expression: 'EXPRESSION'
> ```

Evaluates a javascript expression that must return true or false.  
Example: `%vault_eco_balance% >= 100`

### **String equals**

> ```yaml
> type: string equals
> input: 'TEXT'
> output: 'TEXT'
> ```

Checks if `input:` matches `output:` exactly \(Including case\).

### **String equals ignore case**

> ```yaml
> type: string equals ignorecase
> input: 'TEXT'
> output: 'TEXT'
> ```

Same as [String Equals](requirements.md#string-equals) but ignores the case.

### **String contains**

> ```yaml
> type: string contains
> input: '%player_name%'
> output: 'A'
> ```

Checks if `input:` contains `output:`.  
For example: Checks if `This is a text` contains `is`.

### **Comparators**

> ```yaml
> type: (==, >=, <=, !=, >, <)
> input: #
> output: #
> ```

Compares `input:` with `output:` and returns true or false depending on what type of comparason you choosed.

#### Available options

| Option: | Description: |
| :--- | :--- |
| `==` | `input:` is equal as `output:` |
| `>=` | `input:` is equal or higher than `output:` |
| `<=` | `input:` is equal or smaller than `output:` |
| `!=` | `input:` is NOT equal to `output:` \(Is higher or lower\) |
| `>` | `input:` is higher than `output:` |
| `<` | `input:` is lower than `output:` |

