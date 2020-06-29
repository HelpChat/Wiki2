# Configuration

##Config

{% code title="config.yml" %}
```yaml
# InventoryFull version 1.8
# Created by: extended_clip
# Valid placeholders:
# %block% - display the dropped item type
# %player% - display the players name
#   
# For valid sounds, visit http://jd.bukkit.org/rb/apidocs/org/bukkit/Sound.html
cooldown_time: 5
max_alerts_until_cooldown: 5
sound_when_full:
  enabled: true
  sound: NOTE_PLING
  volume: 10
  pitch: 1
chat_message:
  use_chat_message: true
  message:
  - '&cYour inventory is full!'
actionannouncer:
  use_actionbar: false
  display_time: 5
  message:
  - '&cYour inventory is full!'
  - '&4Your inventory is full!'
titlemanager:
  use_title: false
  title: '&cYou don''t have room in your inventory'
  subtitle: to collect that &f%block%&c!
  fade_in: 12
  fade_out: 12
  duration: 20
  use_actionbar: false
  actionbar_message: '&cYou don''t have room in your inventory'
holographicdisplays:
  use_hologram: false
  message:
  - '&cYour inventory'
  - '&cis full!'
  display_time: 3```
{% endcode %}
