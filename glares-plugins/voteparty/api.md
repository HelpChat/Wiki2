---
description: Developer Information for VoteParty.
---

# API

## Custom Event

Inside of VoteParty, we offer a custom event that is listened to inside the plugin to give out rewards. This allows plugins to hook into it and also give extra rewards or modify to what they see fit.

### VoteReceivedEvent

```java
    /**
     * This event takes place when a hooked plugin receives a vote
     * @param player The player that voted
     */
    public VoteReceivedEvent(OfflinePlayer player) {
        this.player = player;
    }
```

