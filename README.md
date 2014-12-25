notro/rpi-firmware
==========

Raspberry Pi Device Tree kernel 3.18.1+ with support for FBTFT.

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=next rpi-update
```




Sources
-------
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/2f9828c4577a858571b76eef3f7e1d3ff7ac1ba9.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/5fdce56c57f419a8f8a57a6c5b90d63deabca713.tar.gz)
* [notro/spi-bcm2708](https://github.com/notro/spi-bcm2708/archive/1ca01f95d00ab0aae1a07ab5cf18f1090d6981fe.tar.gz)
* [notro/fbtft](https://github.com/notro/fbtft/archive/277db6290388de64bfa251c9acbe3ffda381e5b5.tar.gz)
* [notro/fbtft_tools](https://github.com/notro/fbtft_tools/archive/8553a4b1f5262c6dd076bb5fdd3e97ec7e3cdebe.tar.gz)
* [msperl/spi-config](https://github.com/msperl/spi-config/archive/878f592626db291b3a62b5054278c95e92bc0b39.tar.gz)


Patches
--------
* /home/pi/rpi-firmware/fbtft/patches/dts_irq.patch
* /home/pi/rpi-build/fbtft-build/patches/fbtft.patch/3.15
* /home/pi/rpi-build/fbtft-build/patches/stmpe-ts-Various-fixes.patch/3.10


Kernel config
-------------
Default config: bcmrpi_defconfig



Added:
```text
BACKLIGHT_GPIO=y
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
FB_SYS_COPYAREA=y
FB_SYS_FILLRECT=y
FB_SYS_FOPS=y
FB_SYS_IMAGEBLIT=y
FB_TFT=y
FB_TFT_AGM1264K_FL=y
FB_TFT_BD663474=y
FB_TFT_FBTFT_DEVICE=m
FB_TFT_HX8340BN=y
FB_TFT_HX8347D=y
FB_TFT_HX8353D=y
FB_TFT_ILI9320=y
FB_TFT_ILI9325=y
FB_TFT_ILI9340=y
FB_TFT_ILI9341=y
FB_TFT_ILI9481=y
FB_TFT_ILI9486=y
FB_TFT_PCD8544=y
FB_TFT_RA8875=y
FB_TFT_S6D02A1=y
FB_TFT_S6D1121=y
FB_TFT_SSD1289=y
FB_TFT_SSD1306=y
FB_TFT_SSD1331=y
FB_TFT_SSD1351=y
FB_TFT_ST7735R=y
FB_TFT_TINYLCD=y
FB_TFT_TLS8204=y
FB_TFT_UC1701=y
FB_TFT_UPD161704=y
FB_TFT_WATTEROTT=y
FONTS=y
FONT_10x18=y
FONT_6x10=y
FONT_6x11=y
FONT_7x14=y
FONT_ACORN_8x8=y
FONT_MINI_4x6=y
FONT_PEARL_8x8=y
FONT_SUN12x22=y
FONT_SUN8x16=y
FRAMEBUFFER_CONSOLE_ROTATION=y
GPIOLIB_IRQCHIP=y
GPIO_MCP23S08=m
GPIO_STMPE=y
I2C_BCM2835=m
INPUT_KEYBOARD=y
INPUT_MOUSE=y
KEYBOARD_GPIO=m
MFD_STMPE=y
MOUSE_GPIO=m
SPI_BCM2835=y
SPI_BITBANG=m
SPI_GPIO=m
STMPE_I2C=y
STMPE_SPI=y
TOUCHSCREEN_STMPE=m
```


Changed:
```text
BACKLIGHT_CLASS_DEVICE m -> y
SPI_BCM2708 m -> y
```


<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
