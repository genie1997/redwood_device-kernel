# redwood-kernel

Prebuilt Vajra kernel for Xiaomi `redwood` (POCO X5 Pro 5G).
Drop-in for the device tree at `device/xiaomi/redwood-kernel`.

    5.4.302-Vajra-2.1

- `Image`: kernel, picked up by `LOCAL_KERNEL` in device.mk
- `dtb/`: Yupik SoC dtb, `BOARD_PREBUILT_DTBIMAGE_DIR`; mkbootimg takes it as `--dtb`
- `dtbo.img`: redwood overlay, `BOARD_PREBUILT_DTBOIMAGE`
- `kernel-headers/`: UAPI headers for building vendor modules, `TARGET_KERNEL_SOURCE`

The dtb rides in its own boot image section (`BOARD_INCLUDE_DTB_IN_BOOTIMG`); it is not appended to
`Image`.

    Image sha256 9a6cc4993457841961decb29a1003068cdd73e56461a2d9a72143b39bdfee032

Source: https://github.com/genie1997/android_kernel_xiaomi_redwood (tag `5.4.302-Vajra-20260927`).
The dtb, dtbo and kernel headers are the ones this repo started from.
