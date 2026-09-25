---
description: The managers exposed by ChatChatAPI and what they provide.
---

# ChatChatAPI

`ChatChatAPI` is registered as a Bukkit service. It exposes the following managers:

| Method | Use |
| --- | --- |
| `usersHolder()` | Find, create, unload, and save ChatChat user objects. |
| `hookManager()` | Register hooks and access loaded basic and vanish hooks. |
| `channelTypeRegistry()` | Register channel types that implement custom routing or membership. |
| `ruleManager()` | Register or access rules used to validate public and private messages. |
| `mentionsManager()` | Register and access mention types. |
| `miniPlaceholdersManager()` | Register MiniMessage placeholders, inspect registered placeholders, and compile their tag resolvers. |

The API also includes channel, format, user, hook, mention, placeholder, rule, and event interfaces. Read the Javadocs for method signatures and nullability details.
