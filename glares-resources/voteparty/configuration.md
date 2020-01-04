---
description: Detailed example of what the default config provides.
---

# Configuration

## 

The reason why **VoteParty's** config file might look funny to you is because it does not utilize tradition YAML files. **VoteParty** utilizes an advanced Object-Relational Mapping \(**ORM**\) system in order to provide fast and efficient loading, saving, and utilizing of the data that it contains!

## Why does the config below look different than what I see in mine?

One of the downfalls of the system that **VoteParty** uses for the config is that it was hard to design a way to keep comments \(detailed notes throughout different parts of the config file\), so, in order to help clear some confusion, the config shown below is a detailed version of it to provide the best context it can for each part of the config.

## Config

```yaml
# Configuration for the crate you can give players
crate: {
# Determines if it can be given / 
  enabled: true
  lore: ["&aPlace me &e:)"]
  material: Chest
  name: "&b&lVote&f&lParty &7Crate"
}
# Configuration for particle effects you can play 
# throughout different parts of the plugin
effects: {
# Configuration for particles when party 
# commands are being executed
  party_command_execute: {
    effects: [SMOKE_NORMAL, HEART]
    enabled: true
  }
# Configuration for particles when a party starts
  party_start: {
    effects: [SLIME, HEART]
    enabled: true
  }
# Configuration for particles when a player votes
  vote: {
    effects: [FLAME, HEART]
    enabled: true
  }
}
# Configuration for the vote party
party: {
# Input worlds you would like to disable the party in
# For example, disabledWorlds: ["world_nether"]
# would disable parties in the nether
  disabledWorlds: [ ]
# Configure the commands you want to guarantee the player will get
# In other words, players will ALWAYS get ALL of these
  guaranteedRewards: {
    commands: ["eco give %player_name% 10", "give %player_name% STEAK 8"]
    enabled: true
  }
# Max random rewards from the list below
  maxRewardsPerPlayer: 1
# Allow offline votes to count towards party
  offlineVotes: true
# Commands to execute when a party is starting
  partyCommands: {
    commands: ["broadcast Party Starting!"]
    enabled: false
  }
# Commands to execute at the beginning of the start delay
  prePartyCommands: {
    commands: ["broadcast Party will start soon!"]
    enabled: false
  }
# Random commands to try and execute on players
# Format is [Chance Percentage, "Command"]
# For example, if I wanted to give a player
# $100 from Essentials, with a 90% chance,
# I would do the following:
# [90, "eco give %player_name% 100"]
  rewardCommands: {
    commands: [
      [50, "eco give %player_name% 100"],
      [50, "give %player_name% DIAMOND 6"],
      [50, "give %player_name% IRON_INGOT 12"]
    ]
# How long should the plugin wait 
# inbetween each command being executed
    delay: 1
  }
# How long to wait to start party after 
# reaching votes needed
  startDelay: 15
# The amount of votes needed to start the party
  votesNeeded: 50
}
settings: {
# The default language of the plugin
  language: "en_US"
# The prefix of all the messages in the plugin
  prefix: "&d&lV&dote&5&lP&5arty &7&l» "
}
# Configuration for the voting part of the plugin
voting: {
# Global commands to run when a player votes
  globalCommands: {
    commands: ["broadcast Only %whatever_this_placeholder_is% more votes until a VoteParty!"]
    enabled: true
  }
# Guaranteed commands you want to execute on the player that voted
  guaranteedRewards: {
    commands: ["eco give %player_name% 10", "give %player_name% STEAK 8"]
    enabled: true
  }
# Random commands to try and execute on players
# Format is [Chance Percentage, "Command"]
# Refer to example in party for how to add more
  perVoteRewards: {
    commands: [
      [50, "eco give %player_name% 100"],
      [70, "give %player_name% STEAK 10"]
    ]
    enabled: false
# Max possible commands that will execute from the list aboveWhy does the config look different from a traditional plugin config?
    max_possible: 1
  }
}
```



