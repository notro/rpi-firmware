notro/rpi-firmware
==========

Raspberry Pi kernels 4.10.4+ with [tinydrm](https://github.com/notro/tinydrm/wiki) support including kernel headers.

Install
-------

```text
sudo REPO_URI=https://github.com/notro/rpi-firmware BRANCH=tinydrm rpi-update
```




Sources
-------
* [raspberrypi/firmware](https://github.com/raspberrypi/firmware/archive/2ef9cb622f0587e9a0fc4826a9a2d7d34c092d95.tar.gz)
* [raspberrypi/linux](https://github.com/raspberrypi/linux/archive/45a84008361cf6cfa37a67e4cf06354a8598fb5e.tar.gz)


Patches
--------
* 0001-drm-Store-a-pointer-to-drm_format_info-under-drm_fra.patch
* 0002-drm-cma-helper-simplify-setup-for-drivers-with-dirty.patch
* 0003-drm-fb-cma-helper-Add-drm_fbdev_cma_set_suspend_unlo.patch
* 0004-drm-debugfs-Remove-all-files-automatically-on-cleanu.patch
* 0005-drm-simple-helpers-Add-missing-includes.patch
* 0006-drm-Rely-on-mode_config-data-for-fb_helper-initializ.patch
* 0007-drm-Add-DRM-support-for-tiny-LCD-displays.patch
* 0008-drm-tinydrm-Add-helper-functions.patch
* 0009-drm-tinydrm-Add-MIPI-DBI-support.patch
* 0010-drm-tinydrm-Add-support-for-Multi-Inno-MI0283QT-disp.patch
* 0011-drm-tinydrm-mipi-dbi-Silence-cmd-may-be-used-uniniti.patch
* 0012-drm-tinydrm-mipi-dbi-Fix-field-width-specifier-warni.patch
* 0013-drm-tinydrm-helpers-Properly-fix-backlight-dependenc.patch
* 0014-drm-tinydrm-fix-semicolon.cocci-warnings.patch
* Build tinydrm-helpers.c with DEBUG to get SPI transfer details
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


Changed:
```text
IKCONFIG m -> y
```


<p align="center">Built with <a href="https://github.com/notro/rpi-build/wiki">rpi-build</a></p>
