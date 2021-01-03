# firmware

To flash the firmware into the ESP32 board you will need to install the Arduino IDE and all the required libraries from the Libraries directory. 

Here you can find a tutorial on how to install the libraries: https://www.arduino.cc/en/Guide/Libraries

Installation instructions using Arduino IDE Boards Manager
==========================================================

Starting with 1.6.4, Arduino allows installation of third-party platform packages using Boards Manager. We have packages available for Windows, Mac OS, and Linux (32 and 64 bit).

- Install the current upstream Arduino IDE at the 1.8 level or later. The current version is at the [Arduino website](http://www.arduino.cc/en/main/software).
- Start Arduino and open Preferences window.
- Enter ```https://dl.espressif.com/dl/package_esp32_index.json``` into *Additional Board Manager URLs* field. You can add multiple URLs, separating them with commas.
- Open Boards Manager from Tools > Board menu and install *esp32* platform (and don't forget to select your ESP32 board from Tools > Board menu after installation).

------ Some info on the MyBar.io Board API -------
The ESP32 gets a command over Bluetooth with number of pump, direction and duration on milliseconds: "3-f-3000"
Directions are: f - forward, b - backwards and s -  stop
1 oz of beverage is served by specifying a duration value of 10000 ms

To prime the pumps, send 6000 forward to every pump

To clean the pumps, it is a 3-cycle process:
1 - return all liquid to the bottles 10000 backwards for each pump
2 and 3 run forward 10000 for each pump
There is a pause with a dialogue to explain that you need to remove the tubes and probably empty the glass
