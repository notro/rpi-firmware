
notro/rpi-firmware
=======================================================

Raspberry Pi kernel and firmware with support for FBTFT.


Build scripts used: https://github.com/notro/rpi-build  
Build logs in the [extra/](https://github.com/notro/rpi-firmware/tree/master/extra) directory


### Install

If [rpi-update](https://github.com/Hexxeh/rpi-update) is older than 12. august 2013, then it has to be manually updated first (or REPO_URI will be overwritten):
```text
sudo wget https://raw.github.com/Hexxeh/rpi-update/master/rpi-update -O /usr/bin/rpi-update && sudo chmod +x /usr/bin/rpi-update
```

Because of an [issue](https://github.com/Hexxeh/rpi-update/issues/106), the following command is needed when going from the vanilla kernel to this kernel (not needed on subsequent notro/rpi-firmware updates):
```text
sudo mv /lib/modules/$(uname -r) /lib/modules/$(uname -r).bak
```

**Install**
```text
sudo REPO_URI=https://github.com/notro/rpi-firmware rpi-update
sudo shutdown -r now
```


### Sources

* Firmware  
https://github.com/raspberrypi/firmware/tree/fadc4cbd10d8144d301c894dd9975704db6206fa
* Linux kernel  
https://github.com/raspberrypi/linux/tree/cbd6672e7e1b2dc5026f5dc7929a13a9a68f2a62
* FBTFT  
https://github.com/notro/fbtft/tree/e207c4ec58429d24e8a03de5dce800c1a03dd36e
* [gpio_mouse_device](https://github.com/notro/fbtft_tools/wiki/gpio_mouse_device), [gpio_keys_device](https://github.com/notro/fbtft_tools/wiki/gpio_keys_device), [ads7846_device](https://github.com/notro/fbtft_tools/wiki/ads7846_device)  
https://github.com/notro/fbtft_tools/tree/3c63895e612ceacd48c5a6956535a363e5685439
* ServoBlaster  
https://github.com/richardghirst/PiBits/tree/3f4804aa906525ca3be42ecce30914eeec02af4d
* DMA capable SPI master driver [spi-bcm2708](https://github.com/notro/spi-bcm2708/wiki)  
https://github.com/notro/spi-bcm2708/tree/3209afa4e96c8a6e1f6e582b305d9468aa64d5f9


### Kernel patches

* [fbtft.patch](https://github.com/notro/rpi-build/blob/master/patches/fbtft.patch)
* [bcm2708.patch](https://github.com/notro/rpi-build/blob/master/patches/bcm2708.patch)


### Kernel configuration changes

Deleted:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=m
```

Added:  
```text
CONFIG_BACKLIGHT_CLASS_DEVICE=y
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
CONFIG_FB_TFT_ILI9341=m
CONFIG_FB_TFT_PCD8544=m
CONFIG_FB_TFT_SSD1289=m
CONFIG_FB_TFT_SSD1351=m
CONFIG_FB_TFT_ST7735R=m
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
CONFIG_INPUT_KEYBOARD=y
CONFIG_INPUT_MOUSE=y
CONFIG_INPUT_TOUCHSCREEN=y
CONFIG_KEYBOARD_GPIO=m
CONFIG_KEYBOARD_GPIO_POLLED=m
CONFIG_MOUSE_GPIO=m
CONFIG_TOUCHSCREEN_ADS7846=m
```
