---
description: Example configuration for the config.yml file
---

# Config

```yaml
# Guilds
# Creator: Glare
# Contributors: https://github.com/guilds-plugin/Guilds/graphs/contributors
# Issues: https://github.com/guilds-plugin/Guilds/issues
# Spigot: https://www.spigotmc.org/resources/66176/
# Wiki: https://wiki.glaremasters.me/
# Discord: https://glaremasters.me/discord
settings:
    announcements:
        # This is used for the Guild's Announcement System, which allow me (The Author) to communicate to you guys without updating.
        # The way this works is very simple. If you have "console" set to "true", you will see the announcement when the server starts.
        # If you have "in-game" set to "true", your OPed players will see it the first time they login to the server.
        console: true
        in-game: true
    # Choosing your language for the plugin couldn't be easier! The default language is english.
    # If you speak another language but don't see it here, feel free to submit it via one of the links above to have it added to the plugin.
    # If you try and use a different language than any in the list above, the plugin will not function in a normal manner.
    # As you can see this is currently en-US, and there is a en-US.yml file in the language folder.
    # If I wanted to switch to french, I would use fr-FR as the language instead.
    messagesLanguage: en-US
    # Would you like to check for plugin updates on startup? It's highly suggested you keep this enabled!
    update-check: true
    # What would you like the command aliases for the plugin to be?
    # You can have as many as your want, just separate each with | and NO SPACES.
    plugin-aliases: guild|guilds|g
    # Change this to whatever you change it to above, this will handle the changes within <>
    # Keep in mind you should only set it to ONE thing. Such as guild, town, etc.
    syntax-name: guild
    # Would you like to run vault permission changes async? (Will be less stress on the main thread and prevent lag)
    # Async is used by LuckPerms.
    # Set this to false if you are using PEx.
    # I do suggest you switch to LuckPerms so that you can keep it async, but ultimately the choice is yours.
    run-vault-async: true
storage:
    # What storage method should be used? (MySQL, MariaDB, JSON, SQLite)
    storage-type: json
    # How often (in minutes) do you want all Guild Data to save?
    save-interval: 1
    sql:
        # Define the address for the database. (Doesn't apply to SQLite)
        host: localhost
        # Define the port for the database. (Doesn't apply to SQLite)
        port: '3306'
        # The name of the database to store data in.
        # This must be already created! (Doesn't apply to SQLite)
        database: guilds
        # The prefix for all Guilds tables.
        table-prefix: guilds_
        # Define the credentials for the database. (Doesn't apply to SQLite)
        username: root
        password: ''
        # Sets whether or not to use SSL for the remote SQL database connection (Doesn't apply to SQLite)
        enable-ssl: false
        # These settings change the SQL connection pool.
        # The default settings are optimized for the majority of users.
        # Do NOT change these settings unless you know what you are doing!
        # For those looking to migrate data:
        # IF YOU ARE MIGRATING FROM JSON OR SQLITE TO MYSQL THE SETTINGS MUST BE CONFIGURED EVEN IF THE DATA TYPE IS SET TO JSON OR MYSQL.
        # When migrating to MySQL, it will attempt to use the MySQL backend (grab the login information here) in order to connect to the database.
        # We are not responsible for data loss if you are too lazy to read the warnings.
        # ALWAYS REMEMBER TO BACKUP DATA BEFORE MIGRATING.
        # Lastly, remember to change your storage-type to the type you're migrating to before you reboot.
        pool:
            # Sets the maximum size of the SQL connection pool.
            # This value will determine the maximum number of connections maintained. (Doesn't apply to SQLite)
            maximum-pool-size: 10
            # Sets the minimum number of idle connections that the pool will maintain.
            # For maximum performance keep this value the same as 'maximum-pool-size' (Doesn't apply to SQLite)
            minimum-idle: 10
            # Sets the maximum lifetime of a connection in the pool in milliseconds. (Doesn't apply to SQLite)
            maximum-lifetime: 1800000
            # Sets the maximum number of milliseconds for a connection in the pool before timing out. (Doesn't apply to SQLite)
            connection-timeout: 5000
hooks:
    # Do we want to hook into Essentials-Chat format to handle guild placeholders?
    essentials-chat: false
    # Do we want to hook into WorldGuard to allow claiming land?
    worldguard-claims: false
# Use the following website to get available materials: https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html
# This can work across all MC versions and will attempt to use the proper material based on what version of MC you are using.
guis:
    # What time format should we use in the GUIs?
    # You can use this site to build it https://docs.oracle.com/javase/7/docs/api/java/text/SimpleDateFormat.html
    time-format: MMM, d, yy hh:mm aaa
    guild-list:
        # What should the name of the inventory be?
        gui-name: Guild List
        # What should the name of the all the items be in the inventory?
        # Currently supports {player} and {guild}.
        item-name: '&f{player}''s Guild'
        # How should the menu be sorted?
        # LOADED: In the order that the Guilds were loaded on startup
        # TIER: In order from highest tier to lowest tier
        # MEMBERS: In order from most members to least members
        # BALANCE: In order from most in bank to least
        # WINS: In order from most arena wins to least
        # NAME: In order by name
        # AGE: In order from first created to last
        sort: LOADED
        # What item should players click to go to the next page?
        next-page-item: EMPTY_MAP
        # What should the name of this item be?
        next-page-item-name: '&fNext Page'
        # What item should players click to go to the previous page?
        previous-page-item: EMPTY_MAP
        # What should the name of this item be?
        previous-page-item-name: '&fPrevious Page'
        # What should be the default texture url for textures that fail to load in? Refer to the Guild Manage settings to see how to change the texture!
        head-default-url: 7a2df315b43583b1896231b77bae1a507dbd7e43ad86c1cfbe3b2b8ef3430e9e
        # You are free to design this to your liking
        # This is just an example of all the available placeholders that you can use for the lore!
        # Note: With v3.6.7 and on, you can now use {guild-tier-name} for the name of the tier.
        # Also, from v3.6.7 and on, {guild-status} will now apply from what you set for the guild-info GUI for the status being public or private.
        # In version 3.5.2.2, {guild-challenge-wins} and {guild-challenge-loses} have been added.
        # In version 3.5.3.3, {creation} was added to display the creation date of the guild
        head-lore: 
        - '&cName&8: &a{guild-name}'
        - '&cPrefix&8: &a{guild-prefix}'
        - '&cMaster&8: &a{guild-master}'
        - '&cStatus&8: &a{guild-status}'
        - '&cTier&8: &a{guild-tier}'
        - '&cBalance&8: &a{guild-balance}'
        - '&cMember Count&8: &a{guild-member-count}'
        - '&cCreation Date&8: &a{creation}'
    # Here you can control what the GUI looks like that allows players to choose which vault to open
    # You can do things like set the name of the gui, the material to use, material name, and lore!
    vault-picker:
        # What do you want the name of the gui to be?
        # Currently supports {name} for the name of the guild.
        name: '&8» &r{name}''s Vaults'
        # How many rows would you like to display?
        rows: 1
        # What do you want the material of the vaults to be?
        item-material: CHEST
        # WHat do you want the name of the vault to be?
        # I recommend keeping this blank so that we can put the vault number in the lore.
        item-name: ' '
        item-lore: 
        - '&8• &7Vault &9#{number}'
        - '&8• &7Status: {status}'
        - ''
        # What do you want to show when a vault is unlocked?
        unlocked: '&9Unlocked'
        # What do you want to show when a vault is locked?
        locked: '&c&mLocked&r'
    vault:
        # What do you want the name of the Vault to be?
        # Note: This requires a restart to change the inventory names.
        name: '&8» &rGuild Vault'
        blacklist:
            # What materials would you like to blacklist from being put into the vaults?
            materials: 
            - ''
            # What custom names of items would you like to blacklist from being put into the vaults?
            names: 
            - ''
            # What custom lore do you want to blacklist from being put into the vaults?
            # Please keep in mind this can be prove to false-positives so please let me know if you have issues.
            # This will currently loop through your lore to check for any strings you have in the list to check.
            # Improvements will be made over time. Thanks for your patience and suppport in advanced.
            lores: 
            - ''
    # Welcome to the Guild Info GUI section of the config.
    # Here you can modify the configuration of what the Guild Info GUI looks like.
    # This can be used by any member of a Guild and shows key information of the Guild.
    # You can see things like the members, the balance, tier, etc.
    guild-info:
        # What would you like the name of the GUI to be?
        # Currently supports {name} for the name of the guild and {prefix} for the prefix of the guild
        name: '&8» &r{name}''s Info'
        # What material do you want the tier button to be?
        tier-material: DIAMOND
        # What do you want the name of the tier button to be?
        tier-name: '&3Guild Tier'
        # What do you want the lore of the tier button to be?
        tier-lore: 
        - '&8• &7Level: &b{tier}'
        # Would you like to display this button?
        tier-display: true
        # What material do you want the bank button to be?
        bank-material: GOLD_INGOT
        # What do you want the name of the bank button to be?
        bank-name: '&6Guild Bank'
        # What do you want the lore of the bank button to be?
        bank-lore: 
        - '&8• &7Balance: &e{current} &7/ &e{max}'
        # Would you like to display this button?
        bank-display: true
        # What material do you want the members button to be?
        members-material: IRON_HELMET
        # What do you want the name of the members button to be?
        members-name: '&5Guild Members'
        # What do you want the lore of the members button to be?
        members-lore: 
        - '&8• &7Members: &d{current} &7/ &d{max}'
        - '&8• &7Online: &d{online} &7/ &d{current}'
        - ''
        - '&7Click to view members!'
        # Would you like to display this button?
        members-display: true
        status-material:
            # What material do you want the status button to be when a guild is public?
            public: EMERALD
            # What material do you want the status button to be when a guild is private?
            private: REDSTONE
        # What do you want the name of the status button to be?
        status-name-item: '&2Guild Status'
        status-name:
            # What do you want the status to say if it's public?
            public: '&aPublic'
            # What do you want the status to say if it's private?
            private: '&cPrivate'
        # What do you want the lore of the status button to be?
        status-lore: 
        - '&8• &7Status: &r{status}'
        # Would you like to display this button?
        status-display: true
        # What material do you want the home button to be?
        home-material: BED
        # What do you want the name of the home button to be?
        home-name: '&cGuild Home'
        # What do you want the lore of the home button to be?
        home-lore: 
        - '&8• &7Home: &f{coords}'
        # Would you like to display this button?
        home-display: true
        # What do you want it to say when a guild doesn't have a home set?
        home-empty: '&fNot Set'
        # Do you want players to be teleported to their guild home when they click this?
        home-teleport: false
        # What material do you want the vault button to be?
        vault-material: CHEST
        # What do you want the name of the home button to be?
        vault-name: '&9Guild Vaults'
        # What do you want the lore of the vault button to be?
        vault-lore: 
        - '&7Click here to open your guild vaults!'
        # Would you like to display this button?
        vault-display: true
        # What material do you want the motd button to be?
        motd-material: SIGN
        # What do you want the name of the motd button to be?
        motd-name: '&6Guild MOTD'
        # What do you want the lore of the motd button to be?
        motd-lore: 
        - '{motd}'
        # Would you like to display this button?
        motd-display: true
    # This part of the config controls what the members gui looks like.
    # You can get to this in game by clicking on the members icon via the guild info gui.
    guild-info-members:
        # How should the menu be sorted?
        # ROLE: In order from highest role to lowest
        # NAME: In order by their username
        # AGE: In order of length in guild
        sort: ROLE
        # What would you like the name of the GUI to be?
        name: '&8» &rMembers of {name}'
        item:
            # What material do you want to use to represent members?
            material: EMPTY_MAP
            # What do you want the name of the item to be?
            name: ' '
            # What do you want the lore of the item to be?
            lore: 
            - '&8• &7Name: &a{name}'
            - '&8• &7Role: &a{role}'
            - '&8• &7Status: {status}'
            - '&8• &7Join Date: &a{join}'
            - '&8• &7Last Login: &a{login}'
            # What do you want to be what shows when a member is online?
            online: '&aOnline'
            # What do you want to be what shows when a member is offline?
            offline: '&cOffline'
guild:
    requirements:
        # With the default RegEx currently set, the minimum length of the prefix is 1 and the maximum is 64.
        # To change this, adjust the number and you can refer to the link below on how to modify RegEx.
        # RegEx (https://en.wikipedia.org/wiki/Regular_expression) used to only allow certain characters (default only allows alphanumeric characters).
        # To turn off the ability to use colors, remove the & from the RegEx.
        # Trying to use symbols such as Chinese ones? Try this Regex: [\u4E00-\u9FA5_a-zA-Z0-9&_\一-龥]{1,6}
        name: '[a-zA-Z0-9&]{1,64}'
        # Similar to the name, just refer above.
        prefix: '[a-zA-Z0-9&]{1,20}'
        # Would you like to include color codes signs (&b &l, etc) in the length check?
        include-color-codes: true
    # Would you like to allow players to make a guild without a prefix?
    disable-prefix: false
    # Would you like player to respawn at their guild home (if they have one) when they die?
    respawn-at-home: false
    blacklist:
        # Do we want to enable the blacklist?
        enabled: true
        # Do we want the blacklist to be case sensitive?
        case-sensitive: true
        # What words would you like to blacklist from being used?
        words: 
        - crap
        - ass
        - stupid
    format:
        # This is the style used when a message sent in guild chat.
        # As of 3.4.7, this now supports {display-name} to show the display name of a player.
        chat: '&7&l[Guild Chat]&r &b[{role}&b]&r &b {player}: {message}'
        # Similar to the one above, just for the admins spying.
        spy: '&7&l[Guild Spy]&r &b[{guild}&b]&r &b[{role}&b]&r &b {player}: {message}'
        # Would you like to log the guild chat to console?
        log-guild-chat: false
        # Used for {GUILD_FORMATTED} and %guilds_formatted%
        placeholder-design:
            # The left bracket in the placeholder
            left-bracket: '['
            # The content of the placeholder. Either will be {name} or {prefix}
            content: '{name}'
            # What to show instead of the placeholder if there's no guild
            no-guild: ''
            # The right bracket in the placeholder
            right-bracket: ']'
    damage:
        # Do we want people in the same guild to be able to damage each other?
        guild: false
        # Do we want allies to be able to damage each other?
        ally: false
        # Do we want to respect WorldGuard flags for PVP deny?
        # This will be checked first before checking same guild and ally.
        # This is ONLY needed if you have either of the above two options to set true.
        # ONLY PUT THIS ON TRUE IF YOU HAVE WORLDGUARD INSTALLED OR YOU WILL BREAK STUFF
        respect-wg-pvp-flag: false
    # Would you like to send players their guild's motd on login?
    motd-on-login: true
war:
    # How often (in minutes) can a guild be the defender in a war?
    # This is to help prevent abuse from guilds fighting each other to farm rewards.
    # This is defaulted to 1 day.
    defend-cooldown: 1440
    # Would you like to block commands while a player is in the war?
    disable-commands: false
    # How long does a defending guild have to accept a war challenge? (In seconds)
    accept-time: 120
    # What is the min number of players needed on each side for a war to start?
    min-players: 3
    # What is the max number of players allowed on each side for a war?
    max-players: 8
    # How long do players of both sides have to join the war? (In seconds)
    join-time: 60
    # How long should we wait to teleport the players and start the war after everyone joined?
    ready-time: 60
    post-challenge-commands:
        # Would you like to enable running commands after a challenge ends? (such as broadcasting)
        enabled: false
        # What commands would you like to run after a challenge ends??
        # Supports the following placeholder:
        # {challenger} - The name of the challenging Guild
        # {defender} - The name of the defending Guild
        # {winner} - The winner of the challenge
        # {loser} - The loser of the challenge
        commands: 
        - ''
    rewards:
        # Would you like to give rewards to the winning guild?
        enabled: false
        # What rewards (commands) would you like to run for the winning Guild?
        # Current supports {player}.
        rewards: 
        - ''
timers:
    cooldowns:
        # How often (in seconds) can a player set their guild home?
        sethome: 60
        # How often (in seconds) can a player go to their guild home?
        home: 60
        # How often (in seconds) can a player request to join a guild?
        request: 60
        # How often (in seconds) can a guild buy a buff?
        buff: 60
        # How long should a user have to wait before joining a new guild after leaving one?
        join: 120
    warmups:
        home:
            # Do you want to enable making players stand still before teleporting?
            enabled: false
            # How long should a user have to stand still before teleporting?
            time: 3
cost:
    # How much should it cost to create a guild?
    creation: 0.0
    # How much should it cost to set the cost of the guild home?
    sethome: 0.0
# This section of the config will allow you to handle guild land claiming.
# Remember that the enable / disable for this is the WorldGuard Hook at the TOP of the config.
# There are multiple options when it comes to guild claims. For the time being, all guilds will only get one claim.
claims:
    # This is the number of blocks around the player it will try to create the region.
    # Keep in mind this is the RADIUS, it will go this many blocks in both directions.
    # For example, if you take the default 15, it'll do 30 total as it will go 15 blocks in both directions.
    # This is a CUBOID region, not SPHERE.
    radius: 15
    # Customize the entrance and exit message of joining claims.
    # Supports {prefix} for guild prefix and {guild} for guild name.
    # Also supports color codes!
    enter-message: '&aNow entering &d{guild}''s &aclaim!'
    exit-message: '&aNow leaving &d{guild}''s &aclaim!'
    # Would you like to disable guild claiming in specific worlds?
    disabled-worlds: 
    - ''
    # Would you like to enable claim signs?
    # Format - 
    # First Line: [Guild Claim]
    # Second Line: WorldGuard Region Name
    # Third Line: Price
    claim-signs: false
    # Would you like to make it so that claims can only be aquired through the purchasing with signs?
    # This will disable the regular claim commands.
    force-claim-signs: false
tickets:
    # What do you want the name of the upgrade ticket to be?
    name: '&bGuild Upgrade Ticket'
    # What do you want the lore of the ticket to be?
    lore: 
    - '&dRight click this ticket to upgrade your guild tier!'
    # What do you want the material of the ticket to be?
    material: PAPER
codes:
    # How long do you want the default length of guild codes to be?
    length: 7
    # Do you want inactive codes (no uses left) to display on the /guild code list?
    list-inactive-codes: true
    # What is the max amount of active codes you would like to allow per guild?
    amount: 10

```

