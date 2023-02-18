# BMP280 library for RP2040

This is a library I created for my [personal project](https://github.com/skylordants/Pico_transmitter). I'm sharing it, in case it is helpful to somebody and to make my code public, but I don't intend on regularily maintaining it, because it works for me, unless something big happens.

## Usage
The simplest way to use the library is to include it in a platformio project using [wizio-pico baremetal](https://github.com/Wiz-IO/wizio-pico) platform, but other projects using the RP2040 SDK should work as well. It depends on my [I2C](https://github.com/skylordants/rp2040_i2c) library, but can be made to work without it quite easily, if necessary.

An BMP280 object can be created by calling it's constructor and giving it a pointer to the I2C object. After that, the only thing to do is to call *measure*, which returns *true*, if it's successful. After that, the measurements are saved in the variables *temperature* and *pressure*. Functions *calculate_current_temperature* and *calculate_current_pressure* can be used to get the last measurements in normal units and *calculate_temperature* and *calculate_pressure* can be used to get correct units for any measurements provided.

## Sources
Most of the stuff is based on the [datasheet](https://www.bosch-sensortec.com/media/boschsensortec/downloads/datasheets/bst-bmp280-ds001.pdf). The compensation logic is copied and modified from there. Some initial understanding in how the sensor work was from [BMP2 sensor API](https://github.com/BoschSensortec/BMP2-Sensor-API/), which has a BSD-3 license, but I didn't copy any code, so I shouldn't be committing any license infringement. If anyone thinks otherwise, I can just add another license or just remove the repository.
