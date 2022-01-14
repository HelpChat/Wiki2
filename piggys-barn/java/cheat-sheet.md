# Cheat Sheet

## Gradle Jar Directory

One of the most common requests I got with my hotswapping/productivity guide was how to configure the build tool to automatically output the plugin jar into the plugins folder. This is actually ridiculously simple to do. Simply copy the following:

```groovy
jar {
    destinationDirectory.set(file("server/plugins"))
}
```

{% hint style="info" %}
If using shadowJar, replace `jar` with `shadowJar`.
{% endhint %}

{% hint style="info" %}
This can also be used in regular, non-minecraft projects, however I usually don't use it in those, as I simply run the jar in build/libs.
{% endhint %}

## Run Configuration Keybinds

It's extremely practical to bind your run configurations to keys, as it can be quite a hassle to manually select the individual run configurations every time you need them. To add keybinds for these, you'll need to install the [Run Configuration as Action](https://plugins.jetbrains.com/plugin/9448-run-configuration-as-action) plugin by Turbanov Andrey.

![This menu can be accessed via File > Settings (ctrl + alt + s)](<../../.gitbook/assets/image (9).png>)

With this plugin installed, you'll then want to make your run configurations. Once made, go to the keymap in settings (file > settings, ctrl + alt + s). Open the plugins drop down, then scroll down to the Run Configuration as Action drop down, and also open that. Alternatively, you can search for your configuration name in the search bar.

![](<../../.gitbook/assets/image (10).png>)

![](<../../.gitbook/assets/image (11).png>)

There you'll be able to add keybinds for your run configurations by simply double clicking on one of the list items, and adding either a mouse or keyboard bind. As you can see, I've already assigned a keybind to my gradle jar run configuration.

