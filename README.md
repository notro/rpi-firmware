
notro/rpi-firmware
=======================================================

Raspberry Pi kernel and firmware with builtin support for FBTFT (not loadable modules).


Build scripts used: https://github.com/notro/rpi-build  
Build logs in the [extra/](https://github.com/notro/rpi-firmware/tree/master/extra) directory



### Install

Update [rpi-update](https://github.com/Hexxeh/rpi-update) to make sure we have REPO_URI support:
```text
sudo wget https://raw.github.com/Hexxeh/rpi-update/master/rpi-update -O /usr/bin/rpi-update && sudo chmod +x /usr/bin/rpi-update
```

**Install**
```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=builtin rpi-update
sudo shutdown -r now
```


### Sources

* Linux Kernel  
https://github.com/raspberrypi/linux/tree/9cecb89ac95ffe8f9963250334e3df848fb3732b
* spi-bcm2708: DMA capable SPI master driver  
https://raw.github.com/notro/spi-bcm2708/master/spi-bcm2708.c
* FBTFT  
https://github.com/notro/fbtft.git/tree/f2f198292cf577438d5954117c9862b0fbedb601
* Various SPI device adding modules  
https://github.com/notro/fbtft_tools/tree/b5e2bd8e66fdd07333d82994559f737813cc7d3f
* ServoBlaster  
https://github.com/richardghirst/PiBits/tree/bf455ee13b9ec03f6678f2cbf6827b792cc570c0
* spi-config: SPI device adding module  
https://github.com/msperl/spi-config/tree/878f592626db291b3a62b5054278c95e92bc0b39


### Kernel patches
* [010-fbtft.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/010-fbtft.patch)
* [020-bcm2708.c.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/020-bcm2708.c.patch)
* [021-mach-bcm2708-Reserve-64-IRQs-for-peripherals.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/021-mach-bcm2708-Reserve-64-IRQs-for-peripherals.patch)
* [030-make-room-for-gpio-chips.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/030-make-room-for-gpio-chips.patch)
* [040-gpio_backlight.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/040-gpio_backlight.patch)
* [041-gpio_backlight-gpio-can-sleep.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/041-gpio_backlight-gpio-can-sleep.patch)
* [050-stmpe-ts-Various-fixes.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/050-stmpe-ts-Various-fixes.patch)


### Kernel configuration changes

Deleted:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=m
CONFIG_BCM2708_SPIDEV=y
CONFIG_MFD_CORE=m
CONFIG_SPI_BCM2708=m
```

Added:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=y
CONFIG_BACKLIGHT_GPIO=m
CONFIG_CAN=y
CONFIG_CAN_BCM=m
CONFIG_CAN_CALC_BITTIMING=y
CONFIG_CAN_DEV=y
CONFIG_CAN_GW=y
CONFIG_CAN_MCP251X=m
CONFIG_CAN_RAW=m
CONFIG_CAN_SLCAN=m
CONFIG_CAN_VCAN=m
CONFIG_FB_BACKLIGHT=y
CONFIG_FB_DEFERRED_IO=y
CONFIG_FB_FLEX=y
CONFIG_FB_SYS_COPYAREA=y
CONFIG_FB_SYS_FILLRECT=y
CONFIG_FB_SYS_FOPS=y
CONFIG_FB_SYS_IMAGEBLIT=y
CONFIG_FB_TFT=y
CONFIG_FB_TFT_FBTFT_DEVICE=y
CONFIG_FB_TFT_HX8340BN=y
CONFIG_FB_TFT_HX8347D=y
CONFIG_FB_TFT_ILI9320=y
CONFIG_FB_TFT_ILI9325=y
CONFIG_FB_TFT_ILI9340=y
CONFIG_FB_TFT_ILI9341=y
CONFIG_FB_TFT_PCD8544=y
CONFIG_FB_TFT_S6D1121=y
CONFIG_FB_TFT_SSD1289=y
CONFIG_FB_TFT_SSD1306=y
CONFIG_FB_TFT_SSD1331=y
CONFIG_FB_TFT_SSD1351=y
CONFIG_FB_TFT_ST7735R=y
CONFIG_FB_TFT_TINYLCD=y
CONFIG_FB_TFT_WATTEROTT=y
CONFIG_FONTS=y
CONFIG_FONT_10x18=y
CONFIG_FONT_6x11=y
CONFIG_FONT_7x14=y
CONFIG_FONT_ACORN_8x8=y
CONFIG_FONT_MINI_4x6=y
CONFIG_FONT_PEARL_8x8=y
CONFIG_FONT_SUN12x22=y
CONFIG_FONT_SUN8x16=y
CONFIG_FRAMEBUFFER_CONSOLE_ROTATION=y
CONFIG_GPIO_STMPE=y
CONFIG_INPUT_KEYBOARD=y
CONFIG_INPUT_MOUSE=y
CONFIG_INPUT_TOUCHSCREEN=y
CONFIG_KEYBOARD_GPIO=m
CONFIG_KEYBOARD_GPIO_POLLED=m
CONFIG_MFD_CORE=y
CONFIG_MFD_STMPE=y
CONFIG_MOUSE_GPIO=m
CONFIG_SPI_BCM2708=y
CONFIG_STMPE_I2C=y
CONFIG_STMPE_SPI=y
CONFIG_TOUCHSCREEN_ADS7846=m
CONFIG_TOUCHSCREEN_STMPE=m
```
