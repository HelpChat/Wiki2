---
description: List of commands and permissions for the plugin
---

# Commands & Permissions

## Player Commands

| Command        | Permission               | Description                                                       | Aliases                                   |
| -------------- | ------------------------ | ----------------------------------------------------------------- | ----------------------------------------- |
| /SellAll       | AutoSell.SellAll         | Sells all items in your inventory to the shop you have access to. | Sell, SellItems, SellInv, SellInventory   |
| /AutoSell      | AutoSell.Toggle          | Toggles auto selling.                                             | AS, ASell, AutoS                          |
| /AutoSmelt     | AutoSell.AutoSmelt       | Toggles auto smelting.                                            | ASmelt, Smelt                             |
| /AutoBlocks    | AutoSell.AutoBlocks      | Toggles auto ingots to blocks converter.                          | I2B, ToBlocks, 2Blocks, Ingots2Blocks     |
| /Items \[Shop] | AutoSell.Items           | Displays items with their prices on a menu.                       | Prices, ItemPrices, ShopPrices, ShopItems |
| /ASMultiplier  | AutoSell.Multiplier.Self | Checks your current multiplier.                                   | Multi, ASMulti, Multiplier                |
| /ASWorth       | AutoSell.Worth           | Checks how much does the item in your hand worth.                 | ShopWorth, ShopPrice, ASPrice             |
| /BPToggle      | AutoSell.BPToggle        | Toggles selling item from VKBackPack                              | BackPackToggle                            |

## Admin Commands

| Command                                                                                                      | Permission           | Description                                                |
| ------------------------------------------------------------------------------------------------------------ | -------------------- | ---------------------------------------------------------- |
| /ASA Version                                                                                                 | AutoSell.Admin       | Shows the plugin's version.                                |
| /ASA Reload                                                                                                  | AutoSell.Reload      | Reloads the plugin's files.                                |
| /ASA Shops                                                                                                   | AutoSell.Admin       | Lists loaded shops.                                        |
| /ASA AddShop \<Name>                                                                                         | AutoSell.Admin       | Adds new shop.                                             |
| /ASA DelShop \<Name>                                                                                         | AutoSell.Admin       | Deletes the shop.                                          |
| /ASA Items \[Shop]                                                                                           | AutoSell.Admin       | Lists shop's items.                                        |
| /ASA AddItem \<Shop> \<Cost>                                                                                 | AutoSell.Admin       | Adds the item you're holding to the shop.                  |
| /ASA DelItem \<Shop>                                                                                         | AutoSell.Admin       | Removes the item you're holding from the shop.             |
| /ASA SetMultiplier \<Player/Global> \<Multiplier> \<Days>:\<Hours>:\<Minutes>                                | AutoSell.Admin       | Sets the player or the global multiplier.                  |
| <p>/ASA AddMultiplier <br>&#x3C;Player/Global> &#x3C;Multiplier> &#x3C;Days>:&#x3C;Hours>:&#x3C;Minutes></p> | AutoSell.Admin       | Adds on to the player or the global multiplier.            |
| /ASA StackMultiplier \<Player/Global> \<Multiplier> \<Days>:\<Hours>:\<Minutes>                              | AutoSell.Admin       | Stack time on the player or the global current multiplier. |
| /ASA DelMultiplier \<Player/Global>                                                                          | AutoSell.Admin       | Removes the player or the global multiplier.               |
| /ASA AddSign \<Shop>                                                                                         | AutoSell.Signs.Admin | Adds sell all sign, the one you're looking at.             |
| /ASA DelSign                                                                                                 | AutoSell.Signs.Admin | Removes the sign you're looking at.                        |
| /ASA WhatArea                                                                                                | AutoSell.WhatArea    | Gets the mine/region name you're standing in.              |

#### Command Alias

* /AutoSellAdmin

## Permissions

| Permission                     | Description                                                                                  |
| ------------------------------ | -------------------------------------------------------------------------------------------- |
| AutoSell.Fortune               | Gives the ability to use autosell's fortune feature.                                         |
| AutoSell.Signs.Sell            | Gives the ability to sell all using a sell all sign.                                         |
| AutoSell.BlocksToInventory     | Gives the ability to mine blocks straight to your inventory.                                 |
| AutoSell.Shop.\<Name>          | Sets the player's current shop if he isn't in any shop region.                               |
| AutoSell.AutoSmelt.All         | Gives the ability to auto smelt all blocks in the smelt list. (Auto Smelt has to be enabled) |
| AutoSell.AutoSmelt.\<Material> | Gives the ability to auto smelt the specified material. (Auto Smelt has to be enabled)       |

{% hint style="info" %}
All text between the less-than and greater-than signs (**<>**) is a placeholder/variable, replace it with the requested value without the less-than and greater-than signs (**<>**).
{% endhint %}
