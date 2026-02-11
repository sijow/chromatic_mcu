# Chromatic MCU: small fixes

This is a fork of <https://github.com/ModRetro/chromatic_mcu> with some quality of life improvements.

Currently implemented (version `fix1`):

- Battery level

   The AA battery level thresholds are adjusted so that the level indicator in the menu is more accurate.

   The charge level is computed using linear interpolation between the high, mid, low and depleted points (instead of linear interpolation between high and depleted).

   The thresholds are tuned for [Eneloop batteries](https://lygte-info.dk/review/batteries2012/Eneloop%20AA%20BK-3MCCE%201900mAh%20(White)%202019%20UK.html) but should also work well for other rechargeables.

   The mid-level voltage (corresponding to 50% charge) is particularly difficult to choose as NiMH batteries have a rather flat discharge curve around 50% so a small difference in measured voltage corresponds to a large difference in charge. And since the voltage depends on the load, the correct 50%-level would not be the same when playing with high vs low brightness or sound volume. In practice, this means the battery indicator will turn yellow closer to 60% when playing at high power consumption and closer to 40% when playing at low power consumption.
   
   For the corresponding change to the battery icon overlay in the corner you need to flash the corresponding [FPGA configuration](https://github.com/knuesel/chromatic_fpga).

## Usage

See instructions on the [original project page](https://github.com/ModRetro/chromatic_mcu) for how to build and flash.
