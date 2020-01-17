---
description: The plugin's configuration file!
---

# Configuration

```yaml
# DeluxeQueues
# Creator: Glare
# Contributors: https://github.com/darbyjack/DeluxeQueues/graphs/contributors
# Issues: https://github.com/darbyjack/DeluxeQueues/issues
# Spigot: https://www.spigotmc.org/resources/69390/
# Discord: https://helpch.at/discord
settings:
    # Would you like to check for updates?
    update-check: true
    # How many seconds should be inbetween each queue movement?
    delay-length: 2
    # List all the servers here that you would like to have a queue for.
    # This is also where you specify how many players need to be on each server.
    # You also set the max slots of the server here, make sure it always stays the same as the actual max.
    # Synxtax: server name; amount of players to start the queue at; max slots of server
    # Example: hub;50;200
    servers: 
    - ''
    # What would you like the donator permission node to be?
    # Donators will be moved to the front of the queue!
    donator-permission: deluxequeues.vip
    # What would you like the staff permission node to be?
    # Staff will bypass the queue!
    staff-permission: deluxequeues.staff
notify:
    # How would you like to inform the player that they are in the queue?
    # Currently supports: ACTIONBAR, TEXT, TITLE
    method: ACTIONBAR
    actionbar:
        # How would you like the design for the ActionBar to look?
        design: 'Current Position: {pos} / {total}'
    text:
        # How would you like the design for the text to look?
        design: You are currently in position {pos} out of {total}
    title:
        # How would you like the design for the title to look?
        title: Current in queue
        subtitle: 'Position: {pos} / {total}'

```

