notro/rpi-firmware
==========

Raspberry Pi kernel 3.18.10+ with SPI DMA support.

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware rpi-update
```



Changelog
---------
2015-03-27
* FBTFT support is now in raspberrypi/linux.
  This release only adds SPI DMA support on top of that.
* pitft overlay changed name to pitft28-resistive
* These modules are no longer present:
  - gpio_keys_device - [DT overlay example](https://github.com/raspberrypi/linux/blob/rpi-3.18.y/arch/arm/boot/dts/tinylcd35-overlay.dts)
  - ads7846_device - Use ads7846 DT overlay instead. See [/boot/overlays/README](https://github.com/raspberrypi/firmware/blob/master/boot/overlays/README)
  - gpio_mouse_device
  - stmpe_device
  - gpio_backlight_device
  - rpi_power_switch
  - spi-config
* Builtin console fonts are not enabled (fbcon=font:XX).
  - [sudo dpkg-reconfigure console-setup](https://github.com/notro/fbtft/wiki/Boot-console#console-font)
* Other kconfig options no longer enabled:
  - MOUSE_GPIO
  - GPIO_MCP23S08
  - DYNAMIC_DEBUG

2015-02-07
* Pi 2 support

2014-12-07
* [fbtft_device: added support for waveshare32b](https://github.com/notro/fbtft/commit/e67014490a9df34b9a4bf04e49c50254aebc10a8)
* [fbtft_device: add Tontec 3.5 support](https://github.com/notro/fbtft/commit/8116d7273be8816ce70c1a017b4466ae17e27d53)
* [fb_ili9481,6: regwidth was incorrect](https://github.com/notro/fbtft/commit/c92097b5a5ef82e298a4fe8ec7859c9378e435d8)
* [fbtft: make it possible to override regwidth](https://github.com/notro/fbtft/commit/566dca0e9d531b54c11ea9aea47f76695472776c)



Sources
-------
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/7baf63aeb395947fa1f0a9f18b7ce120f2c4af07.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/7afb1c5b7cf33a3182c97ac9be7379394b9b462a.tar.gz)
* [notro/spi-bcm2708](https://github.com/notro/spi-bcm2708/archive/57fc2d1ea38e337ea04bd4e05a24cc94eea11a8b.tar.gz)


Patches
--------
None

Kernel config
-------------
Default config: bcmrpi_defconfig



<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
