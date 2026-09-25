---
description: Add the ChatChat API dependency and obtain the registered service.
---

# Getting started

Declare the HelpChat snapshots repository and API dependency in your plugin build.

## Maven

```xml
<repositories>
    <repository>
        <id>helpchat-snapshots</id>
        <url>https://repo.helpch.at/snapshots/</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>at.helpch</groupId>
        <artifactId>chat-chat-api</artifactId>
        <version>1.0.0-SNAPSHOT</version>
        <scope>provided</scope>
    </dependency>
</dependencies>
```

## Gradle

```kotlin
repositories {
    maven("https://repo.helpch.at/snapshots/")
}

dependencies {
    compileOnly("at.helpch:chat-chat-api:1.0.0-SNAPSHOT")
}
```

## Get the API service

ChatChat registers `ChatChatAPI` with Bukkit's services manager. Check that ChatChat is enabled before looking up the provider.

```java
import at.helpch.chatchat.api.ChatChatAPI;
import org.bukkit.plugin.RegisteredServiceProvider;

RegisteredServiceProvider<ChatChatAPI> registration =
    getServer().getServicesManager().getRegistration(ChatChatAPI.class);

if (registration == null) {
    getLogger().severe("ChatChat API is unavailable");
    return;
}

ChatChatAPI chatChatAPI = registration.getProvider();
```

Use `softdepend: [ChatChat]` in your plugin metadata if your plugin can run without ChatChat. Disable your integration when the service is unavailable.
