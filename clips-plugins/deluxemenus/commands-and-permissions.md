---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Commands

| **Command** | **Permission** | Description |
| :--- | :--- | :--- |
| /DM | - | Displays some info about the plugin. |
| /DM Open &lt;Menu&gt; | DeluxeMenus.Open | Opens the specified menu. |
| /DM Open  &lt;Menu&gt; &lt;Player&gt; | DeluxeMenus.Open.Others | Opens the specified menu to the specified player. |
| /DM Open &lt;Menu&gt; -p:&lt;Player&gt; | DeluxeMenus.PlaceholdersFor | Opens the specified menu for you, but the placeholders in it will be parsed as the specified player. |
| /DM List | DeluxeMenus.List | Lists loaded menus. |
| /DM Reload | DeluxeMenus.Reload | Reloads the plugin's files. |

#### Command Aliases

* /DeluxeMenus
* /DeluxeMenu
* /DMenu

## Permissions

| Permission | Description |
| :--- | :--- |
| DeluxeMenus.OpenRequirement.Bypass.\* | Bypasses all menu's open requirements. |
| DeluxeMenus.OpenRequirement.Bypass.&lt;Menu&gt; | Bypasses the specified menu's open requirements. |
| DeluxeMenus.PlaceholdersFor.Exempt | Blocks other players from using you in this command `/DM Open <Menu> -p:<You>`. |

{% hint style="info" %}
All text between the less-than and greater-than signs \(**&lt;&gt;**\) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs \(**&lt;&gt;**\).
{% endhint %}

