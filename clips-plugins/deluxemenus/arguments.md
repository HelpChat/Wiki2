# Arguments

> ```yaml
> args:
>   target: 1
>   time: 1
>   reason: -1
> ```
>
> The keys in this config section are the placeholders and will be parsed when using for example `{target}` \(the value in the config section will indicate how many words the {target} placeholder will require\). In the example below we can use "/punish   " and there must be at least 3 arguments after open command. Setting a value of an argument key to `-1` allows every arg to be included in that "arg".

`/punish HelpChat 15min Example`

`Target = HelpChat` `Time = 15min` `Reason = Example` _Values specified in the command will be display when using that placeholder_

**NOTE**: The `-1` can only be used as the last "arg" in your arg list in the config which means the arg spans from the start of the "reason" until the end of the string provided. If you want the reason to only contain a specific amount of words change the value to: `reason: 1` \(reason will be 1 word\), `reason: 2` \(reason will be 2 words\).

If you add this "args" option to a menu, the menu will not open if the required arg amount is not provided with the command. You must also specify an "args\_usage\_message" to tell the person opening the menu the correct usage: \(in this case being the correct punish command\)

> ```yaml
> args_usage_message: "/punish <player> <time> <reason>"
> ```

From here, you can use the new "arg" placeholders in any of your "click commands".

**NOTE**: As of right now arg placeholders are not parsed in requirements. The only place they are parsed are in _material, display\_name, lore_ and _"click command"_

**Example:** \(Punishment menu\)

> ```yaml
> items:
>   '1':
>     material: Barrier
>     amount: 1
>     slot: 11
>     display_name: '&8&l> &aMute'
>     lore:
>     - '&r'
>     - '&8» &bTarget&8: &7{target}'
>     - '&8» &bTime&8: &7{time}'
>     - '&8» &bPunishment&8: &7{reason}'
>     - '&r'
>     left_click_commands:
>     - '[player] warn {target} {reason}'
>     - '[close]'
>     - '[broadcast] &b{target}&7 has been warned for&8: &b{reason}'
>     right_click_commands:
>     - '[player] warn {target} {reason}'
>     - '[close]'
>     - '[broadcast] &b{target}&7 has been warned for&8: &b{reason}'
> ```

![Punishment Menu](https://imgur.com/VlrgkPK.png)

