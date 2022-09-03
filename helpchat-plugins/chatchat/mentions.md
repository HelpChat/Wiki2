---
description: Everything you need to know about mentions.
---

# Mentions

Mentions are a way to get someone's attention to your messages. Messages only work in public messages. Mentions are also highly customizable and can be modified in the settings.yml file.

By default ChatChat registers 2 mention types but other plugins can register their own mention types. The default types are: personal and channel mentions.

## Personal Mentions

These are used to directly mention one specific user.&#x20;

### How they work:

To use them you just type in chat the mention prefix that you can modify in the settings which by default is `@` followed by the user's name. E.g. `@BlitzOffline`. You also need to have the mention usage permission and the block bypass permission in case the mentioned user had turned their mentions off.

### What these mentions do:

The user's name will be highlighted in the message to both the sender and the mentioned person and also the mentioned person will hear a sound. The sound is customizable.\
\
If the mentioned user has their personal mentions turned off and the person mentioning them doesn't have the bypass permission the receiver will still see the highlighted name but they won't hear the sound. Also the sender won't see the highlighted name.
