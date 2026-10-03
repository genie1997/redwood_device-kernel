# redwood-kernel

Prebuilt Vajra kernel for Xiaomi `redwood` (POCO X5 Pro 5G).
Drop-in for the device tree at `device/xiaomi/redwood-kernel`.

    5.4.302-Vajra-3.1

- `Image`: kernel, picked up by `LOCAL_KERNEL` in device.mk
- `dtb/`: Yupik SoC dtb, `BOARD_PREBUILT_DTBIMAGE_DIR`; mkbootimg takes it as `--dtb`
- `dtbo.img`: redwood overlay, `BOARD_PREBUILT_DTBOIMAGE`
- `kernel-headers/`: UAPI headers for building vendor modules, `TARGET_KERNEL_SOURCE`

The dtb rides in its own boot image section (`BOARD_INCLUDE_DTB_IN_BOOTIMG`); it is not appended to
`Image`.

    Image sha256 98f59b5f88233646e5ee2b2c4ad7c69632f489558469389d573a00babef0fc43

Source: https://github.com/genie1997/android_kernel_xiaomi_redwood (tag `5.4.302-Vajra-20261004`, commit `27bc20857e54`).
The dtb, dtbo and kernel headers are the ones this repo started from.
