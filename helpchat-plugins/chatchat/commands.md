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

