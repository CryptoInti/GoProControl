# GoPro Control Arduino

This is a library to interface with GoPro cameras over WiFi, just press a button and turn on your GoPro action camera using an Arduino!

![Alt text](/extras/gopro3_and_nodemcu.jpg?raw=true "GoPro3")

![Alt text](/extras/gopros_and_esps.jpg?raw=true "GoPro4")

Have you ever thought about the possibility to control your action camera with your Arduino? Well if you are here because you googled that you may be interested in watching this video

[![Alt text](https://img.youtube.com/vi/PuM-ZQ2tMW0/0.jpg)](https://www.youtube.com/watch?v=PuM-ZQ2tMW0)

## Supported actions

- take a picture
- start and stop a video
- change the mode (photo, video, etc)
- delete last file or format the SD
- turn the camera on/off
- change the field of view (FOV)
- change frame rate
- change photo and video resolution
- turn the localization on/off
- change the orientation
- more?

## Supported boards:

- ESP8266
- ESP32
- ~~any arduino boards (UNO, nano, 101, etc.) attached to an ESP8266 (ESP01) using AT commands with [this library](https://github.com/bportaluri/WiFiEsp)~~ - removed for now
- offical Arduino boards with Wifi like the MKR series - todo

## Supported cameras:

- HERO3+
- HERO4
- HERO5 (tested with Black)
- HERO6 Black
- HERO7 Black
- Fusion

I made the library with a style which would be quite easy to add other cameras (not only gopro). I would be very happy to accept pull requests 😃

## Installation

- Using Arduino IDE:
	- Go to Tools > Manage libraries 
	- Search for GoProControl
- Using PlatformIO for Visual Studio Code:
	- ````pio lib install "GoProControl"````
- Manually:
	- ````cd $HOME/Arduino/libraries```` ([see Arduino library paths for other operating systems](https://www.arduino.cc/en/hacking/libraries))
	- ````git clone https://github.com/aster94/GoProControl.git````
	- Restart Arduino IDE

## Examples

**Important:** Don't forget to change the SSID and Password on the example code! To do so, edit the Constants.h file (Constants.h.example should be renamed to Constants.h) in the example folder. Also change camera type (HERO3, HERO4, HERO5, HERO6...)

## Supported Options

| Mode | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| VIDEO_MODE | ✔ | ✔ |
| PHOTO_MODE | ✔ | ✔ |
| BURST_MODE | ✔  | ✔ |
| TIMELAPSE_MODE | ✔ | ✔ |
| TIMER_MODE | ✔  | ✔ |
| PLAY_HDMI_MODE | ✔ | ✔ |
| MULTISHOT_MODE |  | ✔ |

| Orientation | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| ORIENTATION_UP | ✔ | ✔ |
| ORIENTATION_DOWN | ✔ | ✔ |
| ORIENTATION_AUTO |  | ✔ |

| Video Resolution | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| VR_4K |  | ✔ |
| VR_2K |  | ✔ |
| VR_2K_SuperView |  | ✔ |
| VR_1440p |  | ✔ |
| VR_1080p_SuperView |  | ✔ |
| VR_1080p | ✔ | ✔ |
| VR_960p | ✔ | ✔ |
| VR_720p_SuperView |  | ✔ |
| VR_720p | ✔ | ✔ |
| VR_WVGA | ✔ | ✔ |

| Field Of View | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| WIDE_FOV | ✔ | ✔ |
| MEDIUM_FOV | ✔ | ✔ |
| NARROW_FOV | ✔ | ✔ |
| LINEAR_FOV |  | ✔ |

| Frame Rate | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| FR_240 | ✔ | ✔ |
| FR_120 | ✔ | ✔ |
| FR_100 | ✔ | ✔ |
| FR_90 |  | ✔ |
| FR_80 |  | ✔ |
| FR_60 | ✔ | ✔ |
| FR_50 | ✔ | ✔ |
| FR_48 | ✔ | ✔ |
| FR_30 | ✔ | ✔ |
| FR_25 | ✔ | ✔ |
| FR_24 | ✔ |  |
| FR_15 | ✔ |  |
| FR_12p5 | ✔ |  |
| FR_12 | ✔ |  |

| Video Encoding | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| NTSC | ✔ | ✔ |
| PAL | ✔ | ✔ |

| Photo Resolution | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| PR_12MP_WIDE |  | ✔ |
| PR_12MP_MEDIUM |  | ✔ |
| PR_12MP_NARROW |  | ✔ |
| PR_12MP_LINEAR |  | ✔ |
| PR_11MP_WIDE | ✔ | ✔ |
| PR_8MP_WIDE | ✔ | ✔ |
| PR_8MP_MEDIUM |  | ✔ |
| PR_7MP_WIDE |  | ✔ |
| PR_7MP_MEDIUM |  | ✔ |
| PR_5MP_WIDE | ✔ | ✔ |
| PR_5MP_MEDIUM |  | ✔ |

| Time Lapse | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| 60 | ✔ | ✔ |
| 30 | ✔ | ✔ |
| 10 | ✔ | ✔ |
| 5 | ✔ | ✔ |
| 1 | ✔ | ✔ |
| 0.5 | ✔ | ✔ |

| Continuous Shot | HERO3 | HERO4,5,6,7 |
| --- | :---: | :---: |
| 10 | ✔ |  |
| 5 | ✔ |  |
| 3 | ✔ |  |
| 0 | ✔ |  |


## Reference

All the commands came from: https://github.com/KonradIT/goprowifihack

The idea cames from another gopro library: https://github.com/agdl/GoPRO which works only on arduino WiFi boards and only with gopro HERO3.
