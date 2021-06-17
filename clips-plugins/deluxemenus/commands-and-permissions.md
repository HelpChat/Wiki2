---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Commands

| **Command** | **Permission** | Description |
| :--- | :--- | :--- |
| /dm | - | Displays some info about the plugin. |
| /dm open &lt;menu&gt; | deluxemenus.open | Opens the specified menu. |
| /dm open &lt;menu&gt; &lt;player&gt; | deluxemenus.open.others | Opens the specified menu to the specified player. |
| /dm open &lt;menu&gt; -p:&lt;player&gt; | deluxemenus.placeholdersfor | Opens the specified menu for you, but the placeholders in it will be parsed as the specified player. |
| /dm list | deluxemenus.list | Lists loaded menus. |
| /dm execute &lt;player&gt; &lt;action&gt; | Player needs to be Op | Executes any action for a player. Check out the [Action Type](https://wiki.helpch.at/clips-plugins/deluxemenus/options-and-configurations#actions-types) for more info. |
| /dm reload | deluxemenus.reload | Reloads the plugin's files. |
| /dm reload &lt;menu&gt; | deluxemenus.reload | Reload a menu. |

### Command Aliases

* /deluxemenus
* /deluxemenu
* /dmenu

## Permissions

| Permission | Description |
| :--- | :--- |
| deluxemenus.openrequirement.bypass.\* | Bypasses all menu's open requirements. |
| deluxemenus.openrequirement.bypass.&lt;menu&gt; | Bypasses the specified menu's open requirements. |
| deluxemenus.placeholdersfor.exempt | Blocks other players from using you in this command `/DM Open <Menu> -p:<You>`. |

{% hint style="info" %}
OP players will bypass all requirements!
{% endhint %}

{% hint style="info" %}
All text between the less-than and greater-than signs \(**&lt;&gt;**\) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs \(**&lt;&gt;**\).
{% endhint %}

