<div align="center">
# GKI KernelSU SUSFS

### Automated Build Repository for ReSukiSU

**Automated GKI Kernel Builds \| Integrated with ReSukiSU + SUSFS**

[![Release](https://img.shields.io/github/v/release/coolzyd9107/GKI_KernelSU_SUSFS?label=Release&style=flat-square&logo=github&logoColor=white&color=2ea44f)](https://github.com/ReSukiSU-GKI/GKI_KernelSU_SUSFS/releases)
[![Telegram](https://img.shields.io/static/v1?label=Telegram&message=Channel&color=0088cc)](https://t.me/ReSukiSUKernelBuilds)
[![ReSukiSU](https://img.shields.io/badge/ReSukiSU-Supported-5AA300?style=flat-square)](https://kernelsu.org/)
[![SUSFS](https://img.shields.io/badge/SUSFS-Integrated-E67E22?style=flat-square)](https://gitlab.com/simonpunk/susfs4ksu)

------------------------------------------------------------------------
</div>

## ⚠️ Repository Notes

1.  This repository is forked from **zzh20188/GKI_KernelSU_SUSFS**. I
    have only made partial modifications and bug fixes. If possible,
    please prioritize using the original upstream repository.

2.  This repository only supports building kernels integrated with
    **ReSukiSU**. Support for all other KernelSU variants has been
    completely removed. If you need to build kernels with other KernelSU
    variants, please fork the upstream repository
    **zzh20188/GKI_KernelSU_SUSFS** and build them yourself.

## 💰 Special Thanks

-   **coolzyd9107**: Creator and owner of this repository (according to
    the original author, "not very good at many things").
-   **zzh20188**: Author of the upstream repository.
-   **zhuzhuzihan**: Helped with numerous fixes and improvements,
    provides the server for our Telegram Bot, and is the primary
    developer of the bot.
-   **TanakaLun**: Contributed numerous fixes and improvements.
-   **YC酱luyancib**: Helped develop the Telegram Bot and contributed
    ideas for workflow and bot improvements.
-   **AlexLiuDev233**: Helped fix issues in the build workflow.
-   **cctv18**: Helped fix build workflow issues, contributed ideas for
    Linux 6.12 kernel support, and provided solutions for several
    SUSFS-related problems.

> Note: Usernames marked with an asterisk (\*) indicate that the
> contributor's GitHub account is currently unavailable or hidden.

------------------------------------------------------------------------

## ⚠️ Important Updates

> **Notice:** OnePlus devices running ColorOS 14 or 15 are currently
> **not supported**. Flashing may require a factory reset before the
> device can boot.

> **ReSukiSU:** ReSukiSU is updated more frequently than SukiSU. If you
> encounter issues with SukiSU, try ReSukiSU instead.

> **The default KernelSU variant has been changed to ReSukiSU.**

> **Android 16:** Android 16 with the Linux 6.12 kernel is now
> supported.

> Starting from commit **#c17aae5**, this repository has completely
> removed support for building kernels with KernelSU variants other than
> ReSukiSU. If you prefer using another KernelSU manager, don't
> worry---we have enabled **multi-manager** support. The kernel driver
> remains ReSukiSU, but it is compatible with most other KernelSU
> managers, including KowSU and SukiSU-Ultra. However, when reporting
> issues, please always submit logs using the ReSukiSU Manager.

> **Re-Kernel (Experimental):** Re-Kernel support has been added and is
> currently in the testing phase.

------------------------------------------------------------------------

## 🧪 Droidspaces Container Support (Experimental)

> **Experimental Feature:** Successful compilation and booting are not
> guaranteed on every GKI version. Always back up your boot image before
> flashing.

> **Tip:** The workflow uses the official GKI kernel patches from
> Droidspaces. Since three different patch sets are available, you may
> need to test them to determine which one works best for your device.

Droidspaces is a lightweight Linux container solution for Android that
can run a complete Linux environment (including systemd, OpenRC, and
more).

**Supported kernels:** 5.10 / 5.15 / 6.1 / 6.6 / 6.12

**Workflow options:**

   Option  Description
  -------- ----------------------------------------
   `off`   Disabled (default)
   `678`   Use the 6_7_8 slot patch (recommended)
   `123`   Use the 1_2_3 slot patch (alternative)
   `345`   Use the 3_4_5 slot patch (alternative)

> **Note:** Linux 6.12 has only one patch, so selecting any option other
> than `off` is sufficient.

If the build fails or the device bootloops after flashing, try switching
to another patch set.

------------------------------------------------------------------------

## 🧪 Spoof `/proc/config.gz` (Stock Config)

This is an advanced feature and does not require a workflow option.

During the build process, the workflow automatically checks whether
`config/stock_defconfig` exists. If it does, it is applied
automatically; otherwise, it is skipped.

Usage:

1.  Make sure your device is running the stock ROM and stock kernel.
2.  Extract `/proc/config.gz` from your device.
3.  Decompress it, rename it to `stock_defconfig`, upload it to the
    `config/` directory, and commit it.

The build process will automatically:

-   Copy it to `$KERNEL_ROOT/common/arch/arm64/configs/stock_defconfig`
-   Modify `$KERNEL_ROOT/common/kernel/Makefile` so that
    `$(obj)/config_data` uses `arch/arm64/configs/stock_defconfig`
    instead of `$(KCONFIG_CONFIG)`
-   Make `/proc/config.gz` in the compiled kernel closely match your
    stock kernel configuration

------------------------------------------------------------------------

<div align="center">
**More content will be added in future updates...**

⭐ If this project helps you, please consider giving it a Star!

⭐ For notifications about new prebuilt releases and major updates,
follow our Telegram channel.
</div>