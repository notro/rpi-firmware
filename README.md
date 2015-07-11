notro/rpi-firmware
==========

Raspberry Pi kernel 4.0.7+ with SPI DMA support.

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware rpi-update
```



Changelog
---------
2015-07-11
* Update to 4.0.7 @ [13f82f4](https://github.com/raspberrypi/linux/commit/151dc845f920bb8f38abc0a6fc89093a913f82f4)

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
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/47d51d6192bdfb37568f21b5810375d1b6d45217.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/5d5a5ceb829329f490dd1c5cb634da66ef5d0f92.tar.gz)
* [notro/spi-bcm2708](https://github.com/notro/spi-bcm2708/archive/3322e8ef23c015941726f0402edfd9c64956b4f7.tar.gz)


Patches
--------
* /home/pi/rpi-firmware/fbtft/patches/bcm2708-spi-dts.patch
* /home/pi/rpi-firmware/fbtft/patches/0001-staging-fbtft-Add-reset-to-fbtft_init_display_dt.patch


Kernel config
-------------
Default config: bcmrpi_defconfig



<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
