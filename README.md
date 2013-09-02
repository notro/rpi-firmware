
notro/rpi-firmware
=======================================================

Raspberry Pi kernel and firmware with support for FBTFT.


Build scripts used: https://github.com/notro/rpi-build  
Build logs in the [extra/](https://github.com/notro/rpi-firmware/tree/master/extra) directory

### Sources

* Firmware  
https://github.com/raspberrypi/firmware/tree/d4f5315cfac4e14091d5440a6d482e033ba21b1b
* Linux kernel  
https://github.com/raspberrypi/linux/tree/1587f775d0a3c437485262ba951afc5e30be69fa
* FBTFT  
https://github.com/notro/fbtft/tree/25e1b0eb0822da905e89016e81740d98174d826d
* gpio_mouse_device, gpio_keys_device  
https://github.com/notro/fbtft_tools/tree/3c63895e612ceacd48c5a6956535a363e5685439
* ServoBlaster  
https://github.com/richardghirst/PiBits/tree/071fc182bcf4e2e69591a781805b63f8e251f3f6


### Kernel source changes

* spi-bcm2708.c: bcm2708_setup_state(): removed ```roundup_pow_of_two()``` limitation


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
