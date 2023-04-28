---
description: Allow players to select chat tags that can be awarded by permission!
---

# DeluxeTags

## Description

**DeluxeTags** gives players the ability to have an extra tag in chat, tab and everywhere else! Tags can be given to players by permissions so you have several ways of giving them to the players. Also, players can have access to multiple tags! they can switch between them using a GUI menu.

## Features

* Ability to create unlimited tags.
* Highly customizable.
* Players can have access to multiple tags.
* Permission-based tags.
* Force tag.
* Supports almost any chat plugin.

## Setup

### PAPI Chat Plugins

(Plugins that support PlaceholderAPI placeholders)

1. Stop the server.
2. Put the **DeluxeTags jar** file you downloaded in your **plugins** folder.
3. Start the server.
4. Modify the **config.yml** and **messages.yml** files that were generated to fit your server's layout (Files path: `/plugins/DeluxeTags/`).
5. Enable **PAPI Chat** option in `config.yml` file\
   `papi_chat: true`
6. Add the placeholders you want to your chat format. **DeluxeTags placeholders** can be found [here](placeholders.md).
7. Restart the server.
8. Give tag permissions to your players `deluxetags.tag.<identifier>`.
9. Select your tag from `/tags` and enjoy!!

### Almost any other chat (including EssentialsX Chat)

1. Stop the server.
2. Put **DeluxeTags jar** file you downloaded in your **plugins** folder.
3. Start the server.
4. Modify the **config.yml** and **messages.yml** files that were generated to fit your server's layout (Files path: `/plugins/DeluxeTags/`).
5. Disable **papi\_chat** option in `config.yml` file.\
   `papi_chat: false`
6. Disable **Format Chat** option in `config.yml` file.\
   `format_chat:`\
   &#x20; `enabled: false`
7. Add the placeholders you want to your chat format. **DeluxeTags placeholders** can be found [here](placeholders.md).\
   **Note:** You'll have to use `{}` for the placeholders instead of `%%`.\
   **Example:** `{deluxetags_tag}`.
8. Restart the server.
9. Give tag permissions to your players `deluxetags.tag.<identifier>`.
10. Select your tag from `/tags` and enjoy!!

{% hint style="danger" %}
For older versions of DeluxeTags (1.8.1 and older) you need to edit your DeluxeTags config.yml to replace all `%placeholders%` to `{placeholders}`.\
**Example:** %deluxetags\_tag% to {deluxetags\_tag}
{% endhint %}

### DeluxeTags's own chat formatter

1. Put **DeluxeTags jar** file you downloaded in your **plugins** folder.
2. Restart the server.
3. Modify the **config.yml** and **messages.yml** files that were generated to fit your server's layout (Files path: `/plugins/DeluxeTags/`).
4. Disable **PAPI Chat** option in `config.yml` file.\
   papi`_chat: false`
5. Enable **Format Chat** option in `config.yml` file.\
   `format_chat:`\
   &#x20; `enabled: true`
6. Change the chat format in `config.yml` file.\
   `format_chat:`\
   &#x20; `format: '{deluxetags_tag} <%1$s> %2$s'`
7. Make sure that you don't have other chat formatting plugins installed.
8. Restart the server.
9. Give tag permissions to your players `deluxetags.tag.name`.
10. Select your tag from `/tags` and enjoy!!
