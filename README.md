# redwood-kernel

Prebuilt Vajra kernel for Xiaomi `redwood` (POCO X5 Pro 5G).
Drop-in for the device tree at `device/xiaomi/redwood-kernel`.

    5.4.302-Vajra-2.4

- `Image`: kernel, picked up by `LOCAL_KERNEL` in device.mk
- `dtb/`: Yupik SoC dtb, `BOARD_PREBUILT_DTBIMAGE_DIR`; mkbootimg takes it as `--dtb`
- `dtbo.img`: redwood overlay, `BOARD_PREBUILT_DTBOIMAGE`
- `kernel-headers/`: UAPI headers for building vendor modules, `TARGET_KERNEL_SOURCE`

The dtb rides in its own boot image section (`BOARD_INCLUDE_DTB_IN_BOOTIMG`); it is not appended to
`Image`.

    Image sha256 e1b82f1d0cbf66bb38e2619afaa613f9d5062a9313e87157fc02e5279b1c6c4f

Source: https://github.com/genie1997/android_kernel_xiaomi_redwood (commit `0bb38370d558`).
The dtb, dtbo and kernel headers are the ones this repo started from.
