notro/rpi-firmware
==========

Raspberry Pi kernel 3.12.22+ with support for FBTFT.

Test release: RA8875 and SSD1322 support

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=test rpi-update
```




Sources
-------
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/462f3e3f476f7b6200004040c09e992f3c551f38.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/1981ddebd4d3108cc942680a75ea151a479d65a8.tar.gz)
* [notro/spi-bcm2708](https://github.com/notro/spi-bcm2708/archive/1ca01f95d00ab0aae1a07ab5cf18f1090d6981fe.tar.gz)
* [notro/fbtft](https://github.com/notro/fbtft/archive/b0503147c90869341905509c37d7ce866e7832a7.tar.gz)
* [notro/fbtft_tools](https://github.com/notro/fbtft_tools/archive/de14557bae567e80f7a5a41a79e8cc1b0c7d99fd.tar.gz)
* [msperl/spi-config](https://github.com/msperl/spi-config/archive/878f592626db291b3a62b5054278c95e92bc0b39.tar.gz)
* https://raw.githubusercontent.com/presslab-us/fbtft/master/fb_ssd1322.c


Patches
--------
* /home/pi/rpi-build/fbtft-build/patches/fbtft.patch/3.12
* /home/pi/rpi-build/fbtft-build/patches/gpio_backlight-gpio-can-sleep.patch/3.10
* /home/pi/rpi-build/fbtft-build/patches/stmpe-ts-Various-fixes.patch/3.10


Kernel config
-------------
Default config: bcmrpi_defconfig



Added:
```text
BACKLIGHT_GPIO=m
CAN=y
CAN_BCM=m
CAN_CALC_BITTIMING=y
CAN_DEV=y
CAN_GW=y
CAN_MCP251X=m
CAN_RAW=m
CAN_SLCAN=m
CAN_VCAN=m
DYNAMIC_DEBUG=y
FB_BACKLIGHT=y
FB_DEFERRED_IO=y
FB_FLEX=m
FB_SYS_COPYAREA=m
FB_SYS_FILLRECT=m
FB_SYS_FOPS=m
FB_SYS_IMAGEBLIT=m
FB_TFT=m
FB_TFT_BD663474=m
FB_TFT_FBTFT_DEVICE=m
FB_TFT_HX8340BN=m
FB_TFT_HX8347D=m
FB_TFT_HX8353D=m
FB_TFT_ILI9320=m
FB_TFT_ILI9325=m
FB_TFT_ILI9340=m
FB_TFT_ILI9341=m
FB_TFT_PCD8544=m
FB_TFT_RA8875=m
FB_TFT_S6D1121=m
FB_TFT_SSD1289=m
FB_TFT_SSD1306=m
FB_TFT_SSD1322=m
FB_TFT_SSD1331=m
FB_TFT_SSD1351=m
FB_TFT_ST7735R=m
FB_TFT_TINYLCD=m
FB_TFT_UPD161704=m
FB_TFT_WATTEROTT=m
FONTS=y
FONT_10x18=y
FONT_6x11=y
FONT_7x14=y
FONT_ACORN_8x8=y
FONT_MINI_4x6=y
FONT_PEARL_8x8=y
FONT_SUN12x22=y
FONT_SUN8x16=y
FRAMEBUFFER_CONSOLE_ROTATION=y
GPIO_MCP23S08=m
GPIO_STMPE=y
INPUT_KEYBOARD=y
INPUT_MOUSE=y
INPUT_TOUCHSCREEN=y
KEYBOARD_GPIO=m
MFD_STMPE=y
MOUSE_GPIO=m
SPI_BITBANG=m
SPI_GPIO=m
STMPE_I2C=y
STMPE_SPI=y
TOUCHSCREEN_ADS7846=m
TOUCHSCREEN_STMPE=m
```


Changed:
```text
BACKLIGHT_CLASS_DEVICE m -> y
MFD_CORE m -> y
```


<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
