# redwood-kernel

Prebuilt Vajra kernel for Xiaomi `redwood` (POCO X5 Pro 5G).
Drop-in for the device tree at `device/xiaomi/redwood-kernel`.

    5.4.302-Vajra-4.1

- `Image`: kernel, picked up by `LOCAL_KERNEL` in device.mk
- `dtb/`: Yupik SoC dtb, `BOARD_PREBUILT_DTBIMAGE_DIR`; mkbootimg takes it as `--dtb`
- `dtbo.img`: redwood overlay, `BOARD_PREBUILT_DTBOIMAGE`
- `kernel-headers/`: UAPI headers for building vendor modules, `TARGET_KERNEL_SOURCE`

The dtb rides in its own boot image section (`BOARD_INCLUDE_DTB_IN_BOOTIMG`); it is not appended to
`Image`.

    Image sha256 2516594abecfdce6b89f252c0faa82c27473dc5b97da8db656a7338c48c72644

Source: https://github.com/genie1997/android_kernel_xiaomi_redwood (tag `5.4.302-Vajra-20261016`, commit `d6db242332ac`).
The dtb and dtbo are the ones this repo started from. The headers are generated from the kernel
tree with `make headers_install`.
