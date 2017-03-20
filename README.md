notro/rpi-firmware
==========

Raspberry Pi kernels 4.9.16+ with [tinydrm](https://github.com/notro/tinydrm/wiki) support.

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=tinydrm49 rpi-update
```




Sources
-------
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/384559354762f36aa55584560d8749fc66a4cfd0.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/8bf13deebd582fd64a6595d23e9c965b652ef7c8.tar.gz)


Patches
--------
* 0001-drm-debugfs-Remove-all-files-automatically-on-cleanu.patch
* 0002-drm-Add-DRM-support-for-tiny-LCD-displays.patch
* 0003-drm-tinydrm-Add-helper-functions.patch
* 0004-drm-tinydrm-Add-MIPI-DBI-support.patch
* 0005-of-Add-vendor-prefix-for-Multi-Inno.patch
* 0006-dt-bindings-display-panel-Add-common-rotation-proper.patch
* 0007-dt-bindings-Add-Multi-Inno-MI0283QT-binding.patch
* 0008-drm-tinydrm-Add-support-for-Multi-Inno-MI0283QT-disp.patch
* 0009-drm-tinydrm-mipi-dbi-Silence-cmd-may-be-used-uniniti.patch
* 0010-drm-tinydrm-mipi-dbi-Fix-field-width-specifier-warni.patch
* Use https://raw.githubusercontent.com/notro/tinydrm/master/rpi-overlays/rpi-display-overlay.dts
* Use https://raw.githubusercontent.com/notro/tinydrm/master/rpi-overlays/pitft28-resistive-overlay.dts


Kernel config
-------------
Default config: bcmrpi_defconfig and bcm2709_defconfig



Added:
```text
DRM_TINYDRM=m
TINYDRM_MI0283QT=m
TINYDRM_MIPI_DBI=m
```


<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
