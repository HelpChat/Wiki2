---
description: The main way to interact with the plugin
---

# ChatChatAPI

{% hint style="info" %}
You can see more detailed documentation about each holder and manager in the JavaDocs.
{% endhint %}

The ChatChatAPI interface provides access to multiple Holders and Managers.

## UsersHolder

A way to get existent user instances, create new user instances, unload existent user instances and save existent user instances to file.

## HookManager

A way to load new Hooks into ChatChat or get any already loaded hooks.

## ChannelTypeRegistry

A way to add new Channel types to ChatChat.

## RuleManager

A way to add new Rules into ChatChat or get any already loaded rules.

## MentionManager

A way to add new Mention types to ChatChat or get any already loaded mention types.

## MiniPlaceholderManager

A way to register new MiniPlaceholders in ChatChat, get any already loaded mini placeholders or compile all the MiniPlaceholders into a [TagResolver](https://jd.advntr.dev/text-minimessage/4.13.1/net/kyori/adventure/text/minimessage/tag/resolver/TagResolver.html).
