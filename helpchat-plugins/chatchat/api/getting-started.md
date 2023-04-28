---
description: Get started using the ChatChat API.
---

# Getting Started

### Declare the ChatChat API repository and dependency in your build files

#### Maven

```xml
<repositories>
    <repository>
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

#### Gradle

```kotlin
repositories {
    maven("https://repo.helpch.at/snapshots/")
}
dependencies {
    compileOnly("at.helpch:chat-chat-api:1.0.0-SNAPSHOT")
}
```

## Get an instance of the ChatChatAPI

The ChatChatAPI interface is how you can access and modify most functionalities of ChatChat.

```java
package at.helpch.example;

import at.helpch.chatchat.api.ChatChatAPI;
import org.bukkit.plugin.RegisteredServiceProvider;
import org.bukkit.plugin.java.JavaPlugin;
import org.jetbrains.annotations.NotNull;

public class ExamplePlugin extends JavaPlugin {

    private ChatChatAPI chatChatAPI;

    @Override
    public void onEnable() {
        if (!getServer().getPluginManager().isPluginEnabled("ChatChat")) {
            getLogger().severe("Could not find ChatChat! Disabling plugin...");
            getServer().getPluginManager().disablePlugin(this);
            return;
        }

        RegisteredServiceProvider<ChatChatAPI> registeredServiceProvider = getServer().getServicesManager().getRegistration(ChatChatAPI.class);
        if (registeredServiceProvider == null) {
            getLogger().severe("Could not find the ChatChatAPI! Disabling plugin...");
            getServer().getPluginManager().disablePlugin(this);
            return;
        }

        chatChatAPI = registeredServiceProvider.getProvider();
    }

    @Override
    public void onDisable() {
        getLogger().info("Disabling plugin...");
        chatChatAPI = null;
    }

    public @NotNull ChatChatAPI getChatChatAPI() {
        return chatChatAPI;
    }
}

```
