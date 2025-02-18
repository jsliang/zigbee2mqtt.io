---
title: "Sunricher ZG9101SAC-HP control via MQTT"
description: "Integrate your Sunricher ZG9101SAC-HP via Zigbee2mqtt with whatever smart home
 infrastructure you are using without the vendors bridge or gateway."
---

*To contribute to this page, edit the following
[file](https://github.com/Koenkk/zigbee2mqtt.io/blob/master/docgen/device_page_notes.js)*

# Sunricher ZG9101SAC-HP

| Model | ZG9101SAC-HP  |
| Vendor  | Sunricher  |
| Description | ZigBee AC phase-cut dimmer |
| Supports | on/off, brightness |
| Picture | ![Sunricher ZG9101SAC-HP](../images/devices/ZG9101SAC-HP.jpg) |

## Notes

None

## Manual Home Assistant configuration
Although Home Assistant integration through [MQTT discovery](../integration/home_assistant) is preferred,
manual integration is possbile with the following configuration:


### ZG9101SAC-HP
{% raw %}
```yaml
light:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    brightness: true
    schema: "json"
    command_topic: "zigbee2mqtt/<FRIENDLY_NAME>/set"

sensor:
  - platform: "mqtt"
    state_topic: "zigbee2mqtt/<FRIENDLY_NAME>"
    availability_topic: "zigbee2mqtt/bridge/state"
    unit_of_measurement: "-"
    value_template: "{{ value_json.linkquality }}"
```
{% endraw %}


