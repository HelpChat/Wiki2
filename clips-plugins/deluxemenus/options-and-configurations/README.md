---
description: About the plugin's options and configurations
---

# Options & Configurations

**DeluxeMenus** is a highly customizable plugin, it has many options and configurations to give you the ability to change everything you want to make your custom menus that fits your server's layout.  
It has **GUI** options to manage the GUI menu, and **Item** options to manage every single item on the GUI menu.

## Useful links

* [Placeholders](https://helpch.at/placeholders)
* Materials
  * [1.8.8](https://helpch.at/docs/1.8.8/org/bukkit/Material.html)
  * [1.12.2](https://helpch.at/docs/1.12.2/org/bukkit/Material.html)
  * [1.13.2](https://helpch.at/docs/1.13.2/org/bukkit/Material.html)
  * [1.14.4](https://helpch.at/docs/1.14.4/org/bukkit/Material.html)
  * [Latest](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)
* [Enchantments](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html) \(Be aware that some enchantments are not available on some items.\)
* [Dye Colors](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/DyeColor.html)
* [Pattern Types](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/block/banner/PatternType.html)
* [Sound Types](https://gist.github.com/Andre601/1ab3b4fabd0010ae241156333491c379)

## Values keywords

| Keyword | Description |
| :--- | :--- |
| **BOOLEAN** | Replace this with `true` or `false` \(If used with a PlaceholderAPI placeholder, this will be `yes` or `no` instead of `true`/`false` \[It's changeable from PlaceholderAPI config file, but `yes`/`no` are the default values\]\). |
| **TEXT** | Replace this with any text. Check the description to find out if you can use color/formatting codes. |
| **\#** | Replace this with a number. Check the description to see if there are limits. |
| **COMMAND** | Replace this with a command without slash \(`/`\). |
| **SOUND** | Replace this with a sound name. |
| **EXPRESSION** | Replace this with a java/placeholder expression/comparison. See [this](requirements.md) page for more information. |

## Actions types

<table>
  <thead>
    <tr>
      <th style="text-align:left">Tag</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>[player] &lt;command&gt;</code>
      </td>
      <td style="text-align:left">Executes a command as the player.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[console] &lt;command&gt;</code>
      </td>
      <td style="text-align:left">Executes a command from the console.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[commandevent] &lt;command&gt;</code>
      </td>
      <td style="text-align:left">Executes an unregistered command as the player.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[message] &lt;text&gt;</code>
      </td>
      <td style="text-align:left">Sends a message to the player. You can use <a href="https://helpch.at/placeholders">placeholders</a> and
        color/format codes here.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[broadcast] &lt;text&gt;</code>
      </td>
      <td style="text-align:left">
        <p>Sends a message to everyone online including the console.</p>
        <p>You can use <a href="https://helpch.at/placeholders">placeholders</a> and
          color/format codes here.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[openguimenu] &lt;menu-name&gt;</code>
      </td>
      <td style="text-align:left">Opens another GUI from DeluxeMenus.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[connect] &lt;server-name&gt;</code>
      </td>
      <td style="text-align:left">Connects the player to a server on the same BungeeCord.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[close]</code>
      </td>
      <td style="text-align:left">Closes the currently opened GUI.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[json] &lt;JSON-text&gt;</code>
      </td>
      <td style="text-align:left">Send a json message to the player. Use <a href="https://minecraftjson.com/">this</a> website
        to easily generate the JSON text.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[jsonbroadcast] &lt;JSON-text&gt;</code>
      </td>
      <td style="text-align:left">Send a json message to everyone online. Use <a href="https://minecraftjson.com/">this</a> website
        to easily generate the JSON text.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[refresh]</code>
      </td>
      <td style="text-align:left">Refresh items in the current menu view. This updates the shown Items themselves.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[broadcastsound] &lt;sound&gt; &lt;pitch&gt; &lt;volume&gt;</code>
      </td>
      <td style="text-align:left">Broadcast a sound to all players on the server.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[sound] &lt;sound&gt; &lt;pitch&gt; &lt;volume&gt;</code>
      </td>
      <td style="text-align:left">Play a sound for the player.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[takemoney] &lt;amount&gt;</code>
      </td>
      <td style="text-align:left">Take a certain amount of money from the player. <a href="https://www.spigotmc.org/resources/34315/">Vault</a> is
        required for this action to work.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[givemoney] &lt;amount&gt;</code>
      </td>
      <td style="text-align:left">Give a certain amount of money to the player. <a href="https://www.spigotmc.org/resources/34315/">Vault</a> is
        required for this action to work.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[takeexp] #L</code>
      </td>
      <td style="text-align:left">Take a certain amount of exp levels or points from a player. To give levels,
        add <code>L</code> at the end, otherwise remove it.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[giveexp] #L</code>
      </td>
      <td style="text-align:left">Give a certain amount of exp levels or points to a player. To give levels,
        add <code>L</code> at the end, otherwise remove it</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[meta] &lt;set/remove/add/subtract/switch&gt; &lt;key&gt; &lt;type&gt; &lt;value&gt;</code>
      </td>
      <td style="text-align:left">Modifies the player&apos;s meta. <code>add/subtract</code> are for number
        types. <code>switch</code> is for boolean, it will swap it from true/false.
        Check <a href="requirements.md#has-meta">here</a> for more detail.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>[chat] &lt;message&gt;</code>
      </td>
      <td style="text-align:left">Send a message in chat as the player who this action got executed for.</td>
    </tr>
  </tbody>
</table>

### **Action tags**

These tags can be added with the action \(e.g. `- '[message] example<delay=20>'`\).

| Tag | Description |
| :--- | :--- |
| `<delay=<time>>` | Executes the action after the specified delay \(in ticks, 20 ticks = 1 second\). |
| `<chance=<chance>>` | Sets a chance to execute the action. |

## RGB/Hex

If you want to use RGB/Hex colors in DeluxeMenus on 1.16+ you can use the following format: "&\#aaFF00"

## Placeholders

There is one available placeholder from DeluxeMenus:

* `%deluxemenus_meta_<key>_<dataType>_<default_value>%`

## General options

### Debug

> ```yaml
> debug: BOOLEAN
> ```
>
> > **Default value:** `false`

Enables/Disables debug mode.  
Sends debug messages to the console.

### Check updates

> ```yaml
> check_updates: BOOLEAN
> ```
>
> > **Default value:** `true`

Enables/Disables checking new updates for the plugin.  
Notifies any operator if there is an update available.

