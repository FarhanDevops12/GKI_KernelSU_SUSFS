<div align="center">GKI KernelSU SUSFS

Automated Build Repository Dedicated to ReSukiSU

Automated GKI Kernel Builds | Integrated with ReSukiSU + SUSFS

""Release" (https://img.shields.io/github/v/release/coolzyd9107/GKI_KernelSU_SUSFS?label=Release&style=flat-square&logo=github&logoColor=white&color=2ea44f)" (https://github.com/ReSukiSU-GKI/GKI_KernelSU_SUSFS/releases)
""Telegram" (https://img.shields.io/static/v1?label=Telegram&message=Channel&color=0088cc)" (https://t.me/ReSukiSUKernelBuilds)
""ReSukiSU" (https://img.shields.io/badge/ReSukiSU-Supported-5AA300?style=flat-square)" (https://kernelsu.org/)
""SUSFS" (https://img.shields.io/badge/SUSFS-Integrated-E67E22?style=flat-square)" (https://gitlab.com/simonpunk/susfs4ksu)

---

</div>⚠️ Repository Notice

① This repository is forked from "zzh20188/GKI_KernelSU_SUSFS" (https://github.com/zzh20188/GKI_KernelSU_SUSFS/). I have only made partial modifications and bug fixes. If possible, please consider forking the original upstream repository first.

② This repository only supports building kernels integrated with ReSukiSU. Support for all other KernelSU variants has been completely removed. If you need to build a kernel with another KernelSU variant, please fork the upstream repository "zzh20188/GKI_KernelSU_SUSFS" (https://github.com/zzh20188/GKI_KernelSU_SUSFS/) and build it yourself.

💰 Special Thanks

"coolzyd9107" (https://github.com/coolzyd9107): Creator and owner of this repository. (He jokingly describes himself as "pretty useless" and says there are still many things he doesn't know.)

"zzh20188" (https://github.com/zzh20188): Author of the upstream repository on which this project is based.

"zhuzhuzihan" (https://github.com/zhuzhuzihan): Contributed numerous fixes and improvements, provides the server for our Telegram Bot (because the repository owner couldn't afford one), and is the primary developer of the Telegram Bot.

"TanakaLun" (https://github.com/TanakaLun): Contributed numerous fixes and improvements.

"YC酱luyancib" (https://github.com/luyanci): Assisted in developing the Telegram Bot and provided ideas for workflow fixes and Bot implementation.

"AlexLiuDev233" (https://github.com/AlexLiuDev233): Helped resolve issues in the build workflow.

"cctv18" (https://github.com/cctv18): Helped resolve build workflow issues, contributed ideas for adding Linux 6.12 kernel build support, and provided solutions for several SUSFS-related issues.

Note: Usernames marked with an asterisk (*) indicate collaborators whose GitHub accounts are currently unavailable or hidden.

---

⚠️ Important Updates

«Notice: OnePlus devices running ColorOS 14 or 15 are currently not supported. Flashing may require a factory reset before the device can boot.»

«ReSukiSU: ReSukiSU is updated more frequently than SukiSU. If you encounter issues with SukiSU, try using ReSukiSU instead.

The default KernelSU variant has been changed to ReSukiSU.»

«Android 16: Android 16 with the Linux 6.12 kernel is now supported.

Starting from commit #c17aae5, this repository has completely removed support for building kernels with KernelSU variants other than ReSukiSU. However, if you prefer using another KernelSU manager for any reason, there's no need to worry. We have enabled multi-manager support. Although the KernelSU driver inside the kernel remains ReSukiSU, it is compatible with most other KernelSU managers, such as KowSU and SukiSU-Ultra. You can therefore continue using your preferred manager. However, when reporting issues, please make sure to submit logs using the ReSukiSU Manager.»

«ReKernel Support (Experimental): ReKernel integration is now supported and is currently in the testing phase.»

---

🧪 Droidspaces Container Support (Experimental)

«Experimental Feature: Successful compilation and booting are not guaranteed on every GKI version. Please back up your boot image before flashing.

Tips: The workflow uses the official GKI kernel patches provided by "Droidspaces" (https://github.com/ravindu644/Droidspaces-OSS) from its "official patch repository" (https://github.com/ravindu644/Droidspaces-OSS/tree/main/Documentation/resources/kernel-patches/GKI). If you know of better patches, feel free to open an issue. Since three different patch sets are available, you may need to test multiple options to determine which one works best for your device. Choose based on community feedback or your own testing.»

"Droidspaces" (https://github.com/ravindu644/Droidspaces-OSS) is a lightweight Linux container solution that allows Android devices to run a complete Linux environment (including support for systemd, OpenRC, and more). It is suitable for development environments, self-hosted services, and similar use cases.

Supported Kernel Versions: 5.10 / 5.15 / 6.1 / 6.6 / 6.12

How to Use: When manually triggering a workflow, select the Droidspaces Container Support option.

Option| Description
"off"| Disabled (default)
"678"| Use the 6_7_8 slot patch (recommended)
"123"| Use the 1_2_3 slot patch (alternative)
"345"| Use the 3_4_5 slot patch (alternative)

«Note: Linux 6.12 only has a single available patch. Selecting any option other than "off" will use it.»

If the build fails or the device bootloops after flashing: Try switching to another slot patch (for example, "678 → 123" or "345"). Different kernel subversions may require different patches.

---

🧪 Spoof "/proc/config.gz" (Stock Config)

This is an advanced feature and does not require manual enabling in the workflow.

During the build process, the workflow automatically checks whether "config/stock_defconfig" exists. If it does, it is applied; otherwise, it is skipped.

How to Use

1. Make sure your device is running the official ROM with the official kernel.
2. Obtain the device's "/proc/config.gz" file (either directly on the phone or from a computer).
3. Extract it, rename it to "stock_defconfig", upload it to the repository's ""config/"" (config/) directory, and commit the change (this can even be done directly from your phone).

The build process will automatically:

- Copy the file to the kernel source tree:
  "$KERNEL_ROOT/common/arch/arm64/configs/stock_defconfig"
- Modify the "$(obj)/config_data" rule in:
  "$KERNEL_ROOT/common/kernel/Makefile"
  replacing "$(KCONFIG_CONFIG)" with "arch/arm64/configs/stock_defconfig"
- Make "/proc/config.gz" in the compiled kernel closely match your device's stock kernel configuration.

---

<div align="center">More features and documentation are coming soon...

⭐ If you find this project helpful, please consider giving it a Star!

⭐ For notifications about new prebuilt releases and major project updates, follow our "Telegram Channel" (https://t.me/ReSukiSUKernelBuilds).

</div>