---
description: Events fired by ChatChat and the changes listeners can make.
---

# Events

## Public chat

`ChatChatEvent` is fired while a public message is processed and before it is delivered. It is cancellable. A listener can inspect or change the sender, channel, format, message, and recipient set.

## Private messages

`PMSendEvent` is fired before a local private message is sent. It is cancellable and exposes the sender, recipient, message, reply state, and sender and recipient formats.

`CrossServerPMSendEvent` is fired after ChatChat finds a remote recipient and before it forwards a cross-server private message. It is cancellable and exposes the recipient UUID and name, reply state, message, and sender, recipient, and social-spy formats.

## Mentions

`MentionEvent` is the base event for a mention processed in a public message. It is cancellable and exposes the sender, target, channel, and whether the mention sound should play.

- `PersonalMentionEvent` is fired for a direct player mention.
- `ChannelMentionEvent` is fired for a channel-wide mention such as `@here`, `@everyone`, or `@channel`.

## Example

Cancel a public message from a selected player:

```java
import at.helpch.chatchat.api.event.ChatChatEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public final class ChatListener implements Listener {
    @EventHandler(ignoreCancelled = true)
    public void onChatChat(final ChatChatEvent event) {
        if (event.user().player().map(player -> player.getName().equals("Example")).orElse(false)) {
            event.setCancelled(true);
        }
    }
}
```

`ChatChatEvent` follows Bukkit's synchronous or asynchronous event contract based on the chat processing context. Listeners should handle it on the appropriate thread.
