notro/rpi-firmware
==========

Raspberry Pi kernel 3.15.7+ with Device Tree support on ARCH_BCM2708

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=dt rpi-update
```



 Upstreaming
--------------
Adding DT support to ARCH_BCM2708 is part of an effort to move to upstream drivers and get DT sooner.
* [Upstreaming](https://github.com/raspberrypi/linux/wiki/Upstreaming)
* [Device Tree on ARCH_BCM2708](https://github.com/raspberrypi/linux/wiki/Device-Tree-on-ARCH_BCM2708)

 Parts used to build this kernel
----------------------------------
* [rpi-build](https://github.com/notro/rpi-build)
* [stdlib/Rakefile](https://github.com/notro/rpi-build-stdlib/blob/master/Rakefile)  
* [stdlib/rpi-linux.rb](https://github.com/notro/rpi-build-stdlib/blob/master/rpi-linux.rb)  
* [stdlib/base.rb](https://github.com/notro/rpi-build-stdlib/blob/master/base.rb)  

[Rakefile](https://github.com/notro/rpi-firmware/blob/dt/extra/Rakefile) used to do this build.


Changelog
---------
2014-07-30
* DT support is in-tree now. Supports platform, i2c and spi devices
* i2c-bcm2835 and spi-bcm2835 are also built

2014-06-16
* Minimal DT support. Core only, except for SPI and I2C drivers

2013-11-06
* First release. DT support for all BCM2708 drivers except USB.



Sources
-------
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/59c7325f2d49603faad398677f339dfd7870ecfd.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/30d2c6249691737507c4b054f3224fddc0595ee0.tar.gz)


Patches
--------
None

Kernel config
-------------
Default config: bcmrpi_defconfig



Added:
```text
BCM2708_DT=y
DMA_OF=y
DTC=y
DYNAMIC_DEBUG=y
I2C_BCM2835=m
IRQCHIP=y
OF=y
OF_ADDRESS=y
OF_EARLY_FLATTREE=y
OF_FLATTREE=y
OF_GPIO=y
OF_IRQ=y
OF_MDIO=m
OF_NET=y
OF_RESERVED_MEM=y
PINCONF=y
PINCTRL=y
PINCTRL_BCM2708=y
PINMUX=y
SPI_BCM2835=m
THERMAL_OF=y
USE_OF=y
```


Deleted:
```text
BCM2708_SPIDEV=y
```


<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
