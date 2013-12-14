
notro/rpi-firmware
=======================================================

Raspberry Pi kernel and firmware with support for FBTFT.


Build scripts used: https://github.com/notro/rpi-build  
Build logs in the [extra/](https://github.com/notro/rpi-firmware/tree/master/extra) directory



### Install

Update [rpi-update](https://github.com/Hexxeh/rpi-update) to make sure we have REPO_URI support:
```text
sudo wget https://raw.github.com/Hexxeh/rpi-update/master/rpi-update -O /usr/bin/rpi-update && sudo chmod +x /usr/bin/rpi-update
```

**Install**
```text
sudo REPO_URI=https://github.com/notro/rpi-firmware rpi-update
sudo shutdown -r now
```


### Sources

* Linux Kernel  
https://github.com/raspberrypi/linux/tree/ff9f6d87957877265086ab8368bdabf27d35f491
* spi-bcm2708: DMA capable SPI master driver  
https://raw.github.com/notro/spi-bcm2708/master/spi-bcm2708.c
* FBTFT  
https://github.com/notro/fbtft.git/tree/5fc26ff3be79745151b2dd59e24f01a7c1d3bc56
* Various SPI device adding modules  
https://github.com/notro/fbtft_tools/tree/3c63895e612ceacd48c5a6956535a363e5685439
* ServoBlaster  
https://github.com/richardghirst/PiBits/tree/1b78f9ad6bb826dbce97b55862e06db8d4aea7f4
* spi-config: SPI device adding module  
https://github.com/msperl/spi-config/tree/88e5cd81dd54b4dca2c1bb29fd95701d7a5aea87


### Kernel patches
* [fbtft.patch](https://github.com/notro/rpi-build/blob/master/patches/master/fbtft.patch)


### Kernel configuration changes

Deleted:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=m
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
CONFIG_FB_FLEX=m
CONFIG_FB_SYS_COPYAREA=m
CONFIG_FB_SYS_FILLRECT=m
CONFIG_FB_SYS_FOPS=m
CONFIG_FB_SYS_IMAGEBLIT=m
CONFIG_FB_TFT=m
CONFIG_FB_TFT_FBTFT_DEVICE=m
CONFIG_FB_TFT_HX8340BN=m
CONFIG_FB_TFT_HX8347D=m
CONFIG_FB_TFT_ILI9320=m
CONFIG_FB_TFT_ILI9325=m
CONFIG_FB_TFT_ILI9340=m
CONFIG_FB_TFT_ILI9341=m
CONFIG_FB_TFT_PCD8544=m
CONFIG_FB_TFT_S6D1121=m
CONFIG_FB_TFT_SSD1289=m
CONFIG_FB_TFT_SSD1306=m
CONFIG_FB_TFT_SSD1331=m
CONFIG_FB_TFT_SSD1351=m
CONFIG_FB_TFT_ST7735R=m
CONFIG_FB_TFT_TINYLCD=m
CONFIG_FB_TFT_WATTEROTT=m
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
CONFIG_TOUCHSCREEN_ADS7846=m
```
