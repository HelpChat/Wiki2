# Configuration

## Config

{% code title="config.yml" %}
```yaml
# MessageAnnouncer v1.11.0 Main configuration
announcer_enabled: true
announcer_random: true
announce_interval: 60
sound:
  enabled: true
  sound_name: NOTE_PLING
  volume: 10
  pitch: 1
interval_announcement_list:
- default
- vote
announcements:
  default:
  - '{"text": "--------"}'
  - '{"text": "This is a JSON auto announcement!"}'
  - '{"text": "--------"}'
  vote:
  - '{"text": "--------"}'
  - '{"text": "Be sure to vote for the server!"}'
  - '{"text": "--------"}'
```
{% endcode %}

