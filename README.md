
# ha-tasmota
Tasmota ws2812 custom component for Home Assistant

Made to control WS2812 Led strips via MQTT.

Based on inbuilt [MQTT Light](https://home-assistant.io/components/light.mqtt/) component of [Home Assistant](https://home-assistant.io/) to work with Theo Arendst's [Tasmota](https://github.com/arendst/Sonoff-Tasmota) custom firmware for iTead Sonoff components 

Sample configuration in light.yaml

    - platform: tasm
      name: "User-friendly name of the device"
      on_command_type: first
      state_topic: "stat/project/POWER1"
      command_topic: "cmnd/project/POWER1"
      brightness_state_topic: "stat/project/RESULT"
      brightness_command_topic: "cmnd/project/Dimmer"
      brightness_value_template: "{{ value_json.Dimmer }}"
      rgb_state_topic: "stat/project/RESULT"
      rgb_command_topic: "cmnd/project/Color"
      rgb_value_template: "{{ value_json.Color }}"
      effect_command_topic: "cmnd/project/Scheme"
      effect_state_topic: "stat/project/RESULT"
      effect_value_template: "{{  value_json.Scheme  }}"
      qos: 0
      payload_on: "ON"
      payload_off: "OFF"
      optimistic: false

**TODO:**
 - Code optimization to minimize the parameters down to: Name, stat,
   cmnd
