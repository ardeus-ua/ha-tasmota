# ha-tasmota
tasmota ws2812 custom component for Home Assistant

Sample configuration in light.yaml

- platform: tasm
  name: "User-friendly name of the device"
  on_command_type: first
  state_topic: "stat/project/POWER1"
  command_topic: "cmnd/project/POWER1"
  brightness_state_topic: "stat/project/RESULT"
  brightness_command_topic: "cmnd/project/Dimmer"
  brightness_value_template: "{{ value_json.Dimmer }}"
  brightness_scale: 100
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
