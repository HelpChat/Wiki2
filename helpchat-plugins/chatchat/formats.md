---
description: Everything about formats, how they work, permissions they require, etc.
---

# Formats

In ChatChat there are 2 types of formats: **BasicFormat** and **PriorityFormat.**

## **Basic Format**

In ChatChat, every format is a BasicFormat. Basic formats have 2 components: Name and Parts.\
These formats are usually used for: private messaging, social spy, mentions, etc.

### Format Name

The format name is also the format identifier. This is what you use to find formats, it's also the name you use when giving people permission to formats. Multiple formats should not have the same name.

### Format Parts

The format parts are made out of a key (the name) and a list of strings (the part).\
\
\- the **key** is the part's name and is going to be completely ignored by the plugin. It was added at the requested of the users as it makes the config look a lot more cleaner.\
\- the **part** is the actual format that will be used. ChatChat will just take the list of strings and append them together into one big string and then parse it to a message.

## Priority Format

Priority formats have everything that Basic Formats have but they also have a priority. These formats are the ones used in `formats.yml` for example.

### Priority

If a player has access to multiple formats, the priority will decide what format will be used when they sends a message in chat.

{% hint style="info" %}
Lower Number = Higher Priority
{% endhint %}

## Permissions

Formats are given away to players using permissions. Every format has a similar permission and that is: `chatchat.format<format-name>`

## Default Format

In your `formats.yml` file, you can specify the name of the default format. You must also create a format in there with that name. The default format will be used when a user has no permission for any other format.
