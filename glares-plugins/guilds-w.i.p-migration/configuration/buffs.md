---
description: Example configuration for the buffs.yml file
---

# Buffs

```yaml
guis:
    guild-buffs:
        # What should the name of the inventory be?
        gui-name: Guild Buffs
        # Do we want to allow users to have more than one buff at a time?
        buff-stacking: false
        # Do you want to enable requiring per-buff permissions?
        # For example, if I wanted to buy the haste buff,
        # I would need the permission guilds.buff.haste
        per-buff-permissions: false
        buffs:
            haste:
                # What do you want to name the buff?
                name: '&a&lSubstance of the Redmod Graff'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: FEATHER
                # What type of potion is this?
                type: FAST_DIGGING
                # You can put as much as you want here
                description: 
                - '&aType » &7Haste'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 0
            speed:
                # What do you want to name the buff?
                name: '&a&lBlessing of the Cheetah'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: SUGAR
                # What type of potion is this?
                type: SPEED
                # You can put as much as you want here
                description: 
                - '&aType » &7Speed'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 1
            fire-resistance:
                # What do you want to name the buff?
                name: '&a&lScales of the Dragon'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: BLAZE_POWDER
                # What type of potion is this?
                type: FIRE_RESISTANCE
                # You can put as much as you want here
                description: 
                - '&aType » &7Fire-Resistance'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 2
            night-vision:
                # What do you want to name the buff?
                name: '&a&lEyes of the Lurking Demon'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: REDSTONE_TORCH_ON
                # What type of potion is this?
                type: NIGHT_VISION
                # You can put as much as you want here
                description: 
                - '&aType » &7Night-Vision'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 3
            invisibility:
                # What do you want to name the buff?
                name: '&a&lFeet of the Ghostly Walker'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: EYE_OF_ENDER
                # What type of potion is this?
                type: INVISIBILITY
                # You can put as much as you want here
                description: 
                - '&aType » &7Invisibility'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 4
            strength:
                # What do you want to name the buff?
                name: '&a&lMighty Strength of the Pouncing Lion'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: DIAMOND_SWORD
                # What type of potion is this?
                type: INCREASE_DAMAGE
                # You can put as much as you want here
                description: 
                - '&aType » &7Strength'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 5
            jump:
                # What do you want to name the buff?
                name: '&a&lBounce of the Quick Witted Rabbit'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: DIAMOND_BOOTS
                # What type of potion is this?
                type: JUMP
                # You can put as much as you want here
                description: 
                - '&aType » &7Jump'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 6
            water-breathing:
                # What do you want to name the buff?
                name: '&a&lLungs of the Albino Shark'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: BUCKET
                # What type of potion is this?
                type: WATER_BREATHING
                # You can put as much as you want here
                description: 
                - '&aType » &7Water-Breathing'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 7
            regeneration:
                # What do you want to name the buff?
                name: '&a&lIntegrity of the Mystic Witch'
                # How much do you want the buff to cost?
                price: 60.0
                # How long (in second) should the buff last?
                time: 60
                # How strong do you want the buff to be? 0 = Potion Level 1, 1 = Potion Level 2, etc...
                amplifier: 0
                # What item do you want to represent the buff?
                icon: EMERALD
                # What type of potion is this?
                type: REGENERATION
                # You can put as much as you want here
                description: 
                - '&aType » &7Regeneration'
                - '&aLength » &760 Seconds'
                - '&aCost » &7$60'
                # Do you want this buff to show in-game?
                display: true
                commands:
                    clicker:
                        # Would you like to enable commands to be sent to the player who bought the buff?
                        enabled: false
                        # What commands would you like to execute on the player that clicked? (Supports {player})
                        commands: 
                        - ''
                    guild:
                        # Would you like to enable commands to be sent to all online players in the guild?
                        enabled: false
                        # What commands would you like to execute on all online players in guild? (Supports {player})
                        commands: 
                        - ''
                # What slot would you like this to use?
                slot: 8
```

