# Multizone-Heating-Blueprint
Control room temperatures with virtual thermostats, one relay on boiler, window sensors, and TRV's in each room
Each room will send command to the boiler relay to start heating, but will switch to off only when the last room gets to the target setpoint of the room.

## !!!! IMPORTANT !!!!

TRV of the radiator should be set to maximum setpoint, it will allwasy be on, but we will controll the opening degree ov the valve.
States of "heat" and "idle"of the room thermostat will open or close the TRV's valve, heat to 100%, idle to 5% (0 or 5 is closed, as for my setup)
Window sensors will turn the room thermostat to OFF, so the TRV will be set to OFF as well. In my setup (TRVZB from Sonoff, does not take commands while off, so even if i set the valvle to 100% it will automatically get back to 0%)


## !!!!! SETPOINT SELECT YAML FILE !!!!!


In my setup i have an ARISTON CLAS ONE Boiler, and it can be integrated in Home Assistant so in my case i needed the request of heat to be always on, but for energy consumption economy i had to set the setpoint low si i can heat a room with a FAN.
This follows the explanation above but instead of turning of a relay switch it's setting the setpoint of the boiler to a desired value, when heating to 55, when idle to 38, so that the boiler keeps a low temp for the fan to work, and the rooms will be controlled by the TRV's.
