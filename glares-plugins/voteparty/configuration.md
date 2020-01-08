---
description: The plugin's configuration file!
---

# Configuration

```yaml
# VoteParty
# Creator: Clip & Glare
# Contributors: https://github.com/VoteParty/VoteParty/graphs/contributors
# Issues: https://github.com/VoteParty/VoteParty/issues
# Spigot: https://www.spigotmc.org/resources/987/
# Wiki: https://wiki.helpch.at/glares-plugins/voteparty
# Discord: https://helpch.at/discord
settings:
    # The default language of the plugin
    language: en_US
    # The prefix of all the messages in the plugin
    prefix: '&d&lV&dote&5&lP&5arty &7&l» '
crate:
    enabled: true
    lore: 
    - ''
    - '&7Place the chest in order to'
    - '&7to receive rewards!'
    - ''
    material: CHEST
    name: '&d&lVote&5&lParty &f&lCrate'
# Configuration for particle effects you can play
# throughout different parts of the plugin
effects:
    # Configuration for particles when party commands are being executed
    party_commands_execute:
        enable: true
        effects: 
        - SMOKE_NORMAL
        - HEART
        offsetX: 0.0
        offsetY: 0.0
        offsetZ: 0.0
        speed: 0.0
        count: 3
    # Configuration for particles when a party starts
    party_start:
        enable: true
        effects: 
        - SMOKE_NORMAL
        - HEART
        offsetX: 0.0
        offsetY: 0.0
        offsetZ: 0.0
        speed: 0.0
        count: 3
    # Configuration for particles when a player votes
    vote:
        enable: true
        effects: 
        - SMOKE_NORMAL
        - HEART
        offsetX: 0.0
        offsetY: 0.0
        offsetZ: 0.0
        speed: 0.0
        count: 3
party:
    # The amount of votes needed for a party to occur
    votes_needed: 50
    # The list of worlds where party rewards won't be given
    disabled_worlds: 
    - ''
    # Choose to allow offline votes count towards the party
    offline_votes: true
    # The amount of time (in seconds) the server will wait to start the party after the amount needed has been achieved
    start_delay: 15
    # The amount of time (in seconds) the server will wait between executing reward commands
    command_delay: 5
    # Configuration for chance rewards to be given during a party.
    # Add as many commands as you want, set their chance, and choose the max amount a player can earn!
    reward_commands:
        enabled: true
        max_possible: 3
        commands: 
        - chance: 90
          command: eco give %player_name% 100
        - chance: 90
          command: give %player_name% DIAMOND 6
        - chance: 90
          command: give %player_name% IRON_INGOT 12
    # A list of rewards that will ALWAYS be given to a player during a party
    guaranteed_rewards:
        enabled: true
        commands: 
        - eco give %player_name% 10
        - give %player_name% STEAK 8
    # Commands to be executed before a party is started
    pre_party_commands:
        enabled: true
        commands: 
        - broadcast Party will start soon!
    # Commands to be executed when a party has started
    party_commands:
        enabled: true
        commands: 
        - broadcast Party will start soon!
voting:
    # Configuration for chance rewards to be given for voting.
    # Add as many commands as you want, set their chance, and choose the max amount a player can earn!
    per_vote_rewards:
        enabled: true
        max_possible: 1
        commands: 
        - chance: 50
          command: eco give %player_name% 100
        - chance: 70
          command: give %player_name% STEAK 10
    # A list of rewards that will ALWAYS be given to a player for voting
    guaranteed_rewards:
        enabled: true
        commands: 
        - eco give %player_name% 10
        - give %player_name% STEAK 8
    # Global commands (such as a broadcast message) to be executed when a player votes
    global_commands:
        enabled: true
        commands: 
        - broadcast Only %voteparty_votes_required_party% more votes until a VoteParty!
```

