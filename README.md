# redwood-kernel

Prebuilt GKI kernel for Xiaomi `redwood` (POCO X5 Pro 5G).
Drop-in for the device tree at `device/xiaomi/redwood-kernel`.

    6.12.92-redwood-g1815b9922f25

- `Image`: GKI kernel (android16-6.12), picked up by `LOCAL_KERNEL` in device.mk
- `dtb/`: Yupik SoC base dtb, `BOARD_PREBUILT_DTBIMAGE_DIR`; mkbootimg takes it as `--dtb`
- `dtbo.img`: redwood overlay, `BOARD_PREBUILT_DTBOIMAGE`
- `modules/`: the vendor and GKI modules loaded in first stage init, signed by this build, and
  `modules.load` in load order; `BOARD_VENDOR_RAMDISK_KERNEL_MODULES` and `_LOAD`
- `kernel-headers/`: UAPI headers for building vendor userspace, `TARGET_KERNEL_SOURCE`

The dtb rides in vendor_boot (`BOARD_INCLUDE_DTB_IN_BOOTIMG`, header v3); it is not appended to
`Image`. The modules keep their signature, so they must not be stripped again
(`BOARD_DO_NOT_STRIP_VENDOR_RAMDISK_MODULES`).

    Image sha256 f3244e6128f769b7c3cec130458c2d56838d5190f501f91969ed7b27c585ca81

The headers are the UAPI the platform's vendor HALs are written against, the same set the 5.4
kernel shipped here, which this kernel serves unchanged. From this tree by `make headers_install`:
the IPA headers (`msm_ipa.h`, `ipa_qmi_service_v01.h`, `rmnet_ipa_fd_ioctl.h`), whose layouts
ipacm and libipanat must match, and `linux/version.h`.
