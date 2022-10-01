---
description: A list of internal and PlaceholderAPI placeholders provided by ChatChat.
---

# Placeholders

## PlaceholderAPI

PlaceholderAPI placeholders that can be used both in ChatChat but also in any other plugin that supports PlaceholderAPI placeholders.

|               Placeholder               |                                                                           Description                                                                          |
| :-------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|        `%chatchat_channel_name%`        |                                                   Get the name of the channel that the user is currently in.                                                   |
|       `%chatchat_channel_prefix%`       |                                                  Get the prefix of the channel that the user is currently in.                                                  |
|   `%chatchat_channel_message_prefix%`   |                                              Get the message prefix of the channel that the user is currently in.                                              |
|     `%chatchat_social_spy_enabled%`     |                                                      Get whether or not this user has social spy enabled.                                                      |
|  `%chatchat_private_messages_enabled%`  |                                                   Get whether or not this user has private messages enabled.                                                   |
| `%chatchat_private_messages_recipient%` | Get the player that this user has last had a private conversation with. (This user expires after 5 minutes by default but can be configured in `settings.yml`) |

## Internal

Placeholders that can be used inside ChatChat itself but nowhere else.

ChatChat has a few internal placeholders, or more so tags that give users more freedom to customise their chats. These are tags you can only use in ChatChat, and sometimes only in some parts of ChatChat.

### \<recipient:PAPI-PLACEHOLDER>

This tag let's your parse PlaceholderAPI placeholders for the recipient of a message. This tag will work with both: private messages and public messages.

**Example of usage: `<recipient:player_name>`.** This would parse the `%player_name%` placeholder for the recipient of the message.

{% hint style="warning" %}
A thing to note is that you don't use the percent sign (%) for the PAPI placeholders inside this tag.
{% endhint %}

### \<papi:PAPI-PLACEHOLDER>

This tag let's you parse PlaceholderAPI placeholders for the sender of a message. This tag will work with both: private messages and public messages.

Since ChatChat already supports PlaceholderAPI placeholders using the normal format (%placeholder\_name%), this tag does have some special features:

* ChatChat doesn't support the legacy formatting anymore but most placeholders still return strings using those formats. This tag will translate those legacy colors to the new ones for you.
* Because of how legacy formatting works, it will bleed into the message but this tag gives you the ability to stop this. You can add a special argument that will determin if the formatting bleeds into the message or not. The argument is either `inserting` -it will bleed into the rest of the message- or `closing` -it will not bleed into the rest of the message-.

Example of usage: `<papi:player_displayname>`, `<papi:closing:player_displayname>` and `<papi:inserting:player_displayname>`. All of these will show the sender's display name but with the colors translated to MiniMessage. The first 2 tags will make the formatting of the display name not bleed into the message, while the last one will let it bleed.
