# Configuration

> # EZPrestige version: 1.2.2 Main Configuration
> # Via config.helpch.at
> # 
> # prestige_rank: <rank players are able to /prestige>
> # confirm_to_prestige: <true/false>
> # chat_integration: <true/false>
> # messages: <-customize your messages
> # valid placeholders: 
> # %cost% - cost to prestige
> # %balance% - players balance
> # %prestige% - next prestige number
> # %displaytag% - next prestige displaytag
> # %prestigerank% - rank player needs to be to use /prestige
> # %rank% - players permission group
> prestige_rank: Free
> confirm_to_prestige: true
> chat_integration: true
> op_prestige_display_tag: '&8[&c999&8]'
> no_prestige_display_tag: '&8[&c0&8]'
> gui:
>   use_prestiges_gui: true
>   display_name: '&cPrestiges'
>   size: 18
>   completed_prestige:
>     material: STAINED_GLASS_PANE
>     data: 13
>     amount: 1
>     display_name: '%displaytag%'
>     lore:
>     - '&acompleted'
>   current_prestige:
>     material: STAINED_GLASS_PANE
>     data: 5
>     amount: 1
>     display_name: '%displaytag%'
>     lore:
>     - '&aYour current prestige'
>   next_prestige:
>     material: STAINED_GLASS_PANE
>     data: 7
>     amount: 1
>     display_name: '%displaytag%'
>     lore:
>     - '&7Next prestige'
>     - '&a$&f%cost%'
>   unavailable_prestige:
>     material: STAINED_GLASS_PANE
>     data: 14
>     amount: 1
>     display_name: '%displaytag%'
>     lore:
>     - '&cPrestige to unlock'
>     - '%displaytag%'
> messages:
>   not_at_prestige_rank:
>   - '&cYou need to be &f%prestigerank% &cto prestige!'
>   not_enough_money:
>   - '&cYou need &a$&f%cost% &cto prestige to &f%displaytag%&c!'
>   confirm_prestige:
>   - '&bAre you sure you want to prestige?'
>   - '&bYour rank will reset and you will need to'
>   - '&bstart over. Type &f/prestige &bto confirm!'
>   last_prestige:
>   - '&bYou are at the last prestige!'
>   prestiges_command:
>     completed_prestige: '&7%displaytag% &f- &aCompleted'
>     current_prestige: '&7%displaytag% &f- &aCurrent prestige!'
>     next_prestige: '&7%displaytag% &f- &a$&f%cost%'
>     unavailable_prestige: '&7%displaytag% &f- &cPrestige to unlock!'
>     header:
>     - '&8&m-----------------------------------------------------'
>     - '&cPrestige list:'
>     footer:
>     - '&8&m-----------------------------------------------------'
