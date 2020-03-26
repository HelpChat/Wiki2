---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Player Commands

| Command | Permission | Description | Aliases |
| :--- | :--- | :--- | :--- |
| /MSG &lt;Player&gt; &lt;Message&gt; | deluxechat.pm | Sends a private message to the specified player. | Message, PM, Tell, Whisper, M, T, W |
| /Reply &lt;Message&gt; | deluxechat.pm | Replies to a private message. | R |
| /MSGToggle | deluxechat.pm.toggle | Toggles private messages/ | MToggle, PMToggle |
| /GToggle | deluxechat.bungee.toggle | Toggles global chat. | GlobalToggle |

## Admin Commands

| Command | Permission | Description |
| :--- | :--- | :--- |
| /DChat | deluxechat.admin/\* | DeluxeChat help command. |
| /DChat Reload | deluxechat.admin/\* | Reloads DeluxeChat files. |
| /DChat List | deluxechat.admin/\* | Lists loaded format names. |
| /DChat Test &lt;Format&gt; &lt;Message&gt; | deluxechat.admin/\* | Tests the specified format. |
| /SocialSpy | deluxechat.socialspy | Toggles social spy mode. |

#### Command Aliases

1. DChat:
   * DeluxeChat 
2. SocialSpy:
   * DeluxeSocialSpy

## Permissions

| Permission | Description |
| :--- | :--- |
| deluxechat.&lt;FormatName&gt; | Gives access to the specified format. |
| deluxechat.color | Gives the ability to use color codes in chat. |
| deluxechat.formatting | Gives the ability to use formatting codes in chat. |
| deluxechat.utf | Gives the ability to use special UTF characters in chat. |
| deluxechat.url | Gives the ability to send clickable links in chat. |
| deluxechat.pm.color | Gives the ability to use color codes in private messages. |
| deluxechat.pm.formatting | Gives the ability to use formatting codes in private messages. |
| deluxechat.pm.url | Gives the ability to send clickable links in private messages. |
| deluxechat.bungee.chat | Gives the ability to chat globally if bungee is enabled. |
| deluxechat.pm.ignoretoggle | Gives the ability to send private messages to players that have PM toggled off. |
| deluxechat.ignore.bypass | Gives the ability to send private messages to players even if they ignore you. |
| deluxechat.vanish.bypass | Gives the ability to send private messages to vanished players. |
| deluxechat.filter.bypass | Gives the ability to bypass the chat filter. |
| deluxechat.bungee.override | Gives the ability to always send to all players in global chat even if they're in local chat. |
| deluxechat.socialspy.onjoin | Toggles on social spy mode on join automatically. |
| deluxechat.admin | Gives access to all DeluxeChat commands and permissions. |
| deluxechat.\* | Gives access to all DeluxeChat commands and permissions. |

{% hint style="info" %}
All text between the less-than and greater-than signs \(**&lt;&gt;**\) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs \(**&lt;&gt;**\).
{% endhint %}

