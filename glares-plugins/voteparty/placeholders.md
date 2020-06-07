---
description: VoteParty's placeholders
---

# Placeholders

**VoteParty** provides [**PlaceholderAPI**](https://placeholderapi.com) placeholders that you can utilize inside any plugin that supports [**PlaceholderAPI**](https://placeholderapi.com).  
You can also use any [**PlaceholderAPI**](https://placeholderapi.com) ****placeholder inside of **VoteParty**. \([PlaceholderAPI placeholders list](https://helpch.at/placeholders)\)  
  
To utilize with plugins such as FeatherBoard, change the below placeholders from %% to {placeholderapi\_&lt;placeholder&gt;}.  
  
Example: {placeholderapi\_voteparty\_votes\_recorded}

<table>
  <thead>
    <tr>
      <th style="text-align:left">Placeholder</th>
      <th style="text-align:left">Return Value</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">%voteparty_votes_recorded%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Returns the current amount of votes towards a Vote Party.</td>
    </tr>
    <tr>
      <td style="text-align:left">%voteparty_votes_required_party%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Returns the amount of votes left that are needed for a Vote Party to happen.</td>
    </tr>
    <tr>
      <td style="text-align:left">%voteparty_votes_required_total%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Returns the total amount of votes needed for a Vote Party to happen.</td>
    </tr>
    <tr>
      <td style="text-align:left">%voteparty_player_votes%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">
        <p><b>DEPRECATED.</b>
        </p>
        <p>Returns the total amount of votes a player has.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">%voteparty_top_TYPE_INFO_PLACEMENT%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Returns information about the placement voter depending on the input.</td>
    </tr>
    <tr>
      <td style="text-align:left">%voteparty_placement_TYPE%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Returns the player&apos;s spot in the leaderboard with the given type.</td>
    </tr>
    <tr>
      <td style="text-align:left">%voteparty_totalvotes_TYPE%</td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Returns the total votes of a player in the time-frame of the type provided.</td>
    </tr>
  </tbody>
</table>

**Type**  
The type placeholder refers to the list of placeholders above that contain `TYPE` in them. The options for these are `daily`, `weekly`, `monthly`, and `alltime`.

**Info**  
The info placeholder refers to the list of placeholders above that contain `INFO` in them. The options for these can be `name` or `votes`.  
  
 The placement is just the placement of the player in the leaderboard, so like `1` would return the top voter, `2` would return the 2nd top voter, etc.  
 **Example Placeholders**:   
`%voteparty_top_alltime_name_1%` - Returns the name of the top voter of all time `%voteparty_top_monthly_name_1%` - Returns the name of the top voter in the past month

## Download

There is **no** download required anymore to utilize the **VoteParty** placeholders. It is all built into the plugin.

