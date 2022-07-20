# Custom Components
I am not the author of the custom component required to use the sensors.
Original repo is here: https://github.com/persuader72/esphome-components

At the time when I was setting my Shelly 1PM up with the sensors the code in
the original repo did not compile and I found no working code. Therefore I
have mixed in the fixes needed for it to run myself. This version compiles
with ESPHome v2022.3.1. If the original author updates his repo I will remove
the component and just link to it.

## Installing the custom component
The `shelly_dallas` folder should be located here:
`config/esphome/custom_components/shelly_dallas`. Only then will ESPHome be
able to recognize the required config.

## Finding the sensor IDs
I have added placeholder sensor IDs in the YAML. I suggest you comment out the
entire following block for the first launch:
```yaml
  - platform: shelly_dallas
    address: 0x123456789000ab28
    name: "${device_name} Temperature Sensor 1"
    id: "${device_id}_temperature_sensor_1"
    device_class: temperature
    state_class: measurement
  - platform: shelly_dallas
    address: 0x123456789000cd28
    name: "${device_name} Temperature Sensor 2"
    id: "${device_id}_temperature_sensor_2"
    device_class: temperature
    state_class: measurement
  - platform: shelly_dallas
    address: 0x123456789000ef28
    name: "${device_name} Temperature Sensor 3"
    id: "${device_id}_temperature_sensor_3"
    device_class: temperature
    state_class: measurement
```
When the firmware is compiled and runs, monitor the logger as you will get the
IDs of the sensors there. They will be listed like this:
```txt
[20:20:20][D][dallas.sensor:079]:   Found sensors:
[20:20:20][D][dallas.sensor:081]:     0x123456789000ab28
[20:20:20][D][dallas.sensor:081]:     0x123456789000cd28
[20:20:20][D][dallas.sensor:081]:     0x123456789000ef28
```