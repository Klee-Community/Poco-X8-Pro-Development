# POCO X8 Pro (klee) Custom ROMs & Development Hub
Welcome to the central community repository for POCO X8 Pro (`klee`) custom software, ROM indexes, and development resources.
## Official Custom ROMs

| ROM Name | Android Version | Maintainer | Notes | Link |
| :--- | :--- | :--- | :--- | :--- |
| **Halcyon** | Android 16 | [Khayloaf](https://t.me/khayloaf) | GApps & Vanilla available | [Download](https://get.hlcyn.org/builds/klee) |
| **Infinity-X** | Android 16 | [bezke](https://t.me/bezke1) | Backlight features confirmed. GApps & Vanilla available | [Download](https://projectinfinity-x.com/downloads/klee) |

## Modified OS & Firmware Ports

| ROM Name | Base | Type | Notes | Download / Source |
| :--- | :--- | :--- | :--- | :--- |
| **Ximi DyperOS** | HyperOS 3.0.304.0 (CN) | Modded | Fastboot flashable. Includes Fenrir kernel. `NoModApp` build recommended for 8GB RAM. | [Download](https://pixeldrain.com/u/Dynnb2CA) / [Telegram Post](https://t.me/WorstDOSMod/283)
| **ColorOS 16** | OnePlus Ace 5 Ultra | Port | Fastboot flashable. Enroll fingerprint twice. | [Download](https://drive.google.com/file/d/1LLo6mt5V8yyFlUOd45PWKs3VjGVWHGXj/view?usp=drive_link) / [Telegram Post](https://t.me/Poco_X8ProUpdates) |

## Development Resources
* **Telegram Updates Channel:** [Poco X8 Pro Updates](https://t.me/Poco_X8ProUpdates)
* **Telegram Community Group:** [Poco X8 Pro Community](https://t.me/PocoX8ProCommunity)

## Custom Kernels & Recoveries

| Type | Name | Maintainer / Credits | Notes | Link |
| :--- | :--- | :--- | :--- | :--- |
| **Kernel** | **Fenrir** | [KazeTheLight](https://t.me/KazeTheLight) | Pre-baked in DyperOS/ColorOS ports | [Telegram](https://t.me/Shinlab/1166) |
| **Recovery** | **OrangeFox** | [camerado842](https://sourceforge.net/u/camerado84/profile/) | OFRP build for Android 16 / GKI | [SourceForge](https://www.google.com/url?sa=i&source=web&rct=j&url=https://sourceforge.net/projects/recovery-for-xiaomi-devices/files/klee/OrangeFox-R12.0-Unofficial-klee.img/download&ved=2ahUKEwjRlrKZzsSWAxXPyDgGHZmGCZsQy_kOegYIAAgSEAI&opi=89978449&cd&psig=AOvVaw0PmEpdztAlpzu5wi0QEYwr&ust=1788050736973000) |

## Official Stock Firmware (Unbrick & Relock)
> ⚠️ **Important:** Only relock your bootloader after flashing the official stock Fastboot firmware (`.tgz`) matching your phone's physical hardware region (e.g., `MI` for Global). Never lock on custom ROMs.
* **Latest Global Firmware (`MI`):** `3.0.306.0.WPJMIXM`
* **Latest China Firmware (`CN`):** `3.0.304.0.WPJCNXM`
## Play Integrity & Banking Setup
To pass Play Integrity (`MEETS_DEVICE_INTEGRITY`) when running root on custom ROMs:
1. **Root Engine:** Use **KernelSU-Next** (v3.3.0+) or **APatch**.
2. **Stealth Layer:** Integrate **SuSFS** (v2.2.0+) at kernel level + **NoMounts** metamodule.
3. **Spoofing Stack:** Combine **Zygisk Next** and **AlwaysStrong** / **PlayIntegrityFork**.
## Contributing & Updating
Maintained a new build or found a broken download link? 
* Open a **Pull Request** targeting `README.md`.
* Submit an entry under the **Issues** or **Discussions** tab.
