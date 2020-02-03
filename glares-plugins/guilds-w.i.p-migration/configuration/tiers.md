---
description: Example configuration for the tiers.yml file
---

# Tiers

```yaml
# This section of the config will talk about various parts of upgrading a guild and allow you to choose how it works.
# For "mob-xp-multiplier" the default is 1, meaning that it will drop the normal amount of XP for non-upgraded guilds.
# DO NOT set it to 0, that will either throw errors or cause mobs to not drop XP.
# Keep in mind for the damage-multiplier, it applies to players also, so by default it's set to normal for every tier.
tiers:
    # Should permissions carry over between tiers?
    carry-over: true
    list:
        1:
            # Which level tier is this? 1 is the default.
            level: 1
            # What is the name of this tier?
            name: Bronze
            # How much is this tier? (If first tier, keep as same price as cost creation)
            cost: 0.0
            # How many members can be in a guild of this tier?
            max-members: 15
            # How many Vaults would you like the Guild to be able to use?
            vault-amount: 1
            # How much extra XP should drop from mobs?
            mob-xp-multiplier: 1.0
            # How much extra damage should be done?
            damage-multiplier: 1.0
            # How much can this tier hold in the bank?
            max-bank-balance: 10000.0
            # How many members should be in a guild for it to be able to rankup?
            members-to-rankup: 0
            # Would you like this tier to be able to open the buff GUI?
            use-buffs: true
            # If you wish to give this tier extra permissions, put them here.
            permissions: 
            - example.perm.here
        2:
            # Which level tier is this? 1 is the default.
            level: 2
            # What is the name of this tier?
            name: Silver
            # How much is this tier? (If first tier, keep as same price as cost creation)
            cost: 200.0
            # How many members can be in a guild of this tier?
            max-members: 30
            # How many Vaults would you like the Guild to be able to use?
            vault-amount: 2
            # How much extra XP should drop from mobs?
            mob-xp-multiplier: 2.0
            # How much extra damage should be done?
            damage-multiplier: 1.0
            # How much can this tier hold in the bank?
            max-bank-balance: 20000.0
            # How many members should be in a guild for it to be able to rankup?
            members-to-rankup: 0
            # Would you like this tier to be able to open the buff GUI?
            use-buffs: true
            # If you wish to give this tier extra permissions, put them here.
            permissions: 
            - example.perm.here
        3:
            # Which level tier is this? 1 is the default.
            level: 3
            # What is the name of this tier?
            name: Gold
            # How much is this tier? (If first tier, keep as same price as cost creation)
            cost: 300.0
            # How many members can be in a guild of this tier?
            max-members: 50
            # How many Vaults would you like the Guild to be able to use?
            vault-amount: 3
            # How much extra XP should drop from mobs?
            mob-xp-multiplier: 3.0
            # How much extra damage should be done?
            damage-multiplier: 1.0
            # How much can this tier hold in the bank?
            max-bank-balance: 30000.0
            # How many members should be in a guild for it to be able to rankup?
            members-to-rankup: 0
            # Would you like this tier to be able to open the buff GUI?
            use-buffs: true
            # If you wish to give this tier extra permissions, put them here.
            permissions: 
            - example.perm.here

```

