cec-audio-mqtt-bridge
===============

A HDMI-CEC Audio to MQTT bridge written in Python 3 for connecting your AV-devices to your Home Automation system. Volume commands from the TV's remote are received and broadcast over MQTT.

# Features
* CEC
  * Exposes itself as an audio receiver
  * Receives volume up/down/mute commands.

# Dependencies

## MQTT (required)
* MQTT broker (like [Mosquitto](https://mosquitto.org/))

## HDMI-CEC
* libcec4 with python bindings (https://github.com/Pulse-Eight/libcec)
  * You can compile the bindings yourself, or use precompiled packages from my [libcec directory](libcec/).
* HDMI-CEC interface device (like a [Pulse-Eight](https://www.pulse-eight.com/) device, or a Raspberry Pi)

# MQTT Topics

The bridge publishes to the following topics:

| topic                   | body                                    | remark                                           |
|:------------------------|-----------------------------------------|--------------------------------------------------|
| `prefix`/cec/volumeup   | `on` / `off`                            | Received volume up command from TV remote        |
| `prefix`/cec/volumedown | `on` / `off`                            | Received volume down command from TV remote      |
| `prefix`/cec/volumemute | `on` / `off`                            | Received volume mute command from TV remote      |

# Interesting links
* https://github.com/nvella/mqtt-cec
* http://www.cec-o-matic.com/
* http://wiki.kwikwai.com/index.php?title=The_HDMI-CEC_bus
