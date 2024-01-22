---
description: More information about registering menu commands
---

# Command Registration

How to register a command?

Each menu can have 2 options:

### [open\_command](gui.md#open-command)

This is used to specify a list of commands that can be used to open the menu.

{% hint style="danger" %}
Note that by using this option alone, you will get no tab completion and other plugins will override this command
{% endhint %}

### [register\_command](gui.md#register-command)

This accepts a boolean value (true or false). If the value is set to true, then on every server restart, DeluxeMenus will make an effort to register the command with the server. This should provide tab completion.

## I have another plugin that registers the same command. What can I do?

When a command is registered with the server, an alias is provided: `/deluxemenus:<menu-command>`.

To better explain this, let's take an example:

&#x20;We have a menu named `randomteleportmenu` with `open_command: "rtp"` and `register_command: true`. We'll consider that the server was restarted since the menu was created so the command was registered.\
We are also using a RandomTeleport plugin that also registers the `/rtp` command.

&#x20;Now when we execute `/rtp`, we get randomly teleported instead of having our menu open.

How do we fix this?\
We could use `/deluxemenus:rtp` to open the menu, but we don't want our players to use prefixed commands as they are too long.\


The solution is to use the [commands.yml](https://bukkit.fandom.com/wiki/Commands.yml) file provided by our server. We can find the file in the server's root directory where we find the the server jar file and the eula.txt file. If you've never modified the file, it will look something like this by default:

```yaml
command-block-overrides: []
ignore-vanilla-permissions: false
aliases:
  icanhasbukkit:
  - version $1-
```

Now, we modify the file like this:

```yaml
command-block-overrides: []
ignore-vanilla-permissions: false
aliases:
  icanhasbukkit:
  - version $1-
  rtp:
  - deluxemenus:rtp $1-
```

Save, restart the server and you're all done!

{% hint style="danger" %}
Make sure to save the changes and restart the server if you want the changes to properly apply!
{% endhint %}

{% hint style="success" %}
If you want to read more about the commands.yml file, you can do so here: [https://bukkit.fandom.com/wiki/Commands.yml](https://bukkit.fandom.com/wiki/Commands.yml)
{% endhint %}
