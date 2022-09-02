---
description: Everything about channels, how they work, permissions they require, etc.
---

# Channels

Channels are made out of 6 components, some of which are optional.

### Channel Name

The channel name is also the channel identifier. This is what you use to find channels, it's also the name you use when giving people permission to see or send messages in a channel. Multiple channels should not have the same name.

### Message Prefix (optional)

Also known as a quick prefix, the message prefix option is used to quickly send messages in different channels without having to switch to that channel before.\
**Default Value:** `empty`

### Channel Prefix (optional)

Also known as a channel display name, is used for display purposes only. Currently the only use is inside the `%chatchat_channel_prefix% placeholder.`\
**Default Value:** `empty`

### Channel Commands (optional)

Are commands that can be used to switch to the respective channel or to directly send a message in that channel. If for example, you have a staff-chat channel and you add the `staff` command as a channel command, users with access to the staff-chat channel can use `/staff` to switch to the staff-chat channel or they can use `/staff <message>` to send a message  in the staff-chat channel.\
**Default Value:** `empty list`

### Channel Radius (optional)

If a channel has a radius, the messages will only be sent to players within x blocks from the sender. Set radius to -1 to mark the channel as global instead.\
**Default Value:** `-1`

### Channel Type (optional)

The channel type option is used to determin the channel's type. By default, ChatChat registers one channel type caleld `default`. When it finds Towny installed it registers 2 new channel types: `towny_town` and `towny_nation`. Other plugins can also use the API to register new channel types.\
**Default Value:** `default`
