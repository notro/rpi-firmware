notro/rpi-firmware
==========

Raspberry Pi kernel 3.12.21+ with support for FBTFT.

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware rpi-update
```



Changelog
---------
2014-06-14
* fb_ssd1351: Add rotation support
* Add Waveshare 2.2" (bd663474 & upd161704) support
* install_kernel_source is removed
* rpi-source support added

2014-03-28
* fix stmpe-ts  
  Interrupts was missed resulting in driver hang
* add rpi_power_switch module  
  Turn on/off the Raspberry Pi with a button

2014-03-08
* fix path in install_kernel_source

2014-03-08
* add extra/{git_hash,install_kernel_source} 

2014-03-06
* Add displays rpi-display and pitft
* Add modules 'stmpe' and 'gpio_backlight'
* DMA is enabled by default

2013-12-14
* add tinylcd35 support

2013-12-08
* Moved to Linux version 3.10
* fbtft_device: add hy28b support
* Add support for S6D1121

2013-11-18
* fb_ssd1306: add support for Adafruit OLED 1.3" monochrome display
* fb_ili9340: add support for the new Adafruit 2.2" display
* Enable console rotation support (fbcon=rotate:1)

2013-09-18
* fbtft: fix performance debug output
* flexfb: add 9-bit SPI emulation support
* fb_watterott: add support for mi0283qt-v2
* fbtft: experimental DMA support
* fbtft: turn off backlight before device removal

Thanks to Derek Campbell (guzunty) there is now experimental DMA support for SPI in FBTFT.  
The CPU runs much lighter using DMA:  https://github.com/notro/fbtft/wiki/FPS#testing-with-dma-support

2013-09-02
* fbtft_device: Add support for Freetronics OLED128 module and Tianma TM022HDH26
* fb_ssd1351: added chip gpio support (backlight)
* ads7846_device: moved to https://github.com/notro/fbtft_tools
* fbtft: add active low backlight pinname: 'led_'

2013-08-22
* All drivers have been rewritten (except flexfb). They now contain only LCD Controller specific logic and a default init sequence. fbtft_device contains the display specific information.  
  Show supported displays like this: sudo modprobe fbtft_device name=list; dmesg | tail -30
* 'rotate' argument is now a conter clockwise angle: 0, 90, 180, 270
* All drivers support all interface modes: SPI 8-bit + D/C, 8-bit + startbyte, 9-bit, GPIO 8, 16 bit (even though the LCD controller might not).
* The drivers will also load automatically when the device is present (need only load fbtft_device).
* The init sequence can be overridden on all drivers with the fbtft_device init argument.



Sources
-------
* [raspberrypi/tools](https://github.com/raspberrypi/tools/archive/108317fde2ffb56d1dc7f14ac69c42f34a49342a.tar.gz)
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/e45a4a25cd6ec19912de3310194ebaf8f02676f6.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/342abe67d0e1f12eae17562bfe7615143d2618d1.tar.gz)
* [notro/spi-bcm2708](https://github.com/notro/spi-bcm2708/archive/1ca01f95d00ab0aae1a07ab5cf18f1090d6981fe.tar.gz)
* [notro/fbtft](https://github.com/notro/fbtft/archive/b0503147c90869341905509c37d7ce866e7832a7.tar.gz)
* [msperl/spi-config](https://github.com/msperl/spi-config/archive/878f592626db291b3a62b5054278c95e92bc0b39.tar.gz)
* [notro/fbtft_tools](https://github.com/notro/fbtft_tools/archive/de14557bae567e80f7a5a41a79e8cc1b0c7d99fd.tar.gz)


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
FB_TFT_S6D1121=m
FB_TFT_SSD1289=m
FB_TFT_SSD1306=m
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
