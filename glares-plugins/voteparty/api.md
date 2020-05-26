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

### PrePartyEvent

```java
	/**
	 * This event takes place when a party is preparing to start
	 */
	public PrePartyEvent() {
	}
```

### PartyStartEvent

```java
	/**
	 * This event takes place when a party is starting
	 */
	public PartyStartEvent() {
	}
```

### PartyEndEvent

```java
	/**
	 * This event takes place when a party is finished
	 */
	public PartyEndEvent() {
	}
```

