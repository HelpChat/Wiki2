---
description: >-
  Totally customizable alert plugin to inform players when they don't have
  inventory space!way
---

# InventoryFull

## Description

**InventoryFull** is a very small plugin that alerts players when they don't have inventory space!

Simply enable any of the following ways to alert players in the config file and use /invfull reload. After the alert type is enabled, when players get a full inventiry they will be alerted!

## Features

* 5 Ways to send the full inventory alert.
* Highly customizable.
* Play a sound when the alert is sent.

## Alerts

Types of alerts:

* ChatMessage - send an inventory full message through chat!
* Actionbar \(Requires [ActionAnnouncer](https://www.spigotmc.org/resources/actionannouncer.1320/)\) - send an inventory full message through the actionbar!
* Title and subtitle \(Requires [TitleManager](https://www.spigotmc.org/resources/titlemanager.1049/)\) - send an inventory full message through the Title and subtitle!
* Holograms \(Requires [HolographicDisplays](https://www.spigotmc.org/resources/titlemanager.1049/)\) - send an inventory full message with a hologram!
* Sound - play a sound to a player when they have a full inventory!

## API

There is an API that will allow you to listen to a special event that is fired when a player has a full inventory and breaks a block that won't fit!

Here is an example:

```yaml
@EventHandler
public void onFull(InventoryFullEvent e) {

    //player with full inventory
    Player p = e.getPlayer();

    //item that does not fit in players inventory
    ItemStack i = e.getItem();

}
```

