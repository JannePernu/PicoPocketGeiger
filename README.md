# Raspberry Pi Pocket Geiger library

A Raspberry Pi library to interface with the [Radiation Watch Pocket Geiger counter](http://www.radiation-watch.co.uk/) (Type 5).

The library monitors the Pocket Geiger through interrupts - using the machine package instead of the original [RPi.GPIO](https://pypi.python.org/pypi/RPi.GPIO) package - and processes the CPM and hourly [Sievert dose](https://en.wikipedia.org/wiki/Sievert).

Learn more about the Pocket Geiger counter on the Radiation Watch [FAQ](http://www.radiation-watch.co.uk/faqs) and on [our blog](https://blog.ytotech.com/2016/03/04/radiation-watch-raspberry/). Actually it is not a proper Geiger-Müller counter, but a Photodiode PIN sensor that can effectively counts gamma rays.

# Getting started

## Install the library

MicroPython, which is used here, has the machine library by default.

## Wiring

The Pocket Geiger must be wired to the GPIO ports of the Raspberry Pi. Refer to the GPIO pin specification of your RPi revision.

For exemple you can wire the radiation and the noise pin on respectively the `GPIO24` and `GPIO23` of your Raspberry Pi.

| Pocket Geiger pin | Raspberry Pi Pico pin | Standing for |
| ----------------- | --------------------- | ------------ |
| `+V` | `3V3` | Alimentation pin (DC 3V~9V) |
| `GND` | `GND` | Ground pin |
| `SIG` | `GP27` | Radiation-detection pulse pin |
| `NS` | `GP26` | Noise-detection pulse pin |


# Note on Noise

Remember the Pocket Geiger can't record correctly in presence of vibration. For a more precise and mobile oriented unit, you may look at the [bGeigie Nano](http://blog.safecast.org/bgeigie-nano/) from the Safecast project.

-----------------------

### Credits

Created upon the [Radiation Watch sample code](http://radiation-watch.sakuraweb.com/share/ARDUINO.zip).
Fork from  MonsieurV/PiPocketGeiger 

### Contribute

Feel free to [open a new ticket](https://github.com/JannePernu/PicoPocketGeiger/issues/new) or submit a PR to improve the lib.
