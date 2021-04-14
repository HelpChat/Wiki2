---
description: Allow players to select chat tags that can be awarded by permission!
---

# DeluxeTags

## Description

**DeluxeTags** gives players the ability to have an extra tag in chat! Tags can be given to players by permissions so you have several ways of giving them to the players. Also, players can have access to multiple tags! they can switch between them using a GUI menu.

## Features

* Ability to create unlimited tags.
* Highly customizable.
* Players can have access to multiple tags.
* Permission-based tags.
* Force tag.
* Supports any chat plugin.

## Setup

### DeluxeChat

1. Put the **DeluxeTags jar** file you downloaded in your **plugins** folder.
2. Restart the server.
3. Modify the **config.yml** and **messages.yml** files that were generated to fit your server's layout \(Files path: `/plugins/DeluxeTags/`\).
4. Download **DeluxeTags expansion** by running the following commands: `/papi ecloud download DeluxeTags /papi reload`
5. Add the placeholders you want to your chat format. **DeluxeTags placeholders** can be found [here](placeholders.md).
6. Reload **DeluxeChat** `/DChat reload`.
7. Give tag permissions to your players `DeluxeTags.Tag.Name`.
8. Select your tag from `/Tags` and enjoy!!

### Essentials Chat

1. Put **DeluxeTags jar** file you downloaded in your **plugins** folder.
2. Restart the server.
3. Modify the **config.yml** and **messages.yml** files that were generated to fit your server's layout \(Files path: `/plugins/DeluxeTags/`\).
4. Disable **DeluxeChat** option in `config.yml` file. `deluxe_chat: false`
5. Disable **Format Chat** option in `config.yml` file. `format_chat:   enabled: false`
6. Change all the placeholder in `config.yml` file from `%placeholder%` to `{placeholder}` \(e.g. from `%deluxetags_amount%` to `{deluxetags_amount}`\).
7. Add the placeholders you want to your chat format. **DeluxeTags placeholders** can be found [here](placeholders.md). **Note:** You'll have to use `{}` for the placeholders instead of `%%`.
8. Restart the server.
9. Give tag permissions to your players `DeluxeTags.Tag.Name`.
10. Select your tag from `/Tags` and enjoy!!

