
notro/rpi-firmware
=======================================================


Raspberry Pi kernel with Device Tree support.  
See [wiki](https://github.com/notro/rpi-firmware/wiki/Device-Tree) for more info.



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
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=dt rpi-update
sudo shutdown -r now
```


### Sources

* Linux Kernel  
https://github.com/raspberrypi/linux/tree/a987a783807aeed2232280248a49ed8fa5981858


### Kernel patches
* [dt_enable_bcm2708_part2.patch](https://github.com/notro/rpi-build/blob/master/patches/dt/dt_enable_bcm2708_part2.patch)
* [dt_enable_bcm2708.patch](https://github.com/notro/rpi-build/blob/master/patches/dt/dt_enable_bcm2708.patch)
* [enable_i2c-bcm2835_and_spi-bcm2835.patch](https://github.com/notro/rpi-build/blob/master/patches/dt/enable_i2c-bcm2835_and_spi-bcm2835.patch)
* [add_a_few_pr_debug_to_core.patch](https://github.com/notro/rpi-build/blob/master/patches/dt/add_a_few_pr_debug_to_core.patch)
* [enable_driver_debug_output.patch](https://github.com/notro/rpi-build/blob/master/patches/dt/enable_driver_debug_output.patch)
* [dt_enable_drivers.patch](https://github.com/notro/rpi-build/blob/master/patches/dt/dt_enable_drivers.patch)


### Kernel configuration changes

Deleted:  
```text
CONFIG_BCM2708_SPIDEV=y
CONFIG_I2C_BCM2708=m
CONFIG_I2C_CHARDEV=m
CONFIG_INPUT_POLLDEV=m
CONFIG_LEDS_CLASS=m
CONFIG_LEDS_GPIO=m
CONFIG_SPI_BCM2708=m
CONFIG_W1=m
CONFIG_W1_MASTER_GPIO=m
```

Added:  
```text
CONFIG_BCM2708_DT=y
CONFIG_COMMON_CLK=y
CONFIG_COMMON_CLK_DEBUG=y
CONFIG_DTC=y
CONFIG_DYNAMIC_DEBUG=y
CONFIG_HAVE_CLK_PREPARE=y
CONFIG_I2C_BCM2708=y
CONFIG_I2C_CHARDEV=y
CONFIG_INPUT_KEYBOARD=y
CONFIG_INPUT_MOUSE=y
CONFIG_INPUT_POLLDEV=y
CONFIG_INPUT_TOUCHSCREEN=y
CONFIG_IRQCHIP=y
CONFIG_IRQ_DOMAIN=y
CONFIG_KEYBOARD_GPIO=y
CONFIG_KEYBOARD_GPIO_POLLED=y
CONFIG_LEDS_CLASS=y
CONFIG_LEDS_GPIO=y
CONFIG_MOUSE_GPIO=y
CONFIG_NEED_MACH_GPIO_H=y
CONFIG_OF=y
CONFIG_OF_ADDRESS=y
CONFIG_OF_DEVICE=y
CONFIG_OF_EARLY_FLATTREE=y
CONFIG_OF_FLATTREE=y
CONFIG_OF_GPIO=y
CONFIG_OF_I2C=y
CONFIG_OF_IRQ=y
CONFIG_OF_MDIO=y
CONFIG_OF_NET=y
CONFIG_PINCONF=y
CONFIG_PINCTRL=y
CONFIG_PINCTRL_BCM2708=y
CONFIG_PINMUX=y
CONFIG_PROC_DEVICETREE=y
CONFIG_SPI_BCM2708=y
CONFIG_TOUCHSCREEN_ADS7846=y
CONFIG_USE_OF=y
CONFIG_W1=y
CONFIG_W1_MASTER_GPIO=y
```
