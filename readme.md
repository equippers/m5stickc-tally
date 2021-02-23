# M5StickC Tally for Blackmagic Switchers

Turn an [M5StickC](https://m5stack.com/products/stick-c) into a Tally for Blackmagic Switchers. You can change the input and label with the buttons.

## Setup

1. Install the [Arduino IDE](https://www.arduino.cc/en/software) (`brew install arduino`).
2. If you're using VS Code, install the [Arduino](https://marketplace.visualstudio.com/items?itemName=vsciot-vscode.vscode-arduino) extension.
3. If you're using the Arduino IDE, open the preferences and set the sketchbook location to this folder, then add `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json` to the list of additional board manager URLs.
4. Using the Arduino Library Manager, install the "M5StickC" library.
5. If you're using the Arduino IDE, choose the "M5Stick-C" board (max supported upload speed is `1500000`).
6. Clone or download [kasperskaarhoj/SKAARHOJ-Open-Engineering](https://github.com/kasperskaarhoj/SKAARHOJ-Open-Engineering).
7. Apply the `ATEMbase` patch by running the following in the cloned/downloaded folder:
```sh
git apply path/to/ATEMbase.patch
```
8. Either symlink or copy the folders `ATEMbase`, `ATEMstd` and `SkaarhojPgmspace` from `ArduinoLibs` into this project's `libraries` folder.


## Build

1. Open `m5stickc-tally/config.h` and adjust the `SWITCHER_IP` and Wifi `SSID` and `PASS`.
2. Connect the M5StickC via USB.
3. Select the serial port.
4. Upload (Action "Arduino: Upload" in VS Code).

## Use

* Press power button (left) to turn on and hold for 6 secs to turn off.
* Button A (the big one) changes the input.
* Button B (right) changes the label.

Disclaimer: The input and label are stored in NVS (non-volatile storage) so that they are persisted when the M5StickC is turned off and on. NVS has a limited number of write cycles before degrading.

## Links

- [One Guy One Blog - Tally Light EPS32 For Blackmagic ATEM Switcher](https://oneguyoneblog.com/2020/06/13/tally-light-esp32-for-blackmagic-atem-switcher/)
- [M5Stack Core API](https://docs.m5stack.com/#/en/arduino/arduino_home_page?id=m5core_api)
- [M5StickC LCD API](https://docs.m5stack.com/#/en/api/lcd_m5stickc)
- [m5stack/M5StickC](https://github.com/m5stack/M5StickC)
- [kasperskaarhoj/SKAARHOJ-Open-Engineering](https://github.com/kasperskaarhoj/SKAARHOJ-Open-Engineering)

## License

[MIT](/license).
