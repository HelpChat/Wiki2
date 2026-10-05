---
description: Easy-to-follow-steps on how to get started with the plugin!
---

# Installation

## First-Time Setup

1. **Stop** your server.
2. Put the **Guilds jar** file that you downloaded into your **plugins** folder.
3. Install the [required dependencies](#plugin-dependencies).
4. **Start** your server.
5. Modify the **config.yml**, **language files**, and all other files to your liking for your server. (All found in `/plugins/Guilds/`.)

## Requirements

### Java and Minecraft

Guilds needs Java 11 or newer at runtime. That floor holds no matter how old your Minecraft is, so a 1.8.8 server runs on Java 11.

Minecraft and Java are separate choices. Use the Java your Minecraft version needs, as long as it is 11 or higher:

| Minecraft / Paper | Java |
| ----------------- | ---: |
| 1.8.8             | 11   |
| 1.16.5            | 16   |
| 1.18.2            | 17   |
| 1.19.4            | 17   |
| 1.20.6            | 21   |
| 1.21.1            | 21   |
| 1.21.4            | 21   |
| 1.21.8            | 21   |

Guilds is tested against Spigot and Paper.

### Plugin Dependencies

**Vault:** Required. Guilds will not enable without it.

**Economy Plugin:** Required. Guilds reaches the economy through Vault and disables itself if it cannot find one. EssentialsX and TheNewEconomy are both popular choices.

**Permission Plugin:** Required. Guilds reaches permissions through Vault and disables itself if it cannot find one. LuckPerms is a popular choice.

A missing dependency produces a console message naming it, so a failed install tells you what went wrong instead of misbehaving later.

**WorldGuard, PlaceholderAPI and Essentials** are optional. The [plugin README](./README.md#optional-dependencies) covers what each one adds.

### Server Dependencies

**CPU:** The plugin will run just fine on basically any modern CPU. It's optimized to be smooth and non-intensive to the server it runs on.

**RAM:** The project uses fairly little RAM. Via testing, the smallest it has run fine on was about 256MB if you were to have about 100 guilds or so running on the server.

**Disk Space:** The project uses very little space. It's optimized to keep itself clean and not bloat up your drive.

### SQL Dependencies

**MySQL:** If you choose to use MySQL, please make sure your database version is 5.7.8 or **higher**.

**MariaDB:** If you choose to use MariaDB, please make sure your database version is 10.2.7 or **higher**.

## Reloading

`/guild reload` applies `config.yml` and `buffs.yml` only. Changes to `roles.yml` and `tiers.yml` need a server restart.

If `/guild console migrate` fails partway through, autosaving can stay switched off until you restart the server. Check your guilds are still saving after a failed migration.

A mistyped `storage-type` in `config.yml` is reported in the console at startup rather than being ignored.
