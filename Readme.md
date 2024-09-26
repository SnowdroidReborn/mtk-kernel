# mtk-kernels
Linux kernel source code for MediaTek-based devices

## Branches
| Branch name                   | Kernel version                        | Device model                       | Device codename     | Description
|-------------------------------|------------------------|------------------------------------|---------------------|----------------------------------------------------------------------------------------------------|
| **xiaomi_nikel_3.18**         | 3.18.22                | Xiaomi Redmi Note 4/4X (MTK)       | `nikel`             | Modified from [Ruben1863's custom kernel](https://github.com/Ruben1863/android_kernel_xiaomi_nikel)

## Description
This kernel is a custom one and can be built in the AOSP version originally developed for the Vernee Apollo Lite device, with subsequent replacement with the **_non-GPL-respected_** MIUI kernel.

## Known issues
1. **When trying to load the kernel, a bootloop occurs (tested without replacing the kernel in boot.img)**.
2. **The kernel does not work fully due to a number of reasons:**
   * Despite official statements, Xiaomi does [not publish kernel source codes](https://www.xda-developers.com/xiaomi-aims-to-release-kernel-source-code-for-new-devices-within-3-months-after-launch/) for some devices that run on MediaTek processors.
   * Due to the above issue, after replacing the kernel, the front camera does not work due to the lack of source codes for the `s5k5e8yx_b6_mipi_raw` HAL driver for `libcameracustom` module (aka `s5k5e8yxb6mipiraw`).
3. **Some symbolic links are broken in the [`arch/[arch_id]/boot/dts/include`](https://github.com/SnowdroidReborn/mtk-kernels/tree/xiaomi_nikel_custom_3.18/arch/arm64/boot/dts/include/dt-bindings) directory** and have been replaced with pseudo-symbolic ones.\
   We strongly recommend reviewing the contents of the `symlink` file before building to avoid build errors.

## Acknowledgements
* [@Ruben1863](https://github.com/Ruben1863)
* [@jmpfbmx](https://github.com/jmpfbmx)
* [@R0rt1z2](https://github.com/R0rt1z2)
* [@tretdm](https://github.com/tretdm)
