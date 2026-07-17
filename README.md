# TFT Display (ESP32-C3)

This original project was gonna be way cooler, but missing some parts to make what I was originally gonna make, and my stepper motor was stolen from me in the middle of the night and my mouse :(

Drives a 2.8" TFT (TPM408-2.8, 240x320, ST7789)

At time of writing the display powers on (backlight visible) but shows a blank white screen instead of rendering content. This is a known, common failure mode for this class of SPI TFT panel and is still being debugged. Documenting it here so the wiring/setup is preserved even if not resolved before submission.


## Wiring

| Display pin | ESP32-C3 GPIO |
|---|---|
| VCC | 3.3V |
| GND | GND |
| CS | GPIO7 |
| RESET | GPIO6 |
| DC/RS | GPIO5 |
| SDI/MOSI | GPIO4 |
| SCK | GPIO3 |
| SDO/MISO | GPIO10 (disconnect to test) |
| LED (backlight) | 3.3V |

## Library / config
- `TFT_eSPI` (Bodmer)
- Config lives in `TFT_eSPI/User_Setup.h` inside the Arduino libraries folder, not in the sketch itself
- Sketch: draws simple filled shapes (blinking "eyes") via `fillRoundRect()` once `tft.init()` succeeds
