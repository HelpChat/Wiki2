---
description: Plugin's placeholders
---

# Placeholders

## Plugin's placeholders

**DeluxeChat** has some placeholders built-into it:

| Placeholder                      | Description                                                                                                                                                                       |
| -------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| %server%                         | This placeholder works only if **BungeeCord** is enabled. It displays the prefix of the server (`server_prefix` in the config) the player in when chatting globally (`/GToggle`). |
| %recipient\_\<PAPI Placeholder>% | This placeholder is for private message formats. It returns the recipient's PlaceholderAPI placeholder value. e.g. `%recipient_vault_prefix%`.                                    |

## PlaceholderAPI placeholders

**DeluxeChat** plugin provides [**PlaceholderAPI** ](https://www.spigotmc.org/resources/6245/)placeholders that you can use in any plugin that supports [**PlaceholderAPI**](https://www.spigotmc.org/resources/6245/).\
You can also use any [**PlaceholderAPI**](https://www.spigotmc.org/resources/6245/) placeholder in **DeluxeChat** plugin. ([PlaceholderAPI placeholders list](https://helpch.at/placeholders))

### Placeholders

| Placeholder                        | Return Value | Description                                                           |
| ---------------------------------- | ------------ | --------------------------------------------------------------------- |
| %deluxechat\_is\_pm\_toggled%      | Boolean      | Returns whether if the player has private messages toggled on or not. |
| %deluxechat\_social\_spy\_enabled% | Boolean      | Returns whether if social spy mode is enabled or not.                 |
| %deluxechat\_pm\_recipient%        | Text         | Returns the private message recipient name. (Used in PM format)       |

### Download

To use these placeholders, you have to download **DeluxeChat Expansion**. You can download it automatically by running:

> `/papi ecloud download DeluxeChat`\
> `/papi reload`

Or you can download it manually from the [eCloud](https://api.extendedclip.com/expansions/deluxechat/), and put it inside the `expansions` folder (folder path: `/plugins/PlaceholderAPI/expansions/`).&#x20;
