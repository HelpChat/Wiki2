# Developer API

## Build Tool Stuff <a id="hooking-into-the-api"></a>

![](https://img.shields.io/badge/version-3.5.5.9-green)

{% tabs %}
{% tab title="Maven" %}
```markup
        <repository>
            <id>glares-repo</id>
            <url>https://repo.glaremasters.me/repository/public/</url>
        </repository>
        
        <dependency>
            <groupId>me.glaremasters</groupId>
            <artifactId>guilds</artifactId>
            <version>VERSION</version>
        </dependency>
```
{% endtab %}

{% tab title="Gradle" %}
```groovy
repositories {
    maven { 
        url = 'https://repo.glaremasters.me/repository/public/' 
    }
}

dependencies {
    compileOnly 'me.glaremasters:guilds:VERSION'
}
```
{% endtab %}
{% endtabs %}

## Hooking Into the API <a id="hooking-into-the-api"></a>

Obtaining the instance of the API is pretty simple by using the singleton that provides static access to the class. You can obtain the instance of the API through the main `Guilds` class.

```java
GuildsAPI api = Guilds.getApi();
```

## Using the API <a id="using-the-api"></a>

The API can be used for obtaining a bunch of information from the plugin. You can browse over the following section to see what all is provided.

### Getting a Guild object <a id="getting-a-guild-object"></a>

We provide a few ways to obtain a Guild object, so feel free to use what is easiest for you.

{% tabs %}
{% tab title="OfflinePlayer" %}
```kotlin
    /**
     *
     * Get the guild of a player
     * @param player the players you're getting the guild of
     * @return the guild that the player is in
     */
    fun getGuild(player: OfflinePlayer): Guild? {
        return guildHandler.getGuild(player)
    }
```
{% endtab %}

{% tab title="Guild UUID" %}
```kotlin
    /**
     * Get a guild by it's uuid
     * @param uuid uuid of the guild
     * @return the guild the uuid belong to
     */
    fun getGuild(uuid: UUID): Guild? {
        return guildHandler.getGuild(uuid)
    }
```
{% endtab %}

{% tab title="Guild Name" %}
```kotlin
    /**
     * Get a guild by it's name
     * @param name the name of the guild
     * @return the guild object
     */
    fun getGuild(name: String): Guild? {
        return guildHandler.getGuild(name)
    }
```
{% endtab %}
{% endtabs %}

### Getting a Guild Vault <a id="getting-a-guild-vault"></a>

```kotlin
   /**
     * Get a copy of one of a guild's vaults
     * @param guild the guild to get the vault of
     * @param vaultNumber which vault to get
     * @return guild vault
     */
    fun getGuildVault(guild: Guild, vaultNumber: Int): Inventory {
        return guildHandler.getGuildVault(guild, vaultNumber)
    }
```

### Getting a GuildRole <a id="getting-a-guildrole"></a>

```kotlin
    /**
     * Get the role of a player
     * @param player role
     * @return the role of a player
     */
    fun getGuildRole(player: Player): GuildRole? {
        return getGuild(player)?.getMember(player.uniqueId)?.role
    }
```

### Getting the GuildHandler <a id="getting-the-guildhandler"></a>

The GuildHandler will give you access to anything you might need in the plugin. Please use caution with this method as the content it lets you access to can break the plugin if you use it incorrectly.

```java
    /**
     * Get a copy of the guild handler
     * @return guild handler
     */
    public GuildHandler getGuildHandler() {
        return guildHandler;
    }
```

## Custom Events <a id="custom-events"></a>

In the plugin we offer a bunch of custom events that you can listen to and modify as you see fit.

### Base GuildEvent <a id="base-guildevent"></a>

```java
    /**
     * Base guild event
     * @param player player in event
     * @param guild guild in the event
     */
    public GuildEvent(Player player, Guild guild) {
        super(player);
        this.guild = guild;
    }
```

### GuildAddAllyEvent <a id="guildaddallyevent"></a>

```java
    /**
     * This event takes place when two guilds ally each other
     * @param player player who accepted
     * @param guild guild one
     * @param ally guild two
     */
    public GuildAddAllyEvent(Player player, Guild guild, Guild ally) {
        super(player, guild);
        this.ally = ally;
    }
```

### GuildCreateEvent <a id="guildcreateevent"></a>

```java
    /**
     * Called when people create a guild
     * @param player player creating the guild
     * @param guild the guild being created
     */
    public GuildCreateEvent(Player player, Guild guild) {
        super(player, guild);
    }
```

### GuildDepositMoneyEvent <a id="guilddepositmoneyevent"></a>

```java
    /**
     * Base guild event
     *  @param player player in event
     * @param guild  guild in the event
     * @param amount the amount to deposit
     */
    public GuildDepositMoneyEvent(Player player, Guild guild, double amount) {
        super(player, guild);
        this.amount = amount;
    }
```

### GuildInviteEvent <a id="guildinviteevent"></a>

```java
    /**
     * Called when a player gets invited to a guild
     * @param player the player inviting other to guild
     * @param guild the guild player will be joining
     * @param invitedPlayer the player being invited
     */
    public GuildInviteEvent(Player player, Guild guild, Player invitedPlayer) {
        super(player, guild);
        this.invitedPlayer = invitedPlayer;
    }
```

### GuildJoinEvent <a id="guildjoinevent"></a>

```java
    /**
     * Called when a player joins a guild
     * @param player the player joining a guild
     * @param guild the guild the player will be joining
     */
    public GuildJoinEvent(Player player, Guild guild) {
        super(player, guild);
    }
```

### GuildLeaveEvent <a id="guildleaveevent"></a>

```java
    /**
     * Called a when a player leaves the guild
     * @param player the player leaving the guild
     * @param guild the guild the player was leaving
     */
    public GuildLeaveEvent(Player player, Guild guild) {
        super(player, guild);
    }
```

### GuildKickEvent

```java
/**
* Called when a player is kicked from the guild
* @param player the player executing the event
* @param kicked the player being kicked from the guild
* @param cause the cause for being kicked
*/
class GuildKickEvent(player: Player, guild: Guild, val kicked: OfflinePlayer, val cause: Cause) : GuildEvent(player, guild) {

    enum class Cause {
        PLAYER_KICKED, ADMIN_KICKED
    }
}
```

### GuildPrefixEvent <a id="guildprefixevent"></a>

```java
    private String prefix;

    /**
     * Base guild event
     *  @param player player in event
     * @param guild  guild in the event
     * @param prefix
     */
    public GuildPrefixEvent(Player player, Guild guild, String prefix) {
        super(player, guild);
        this.prefix = prefix;
    }

    public String getPrefix() {
        return prefix;
    }
```

### GuildRemoveAllyEvent <a id="guildremoveallyevent"></a>

```java
    /**
     * Called when a guild removes an ally
     * @param player the player calling the removal
     * @param guild the guild calling the removal
     * @param ally the guild being removed
     */
    public GuildRemoveAllyEvent(Player player, Guild guild, Guild ally) {
        super(player, guild);
        this.ally = ally;
    }
```

### GuildRemoveEvent <a id="guildremoveevent"></a>

```java
    private String name;
    
    /**
     * Called when a guild is removed
     * @param player the player removing the guild
     * @param guild the guild getting removed
     * @param cause the reason for the guild being removed
     */
    public GuildRemoveEvent(Player player, Guild guild, Cause cause) {
        super(player, guild);
        this.cause = cause;
    }

    public enum Cause {
        MASTER_LEFT,
        PLAYER_DELETED,
        ADMIN_DELETED
    }
```

### GuildRenameEvent <a id="guildrenameevent"></a>

```java
    /**
     * @param player player in event
     * @param guild  guild in the event
     */
     public GuildRenameEvent(Player player, Guild guild, String newName) {
        super(player, guild);
        this.name = newName;
    }

    public String getName() {
        return name;
    }
```

### GuildTransferEvent <a id="guildtransferevent"></a>

```java
private Player newMaster;

    /**
     * Base guild event
     *  @param player player in event
     * @param guild  guild in the event
     * @param newMaster
     */
    public GuildTransferEvent(Player player, Guild guild, Player newMaster) {
        super(player, guild);
        this.newMaster = newMaster;
    }

    public Player getNewMaster() {
        return newMaster;
    }
```

### GuildWithdrawMoneyEvent <a id="guildwithdrawmoneyevent"></a>

```java
    /**
     * @param player player in event
     * @param guild  guild in the event
     * @param amount the amount to withdraw
     */
    public GuildWithdrawMoneyEvent(Player player, Guild guild, double amount) {
        super(player, guild);
        this.amount = amount;
    }a
```

### GuildWarAcceptEvent

```kotlin
/**
 * Called when a guild war has been accepted
 * @param player the player that accepted the war challenge
 * @param challenger the challenging guild for the war
 * @param defender the defending guild for the war
 */
class GuildWarAcceptEvent(player: Player, val challenger: Guild, val defender: Guild) : GuildEvent(player, defender)
```

### GuildWarChallengeEvent

```kotlin
/**
 * Called when a guild war challenge has been sent from one guild to another
 * @param player the player that sent the war challenge
 * @param challenger the challenging guild for the war
 * @param defender the defending guild for the war
 */
class GuildWarChallengeEvent(player: Player, val challenger: Guild, val defender: Guild) : GuildEvent(player, challenger)
```

### GuildWarDeclineEvent

```kotlin
/**
 * Called when a guild war has been declined
 * @param player the player that declined the challenge
 * @param challenger the challenging guild for the war
 * @param defender the defending guild for the war
 */
class GuildWarDeclineEvent(player: Player, val challenger: Guild, val defender: Guild) : GuildEvent(player, defender)
```

### GuildWarEndEvent

```kotlin
/**
 * Called when a guild war has ended
 * @param challenger the challenging guild for the war
 * @param defender the defending guild for the war
 * @param winner the winner of the guild war
 */
class GuildWarEndEvent(val challenger: Guild, val defender: Guild, val winner: Guild) : Event() {

    override fun getHandlers(): HandlerList {
        return handlerList
    }

    companion object {
        val handlerList = HandlerList()
    }
}

```

### GuildWarStartEvent

```kotlin
/**
 * Called when a guild war has started
 * @param challenger the challenging guild for the war
 * @param defender the defending guild for the war
 */
class GuildWarStartEvent(val challenger: Guild, val defender: Guild) : Event() {

    override fun getHandlers(): HandlerList {
        return handlerList
    }

    companion object {
        val handlerList = HandlerList()
    }
}

```

