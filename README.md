
notro/rpi-firmware
=======================================================

Raspberry Pi kernel and firmware with support for FBTFT.


Build scripts used: https://github.com/notro/rpi-build  
Build logs in the [extra/](https://github.com/notro/rpi-firmware/tree/master/extra) directory

### Sources

* Firmware  
https://github.com/raspberrypi/firmware/tree/3ab17ac25e92ade48325472994b6660c5efd05b5
* Linux kernel  
https://github.com/raspberrypi/linux/tree/63b69a8806ce1890711ff55280c90673ea415933
* FBTFT  
https://github.com/notro/fbtft/tree/76b5b981191344afd9380a04e3c0ee6b5e985856
* gpio_mouse_device, gpio_keys_device  
https://github.com/notro/fbtft_tools/tree/2a4294361711f869ca537a2404ba932e4ad17cf9
* ServoBlaster  
https://github.com/richardghirst/PiBits/tree/fdf979c383c3d02dc9d5ce9846ef6a02baf0fa27


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
CONFIG_TOUCHSCREEN_ADS7846_DEVICE=m
```
