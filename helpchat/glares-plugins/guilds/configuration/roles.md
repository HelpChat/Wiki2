---
description: Example configuration for the roles.yml file
---

# Roles

```yaml
roles:
    0:
        name: GuildMaster
        permission-node: guilds.roles.master
        permissions:
            activate-buff: true
            add-ally: true
            ally-chat: true
            change-home: true
            change-prefix: true
            rename: true
            chat: true
            demote: true
            deposit-money: true
            invite: true
            kick: true
            open-vault: true
            promote: true
            remove-ally: true
            remove-guild: true
            toggle-guild: true
            transfer-guild: true
            upgrade-guild: true
            withdraw-money: true
            claim-land: true
            unclaim-land: true
            destroy: true
            place: true
            interact: true
            create-code: true
            delete-code: true
            see-code-redeemers: true
            modify-motd: true
            initiate-war: true
    1:
        name: Officer
        permission-node: guilds.roles.officer
        permissions:
            activate-buff: false
            add-ally: true
            ally-chat: true
            change-home: true
            change-prefix: false
            rename: false
            chat: true
            demote: true
            deposit-money: true
            invite: true
            kick: true
            open-vault: true
            promote: true
            remove-ally: true
            remove-guild: false
            toggle-guild: false
            transfer-guild: false
            upgrade-guild: false
            withdraw-money: true
            claim-land: false
            unclaim-land: false
            destroy: true
            place: true
            interact: true
            create-code: true
            delete-code: true
            see-code-redeemers: true
            modify-motd: false
            initiate-war: true
    2:
        name: Veteran
        permission-node: guilds.roles.veteran
        permissions:
            activate-buff: false
            add-ally: false
            ally-chat: true
            change-home: false
            change-prefix: false
            rename: false
            chat: true
            demote: false
            deposit-money: true
            invite: true
            kick: false
            open-vault: true
            promote: false
            remove-ally: false
            remove-guild: false
            toggle-guild: false
            transfer-guild: false
            upgrade-guild: false
            withdraw-money: false
            claim-land: false
            unclaim-land: false
            destroy: true
            place: true
            interact: true
            create-code: false
            delete-code: false
            see-code-redeemers: false
            modify-motd: false
            initiate-war: false
    3:
        name: Member
        permission-node: guilds.roles.member
        permissions:
            activate-buff: false
            add-ally: false
            ally-chat: true
            change-home: false
            change-prefix: false
            rename: false
            chat: true
            demote: false
            deposit-money: true
            invite: false
            kick: false
            open-vault: true
            promote: false
            remove-ally: false
            remove-guild: false
            toggle-guild: false
            transfer-guild: false
            upgrade-guild: false
            withdraw-money: false
            claim-land: false
            unclaim-land: false
            destroy: true
            place: true
            interact: true
            create-code: false
            delete-code: false
            see-code-redeemers: false
            modify-motd: false
            initiate-war: false

```

