notro/rpi-firmware
==========

Raspberry Pi kernel 3.12.22+ with experimental Device Tree support using ARCH_BCM2708

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=dt rpi-update
```



Parts used to build this kernel
----------------------------------
* [rpi-build](https://github.com/notro/rpi-build)
* [stdlib/Rakefile](https://github.com/notro/rpi-build-stdlib/blob/master/Rakefile)  
* [stdlib/rpi-linux-dt.rb](https://github.com/notro/rpi-build-stdlib/blob/master/rpi-linux-dt.rb)  
* [stdlib/uboot.rb](https://github.com/notro/rpi-build-stdlib/blob/master/uboot.rb)  
* [stdlib/base.rb](https://github.com/notro/rpi-build-stdlib/blob/master/base.rb)  

See the [extra directory](https://github.com/notro/rpi-firmware/tree/master/extra) which contain accumulated patch files, and the [Rakefile](https://github.com/notro/rpi-firmware/blob/master/extra/Rakefile) used do this build.


Changelog
---------
2014-06-16
* Minimal DT support. Core only, except for SPI and I2C drivers

2013-11-06
* First release. DT support for all BCM2708 drivers except USB.



Sources
-------
* [raspberrypi/tools](https://github.com/raspberrypi/tools/archive/108317fde2ffb56d1dc7f14ac69c42f34a49342a.tar.gz)
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/5bb031721026b6d84561f3cc96b9b6a7e6921431.tar.gz)
* [http://git.denx.de/?p=u-boot/u-boot-arm.git](http://git.denx.de/?p=u-boot/u-boot-arm.git;a=snapshot;h=0a26e1d6c394aacbf1153977b7348d1dff85db3f;sf=tbz2)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/99df631ec39cbd4afaf2d3b8d8483d7f2489add2.tar.gz)


Patches
--------
* U-Boot: Copy ATAG_CMDLINE to bootargs environment variable
* Add drivers/pinctrl/pinctrl-bcm2708.c
* Add Device Tree support BCM2708_DT
* /home/pi/rpi-build/stdlib/patches/armctrl.patch
* /home/pi/rpi-build/stdlib/patches/dt-enable-drivers.patch
* Disable spi0, i2c0 and i2c1 devices in /home/pi/rpi-firmware/dt/workdir/linux/arch/arm/mach-bcm2708/bcm2708.c
* i2c: bcm2708: Linking platform nodes to adapter nodes
* Make it possible to choose I2C_BCM2835 and SPI_BCM2835 with MACH_BCM2708
* /home/pi/rpi-build/stdlib/patches/i2c--bcm2835--Linking-platform-nodes-to-adapter-nodes.patch/3.12


Kernel config
-------------
Default config: bcmrpi_defconfig



Added:
```text
BCM2708_DT=y
COMMON_CLK=y
COMMON_CLK_DEBUG=y
DMA_OF=y
DTC=y
DYNAMIC_DEBUG=y
HAVE_CLK_PREPARE=y
IRQCHIP=y
OF=y
OF_ADDRESS=y
OF_EARLY_FLATTREE=y
OF_FLATTREE=y
OF_GPIO=y
OF_IRQ=y
OF_MDIO=m
OF_NET=y
PINCONF=y
PINCTRL=y
PINCTRL_BCM2708=y
PINMUX=y
PROC_DEVICETREE=y
USE_OF=y
```


Deleted:
```text
BCM2708_SPIDEV=y
```


<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
