---
description: Example configuration for the buffs.yml file
---

# Buffs

```yaml
guild-buffs:
    # What should the name of the inventory be?
    gui-name: Guild Buffs
    # How often (in seconds) can a guild buy a buff?
    cooldown: 60
    # Do we want to allow users to have more than one buff at a time?
    buff-stacking: false
    # Set the name and material for the navigation buttons
    nav:
        next:
            material: EMPTY_MAP
            name: Next
        previous:
            material: EMPTY_MAP
            name: Previous
    # This is where the buffs themselves are to be created. You can create an unlimited number of buffs as long as the IDENTIFIERS are different.
    # Ths identifiers can be anything you want, they just tell the plugin that they aren't the same as the buff before.
    # The buffs are loaded into the menu in the order they are listed in the config. So, to change the order, simply change their location in their list of the config.
    # Example Buff:
    #     # The identifier of the buff, can be anything you want.
#    - identifier: '1'
    # This is what the buff will look like to the player when they DON'T have the permission listed below.
#      locked:
#        name: '&a&lSubstance of the Redmod Graff'
#        material: FEATHER
#        lore:
#        - '&aType » &7Haste'
#        - '&aLength » &760 Seconds'
#        - '&aCost » &7$60'
    # This is what the buff will look like to the player when they DO have the permission listed below.
#      unlocked:
#        name: '&a&lSubstance of the Redmod Graff'
#        material: FEATHER
#        lore:
#        - '&aType » &7Haste'
#        - '&aLength » &760 Seconds'
#        - '&aCost » &7$60'
    # The price of the buff, pulled from Guild Bank.
#      price: 60.0
    # The effects that the guild will get for buying the buff. You should be able to list as many as you want.
    # The way you do it is: EFFECT_TYPE;AMPLIFICATION;LENGTH OF BUFF
    # So, this effect here will give Haste I for 60 seconds.
#      effects:
#      - FAST_DIGGING;0;60
    # The permission required to purchase the buff.
#      permission: example.perm.here
    # Would you like to execute commands on the player that bought the buff for the guild? Supports {player}, {buyer}, {buff_name}.
#      clicker:
#        enabled: false
#        commands:
#        - ''
    # Would you like to execute commands on the guild that bough the buff? Supports {player}, {buyer}, {buff_name}.
#      guild:
#        enabled: false
#        commands:
#        - ''
    buffs: 
    - identifier: '1'
      locked:
        name: '&a&lSubstance of the Redmod Graff'
        material: FEATHER
        lore:
        - '&aType » &7Haste'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lSubstance of the Redmod Graff'
        material: FEATHER
        lore:
        - '&aType » &7Haste'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - FAST_DIGGING;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '2'
      locked:
        name: '&a&lBlessing of the Cheetah'
        material: SUGAR
        lore:
        - '&aType » &7Speed'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lBlessing of the Cheetah'
        material: SUGAR
        lore:
        - '&aType » &7Speed'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - SPEED;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '3'
      locked:
        name: '&a&lScales of the Dragon'
        material: BLAZE_POWDER
        lore:
        - '&aType » &7Fire-Resistance'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lScales of the Dragon'
        material: BLAZE_POWDER
        lore:
        - '&aType » &7Fire-Resistance'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - FIRE_RESISTANCE;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '4'
      locked:
        name: '&a&lEyes of the Lurking Demon'
        material: EYE_OF_ENDER
        lore:
        - '&aType » &7Night-Vision'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lEyes of the Lurking Demon'
        material: EYE_OF_ENDER
        lore:
        - '&aType » &7Night-Vision'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - NIGHT_VISION;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '5'
      locked:
        name: '&a&lFeet of the Ghostly Walker'
        material: DIAMOND_BOOTS
        lore:
        - '&aType » &7Invisibility'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lFeet of the Ghostly Walker'
        material: DIAMOND_BOOTS
        lore:
        - '&aType » &7Invisibility'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - INVISIBILITY;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '6'
      locked:
        name: '&a&lMighty Strength of the Pouncing Lion'
        material: DIAMOND_SWORD
        lore:
        - '&aType » &7Strength'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lMighty Strength of the Pouncing Lion'
        material: DIAMOND_SWORD
        lore:
        - '&aType » &7Strength'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - INCREASE_DAMAGE;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '7'
      locked:
        name: '&a&lBounce of the Quick Witted Rabbit'
        material: DIAMOND_BOOTS
        lore:
        - '&aType » &7Jump'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lBounce of the Quick Witted Rabbit'
        material: DIAMOND_BOOTS
        lore:
        - '&aType » &7Jump'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - JUMP;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '8'
      locked:
        name: '&a&lLungs of the Albino Shark'
        material: BUCKET
        lore:
        - '&aType » &7Water-Breathing'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lLungs of the Albino Shark'
        material: BUCKET
        lore:
        - '&aType » &7Water-Breathing'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - WATER_BREATHING;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''
    - identifier: '9'
      locked:
        name: '&a&lIntegrity of the Mystic Witch'
        material: EMERALD
        lore:
        - '&aType » &7Regeneration'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      unlocked:
        name: '&a&lIntegrity of the Mystic Witch'
        material: EMERALD
        lore:
        - '&aType » &7Regeneration'
        - '&aLength » &760 Seconds'
        - '&aCost » &7$60'
      price: 60.0
      effects:
      - REGENERATION;0;60
      permission: example.perm.here
      clicker:
        enabled: false
        commands:
        - ''
      guild:
        enabled: false
        commands:
        - ''

```
