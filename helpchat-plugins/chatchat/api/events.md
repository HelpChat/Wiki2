---
description: >-
  ChatChat triggers a few events. You can find a list with all the events on
  this page.
---

# Events

## ChatChatEvent

The event is fired whenever a public chat message is being processed and about to be sent.

## PMSendEvent

The event is fired when a private message is being processed and about to be sent.

## ChannelMentionEvent

The event is fired when a user is mentioned in a public message using a channel mention such as: @here, @everyone, @channel

## PersonalMentionEvent

The event is fired when a user is mentioned in a public message using a direct mention such as: @BlitzOffline

## MentionEvent

The event is fired whenever a user is mentioned in a public message thru a channel mention or a direct mention.

## Example

Example of a class listening to the ChatChatEvent and canceling it if the sender's name is BlitzOffline.

```java
package at.helpch.example.listener;

import at.helpch.chatchat.api.event.ChatChatEvent;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

public class ChatChatEventListener implements Listener {

    @EventHandler(ignoreCancelled = true)
    public void onChatChatEvent(final ChatChatEvent event) {
        if (event.user().player().getName().equals("BlitzOffline")) {
            event.setCancelled(true);
            return;
        }
    }
}

```
