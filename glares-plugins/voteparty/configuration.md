---
description: >-
  Give rewards to all online players when the server gets a certain amount of
  votes! 1.8+
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
    # Configuration for particles when a party starts
    party_start:
        enable: true
        effects: 
        - SMOKE_NORMAL
        - HEART
    # Configuration for particles when a player votes
    vote:
        enable: true
        effects: 
        - SMOKE_NORMAL
        - HEART
party:
    votes_needed: 50
    disabled_worlds: 
    - ''
    offline_votes: true
    start_delay: 15
    command_delay: 1
    reward_commands:
        enabled: true
        max_possible: 1
        commands: 
        - chance: 50
          command: eco give %player_name% 100
        - chance: 50
          command: give %player_name% DIAMOND 6
        - chance: 50
          command: give %player_name% IRON_INGOT 12
    guaranteed_rewards:
        enabled: true
        commands: 
        - eco give %player_name% 10
        - give %player_name% STEAK 8
    pre_party_commands:
        enabled: true
        commands: 
        - broadcast Party will start soon!
    party_commands:
        enabled: true
        commands: 
        - broadcast Party will start soon!
voting:
    per_vote_rewards:
        enabled: true
        max_possible: 1
        commands: 
        - chance: 50
          command: eco give %player_name% 100
        - chance: 70
          command: give %player_name% STEAK 10
    guaranteed_rewards:
        enabled: true
        commands: 
        - eco give %player_name% 10
        - give %player_name% STEAK 8
    global_commands:
        enabled: true
        commands: 
        - broadcast Only %voteparty_votes_required_party% more votes until a VoteParty!
```
