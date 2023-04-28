---
description: List of all commands and the required permission that ChatChat has.
---

# Commands

## Admin Commands

|                  Command                 |      Permission      |                                     Description                                    |
| :--------------------------------------: | :------------------: | :--------------------------------------------------------------------------------: |
|        /chatchat dump \[filename]        |     chatchat.dump    | Creates and posts a dump containing all files of the plugin or the file specified. |
| /chatchat test \<format-name> \<message> | chatchat.test.format |                    Sends the message using the specified format.                   |
|             /chatchat reload             |    chatchat.admin    |                          Reload the ChatChat configuration                         |

## Player Commands

|            Command            |             Aliases            |            Permission           |                               Description                              |
| :---------------------------: | :----------------------------: | :-----------------------------: | :--------------------------------------------------------------------: |
| /whisper \<player> \<message> | /tell, /w, /msg, /message, /pm |           chatchat.pm           |                 Send a private message to another user.                |
|       /reply \<message>       |               /r               |           chatchat.pm           | Send a reply to the last user that you messaged or sent you a message. |
|           /togglemsg          |     /toggledms, /togglepms     |        chatchat.pm.toggle       |                Toggle your private messages on and off.                |
|       /ignore \<player>       |                -               |         chatchat.ignore         |                             Ignore a user.                             |
|      /socialspy \[on/off]     |       /sspy, /pmspy, /spy      |        chatchat.socialspy       |                   Turn your own social spy on or off.                  |
|    /togglemention personal    |      /toggleping personal      | chatchat.mention.personal.block |             Toggle if you receive personal mentions or not.            |
|     /togglemention channel    |       /toggleping channel      |  chatchat.mention.channel.block |             Toggle if you receive channel mentions or not.             |

## Channel Commands

In ChatChat, each channel can have its own commands. Those commands can be set when creating the channels in `plugins/ChatChat/channels.yml` under the toggle-command option.

{% hint style="danger" %}
To make sure channel commands are properly registered, restart the server after any modifications to them.
{% endhint %}

## Command Overriding

If by any chance there are other plugins taking over a command that you want ChatChat to use, or vice versa, you can select which one is going to be used in the `commands.yml` bukkit file.

**Example:**\
\
Let's say you have a plugin that takes over the /msg command and you want ChatChat to take over. You open the `commands.yml` file and add the following under the `aliases:` option:

```yaml
  msg:
  - chatchat:msg $1-
```

{% hint style="danger" %}
Restart the server after modifying the `commands.yml` file to make sure all changes are properly applied!
{% endhint %}
