# POCO X8 Pro (klee) Custom ROMs & Development Hub
Welcome to the central community repository for POCO X8 Pro (`klee`) custom software, ROM indexes, and development resources.

## Official ROMs

| Name | Platform | Maintainer | Notes | Source |
| :--- | :--- | :--- | :--- | :--- |
| **Halcyon** | Android 16 | [Khayloaf](https://t.me/khayloaf) | GApps & Vanilla available | [Download](https://get.hlcyn.org/builds/klee) |
| **Infinity X** | Android 16 | [bezke](https://t.me/bezke1) | Integrated Fenrir for native integrity. Requires Fenrir boot/vendor_boot | [Download](https://projectinfinity-x.com/downloads/klee) / [Telegram Post](https://t.me/Poco_X8ProUpdates/13) |


## Community ROMs

| Name | Platform | Maintainer | Notes | Source |
| :--- | :--- | :--- | :--- | :--- |
| **DyperOS** | HyperOS 3.0.304.0 (CN) | [Fiqih Wijaya](https://t.me/Fiqih_wijaya) | Fastboot flashable. Includes Fenrir kernel. `NoModApp` build recommended for 8GB RAM. | [PixelDrain](https://pixeldrain.com/u/Dynnb2CA) / [Telegram Post](https://t.me/WorstDOSMod/283)
| **HyperDot** | HyperOS 3.0.303.0 (ID) | [Raka Rizaldy](https://t.me/rakarizaldy) | Includes OrangeFox by default, debloated, modded system apps. Fenrir kernel flashable via OrangeFox Klee Tools. | [SourceForge](https://sourceforge.net/projects/hyperdot/files/HyperOS-STABLE-UPDATES/HyperOS3.0/HyperDot%20Klee%20OS3.303.0%20WPJIDXM.zip/download) / [Telegram Channel](https://t.me/MrDoubleR_Channel) |
| **ColorOS** | ColorOS 16.0.9 | [KazeTheLight](https://t.me/KazeTheLight) | Ported from OnePlus Ace 5 Ultra. Fastboot flashable. Enroll fingerprint twice. | [Drive](https://drive.google.com/file/d/1LLo6mt5V8yyFlUOd45PWKs3VjGVWHGXj/view?usp=drive_link) / [Telegram Post](https://t.me/Poco_X8ProUpdates) |
| **Shinkai** | Android 17 | [Khayloaf](https://t.me/khayloaf) | Community build (Heptakaideka). Signed & enforcing. GApps included; do not swap kernel. | [SourceForge](https://sourceforge.net/projects/kylieerom/files/Shinkai/heptakaideka/Shinkai-Project_klee-heptakaideka-20260829-1057.zip/download) / [PixelDrain](https://pixeldrain.com/u/3h7qr9RT) / [Telegram Post](https://t.me/Poco_X8ProUpdates/9) |
| **PixelOS** | Android 17 | [Khayloaf](https://t.me/khayloaf) | GApps included | [SourceForge](https://sourceforge.net/projects/kylieerom/files/pixelos/seventeen/PixelOS_klee-17.0-20260822-0944.zip/download) / [PixelDrain](https://pixeldrain.com/u/8u1VQsnj) / [Telegram Post](https://t.me/CilokDiscussion/43135) |

## Resources

* **Telegram Updates Channel:** [Poco X8 Pro Updates](https://t.me/Poco_X8ProUpdates)
* **Telegram Community Group:** [Poco X8 Pro Community](https://t.me/PocoX8ProCommunity)

## Kernels & Recoveries

| Type | Name | Mantainer | Notes | Source |
| :--- | :--- | :--- | :-------- | :--- |
| **Kernel / LK** | **Fenrir** | [KazeTheLight](https://t.me/KazeTheLight) | LK & Preloader patch for Stock HyperOS (ID/CN/GL). Enables Strong Integrity. Requires ENG Preloader & `fastboot -w`. | [Telegram Post](https://t.me/Poco_X8ProUpdates/12) |
| **Recovery** | **OrangeFox** | [camerado842](https://sourceforge.net/u/camerado84/profile/) | OFRP build for Android 16 / GKI | [SourceForge](https://www.google.com/url?sa=i&source=web&rct=j&url=https://sourceforge.net/projects/recovery-for-xiaomi-devices/files/klee/OrangeFox-R12.0-Unofficial-klee.img/download&ved=2ahUKEwjRlrKZzsSWAxXPyDgGHZmGCZsQy_kOegYIAAgSEAI&opi=89978449&cd&psig=AOvVaw0PmEpdztAlpzu5wi0QEYwr&ust=1788050736973000) |

### ⚠️ Fenrir Flashing Guide (Stock HyperOS Only)

> **Warning:** Fenrir modifies low-level `lk` and `preloader` partitions. Back up your stock `lk.img` before proceeding. Requires a data wipe.

1. **Prerequisites:** Must be on Stock HyperOS (Bases: `3.302.0 ID`, `3.304.0 CN`, or `3.304.0 GL`).
2. **Flash ENG Preloader:** 
   ```bash
   fastboot flash preloader_ab eng_preloader.bin
3. **Flash Fenrir LK**
   ```bash
   fastboot flash lk_ab fenrir_lk.img
5. **Wipe & Reboot**
   ```bash
   fastboot -w
   fastboot reboot

> 💡 **Fenrir Security & Flashing Rules:**
> * **Rooting:** Patch `init_boot` with KernelSU only. Do **NOT** flash custom GKI kernels on Fenrir setups.
> * **Data Wipe Mandate:** Moving between Fenrir and non-Fenrir builds strictly requires a full data format (`fastboot -w`).
> * **Detection Limits:** Fenrir handles hardware lock spoofing (`MEETS_STRONG_INTEGRITY` & Widevine L1). To hide root/custom ROM files from strict banking apps, pair it with **Hide My Applist (HMA)** and **SuSFS**.

## Official Stock Firmware (Unbrick & Relock)

> ⚠️ **Important:** Only relock your bootloader after flashing the official stock Fastboot firmware (`.tgz`) matching your phone's physical hardware region (e.g., `MI` for Global). Never lock on custom ROMs.
* **Latest Global Firmware (`MI`):** `3.0.306.0.WPJMIXM`
* **Latest China Firmware (`CN`):** `3.0.304.0.WPJCNXM`
## Play Integrity & Banking Setup
To pass Play Integrity (`MEETS_DEVICE_INTEGRITY`) when running root on custom ROMs:
1. **Root Engine:** Use **KernelSU-Next** (v3.3.0+) or **APatch**.
2. **Stealth Layer:** Integrate **SuSFS** (v2.2.0+) at kernel level + **NoMounts** metamodule.
3. **Spoofing Stack:** Combine **Zygisk Next** and **AlwaysStrong** / **PlayIntegrityFork**.

## Essential Root Toolkit & Modules

| Category | Module | Purpose | Source |
| :--- | :--- | :--- | :--- |
| **Keybox Spoofing** | **Tricky Store** | Bypasses hardware key attestation for high-security banking/enterprise apps | [GitHub](https://github.com/5ec1cff/TrickyStore) |
| **App Isolation** | **Hide My Applist (HMA)** | Hides root apps (KernelSU Manager, Termux) from aggressive detectors | [GitHub](https://github.com/Dr-TSNG/Hide-My-Applist) |
| **Safety Rescue** | **Yet Another Bootloop Protector (YABP)** | Auto-disables rogue modules if the phone fails to boot or SystemUI crashes | [GitHub](https://github.com/Magisk-Modules-Alt-Repo/YetAnotherBootloopProtector) |
| **Framework** | **LSPosed (Zygisk Release)** | Required to run system customization modules like HyperCeiler | [GitHub](https://github.com/mywalkb/LSPosed_mod) |

## Quick Troubleshooting & Common Issues
* **Banking app still detects root?** Enable target isolation in KernelSU-Next/HMA, clear data for *Google Play Services*, *Play Store*, and your banking app, then reboot.
* **Stuck in bootloop after flashing a module?** Reboot into OrangeFox Recovery -> **Menu > Files** -> navigate to `/data/adb/modules/` and delete the folder of the offending module.

## Contributing & Updating

Maintained a new build or found a broken download link? 
* Open a **Pull Request** targeting `README.md`.
* Submit an entry under the **Issues** or **Discussions** tab.
