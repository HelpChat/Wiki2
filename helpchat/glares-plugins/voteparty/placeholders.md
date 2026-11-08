---
description: VoteParty's placeholders
---

# Placeholders

**VoteParty** provides [**PlaceholderAPI**](https://placeholderapi.com) placeholders that you can utilize inside any plugin that supports [**PlaceholderAPI**](https://placeholderapi.com).\
You can also use any [**PlaceholderAPI**](https://placeholderapi.com) placeholder inside of **VoteParty**. ([PlaceholderAPI placeholders list](https://helpch.at/placeholders))\
\
To utilize with plugins such as FeatherBoard, change the below placeholders from %% to {placeholderapi\_\<placeholder>}.\
\
Example: {placeholderapi\_voteparty\_votes\_recorded}

| Placeholder                             | Return Value | Description                                                                                              |
| --------------------------------------- | ------------ | -------------------------------------------------------------------------------------------------------- |
| %voteparty\_votes\_recorded%            | Text         | Returns the current amount of votes towards a Vote Party.                                                |
| %voteparty\_votes\_required\_party%     | Text         | Returns the amount of votes left that are needed for a Vote Party to happen.                             |
| %voteparty\_votes\_required\_total%     | Text         | Returns the total amount of votes needed for a Vote Party to happen.                                     |
| %voteparty\_player\_votes%              | Text         | <p><strong>DEPRECATED.</strong></p><p>Returns the total amount of votes a player has.</p>                |
| %voteparty\_votes\_total%               | Text         | Returns the total votes of all players                                                                   |
| %voteparty\_top\_TYPE\_INFO\_PLACEMENT% | Text         | Returns information about the placement voter depending on the input.                                    |
| %voteparty\_placement\_TYPE%            | Text         | Returns the player's spot in the leaderboard with the given type.                                        |
| %voteparty\_totalvotes\_TYPE%           | Text         | Returns the total votes of a player in the time-frame of the type provided.                              |
| %voteparty\_totalparties\_TYPE%         | Text         | Returns the total amount of parties the server has had in a given time-frame based on the type provided. |

**Type**\
The type placeholder refers to the list of placeholders above that contain `TYPE` in them. The options for these are `daily`, `weekly`, `monthly`, `lastmonth`, `annually` and `alltime`.

**Info**\
The info placeholder refers to the list of placeholders above that contain `INFO` in them. The options for these can be `name` or `votes`.\
\
&#x20;The placement is just the placement of the player in the leaderboard, so like `1` would return the top voter, `2` would return the 2nd top voter, etc.\
&#x20;**Example Placeholders**: \
`%voteparty_top_alltime_name_1%` - Returns the name of the top voter of all time `%voteparty_top_monthly_name_1%` - Returns the name of the top voter in the past month

## Download

There is **no** download required anymore to utilize the **VoteParty** placeholders. It is all built into the plugin.
