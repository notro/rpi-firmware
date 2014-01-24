
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
https://github.com/raspberrypi/linux/tree/943b563ec9961b53b77a0e7b6c07289826c082a5
* spi-bcm2708: DMA capable SPI master driver  
https://raw.github.com/notro/spi-bcm2708/master/spi-bcm2708.c
* FBTFT  
https://github.com/notro/fbtft.git/tree/238c3ad645a5a8214ec3190e621958d7d837ca21
* Various SPI device adding modules  
https://github.com/notro/fbtft_tools/tree/3c63895e612ceacd48c5a6956535a363e5685439
* ServoBlaster  
https://github.com/richardghirst/PiBits/tree/e62579ecb7ab46f8c081c7283b964a736363290b
* spi-config: SPI device adding module  
https://github.com/msperl/spi-config/tree/88e5cd81dd54b4dca2c1bb29fd95701d7a5aea87


### Kernel patches
* [bcm2708.c.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/bcm2708.c.patch)
* [fbtft.patch](https://github.com/notro/rpi-build/blob/master/patches/builtin/fbtft.patch)


### Kernel configuration changes

Deleted:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=m
CONFIG_BCM2708_SPIDEV=y
CONFIG_SPI_BCM2708=m
```

Added:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=y
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
CONFIG_INPUT_KEYBOARD=y
CONFIG_INPUT_MOUSE=y
CONFIG_INPUT_TOUCHSCREEN=y
CONFIG_KEYBOARD_GPIO=m
CONFIG_KEYBOARD_GPIO_POLLED=m
CONFIG_MOUSE_GPIO=m
CONFIG_SPI_BCM2708=y
CONFIG_TOUCHSCREEN_ADS7846=m
```
