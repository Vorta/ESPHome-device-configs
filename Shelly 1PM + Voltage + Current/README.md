# Shelly 1PM with Voltage and Current metering
**To do this you need to modify the hardware of your Shelly 1PM!**

It is possible to solder unused GPIO pins to the power metering chip. I have done
a few so this is my ESPHome config for those Shellies. You may need to modify `cf1_pin`
and `sel_pin` parameters if you solder the wires differently.
