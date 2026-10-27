# OceanTriRecomp Android (Cheats Mod Edition) 🦖📱⚡

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](LICENSE)
[![Platform: Android](https://img.shields.io/badge/Platform-Android%20ARM64-green.svg)](https://github.com/efryansyah29/OceanTriRecomp-Android)
[![Latest Release](https://img.shields.io/badge/Release-v1.5--cheats--final-brightgreen.svg)](https://github.com/efryansyah29/OceanTriRecomp-Android/releases)

Native **Android ARM64** port of **Monster Hunter Tri (Wii)** through static Ahead-of-Time (AOT) binary recompilation. Experience native hardware execution with zero heavy emulation overhead, now featuring an interactive **In-Game Cheats Selector** and full compatibility for **Android 14, 15, and 17 (PixelOS / POCO X6 5G)**.

> **Original Base Project:** Forked from [Kiridor123/OceanTriRecomp-Android](https://github.com/Kiridor123/OceanTriRecomp-Android) (upstream by [krisztsa/OceanTriRecomp](https://github.com/krisztsa/OceanTriRecomp)).

---

## 🌟 What's New in This Fork?

This fork enhances the official v1.5 release with user-facing quality-of-life enhancements, modernized packaging, and an integrated cheat engine:

### 🛡️ 1. Interactive In-Game Cheats Selection Dialog
While the underlying Capcom/Recomp engine contained built-in cheat toggles, there was no native UI to activate them on Android. This fork adds an interactive selection modal upon launching the game:
- **🛡️ God Mode (No Damage)**: Hunter is invulnerable to all monster damage.
- **⚡ Infinite Stamina**: Endless sprinting, evading, and attacking without stamina loss.
- **🫧 Infinite Air (Oxygen)**: Endless underwater swimming and diving breath.
- **🎒 Infinite Items**: Consumables in pouch (Potions, Whetstones, Rations, Traps) never deplete.
- **🏹 Infinite Ammo**: Bowgun shots and coatings do not consume pouch ammo.
- **💰 Infinite Zenny**: Grants 9,999,999z for equipment crafting and upgrades.
- **💾 Automatic Persistence**: Preferences are saved to `/storage/emulated/0/MH3/cheats.txt` and reloaded automatically.
- **🌐 Online Fair-Play Protection**: Safe checks prevent disruptive exploits when connected to Loc Lac online servers (`mh3sp.com`).

### 📱 2. Android 15 & 17 (PixelOS / POCO X6 5G) Compatibility Fixes
- **16KB Page Alignment & Uncompressed Resources**: Fixed the notorious `"App not installed / Package appears to be invalid"` error on bleeding-edge Android 15/17 custom ROMs (such as PixelOS on Snapdragon 7s Gen 2). `resources.arsc` and app assets are stored with zero compression and exact 4-byte boundaries.
- **Cold-Start Crash Fix**: Resolved instant crash on startup caused by early `SDLActivity` lifecycle dialog execution before window tokens were ready (`WindowManager.BadTokenException`).
- **Clean Single-Engine Architecture**: Repackaged on top of the rock-solid v1.5 engine binaries to eliminate native JNI symbol conflicts.

### 🎮 3. Gamepad & Controller Optimization
- Tested and verified with **GameSir Nova Lite**, **Xbox Wireless Controllers**, and **Nintendo Switch Pro Controllers** over Bluetooth and USB-C OTG.
- Full support for setting **Touch Opacity to 0%** in *Settings → Controls* for a clean, TV-like HUD experience on your phone.

---

## 📲 Quick Start / Installation

1. Go to the **[Releases](https://github.com/efryansyah29/OceanTriRecomp-Android/releases)** page.
2. Download the latest **`OceanTriRecomp-Android-v1.5-cheats.apk`**.
3. Install the APK on your Android device (ensure previous versions are uninstalled first if you encounter signature conflicts).
4. Provide your legally dumped Monster Hunter Tri PAL European ROM (`RMHP08.iso` or `RMHP08.rvz`):
   - Place the ROM into `/storage/emulated/0/MH3/` on your internal storage, **OR**
   - Tap **Select ROM** when prompted by the app to browse and pick the file.
5. Select your desired cheats on the startup screen, tap **Start Game**, and enjoy your hunt!

---

## 🙏 Credits & Upstream Projects

This project stands upon the incredible work of the open-source recompilation community:

### Base Recompilation Engine: OceanTriRecomp
> **Upstream Project: [krisztsa/OceanTriRecomp](https://github.com/krisztsa/OceanTriRecomp)**  
> All credit for the static PowerPC → C++ recompilation architecture, the modern rendering pipeline via Aurora HAL, and the core game runtime belongs to **[krisztsa](https://github.com/krisztsa)**.

### Android Upstream Port: Kiridor123
> **Android Port: [Kiridor123/OceanTriRecomp-Android](https://github.com/Kiridor123/OceanTriRecomp-Android)**  
> Credit to **Kiridor123** for porting OceanTriRecomp to Android ARM64, touchscreen layout engine, audio pipeline, and mobile adaptations.

### Online Multiplayer Server: MH3SP
> Online multiplayer (Loc Lac City) is powered by **[sepalani/MH3SP](https://github.com/sepalani/MH3SP)** created by **[Sepalani](https://github.com/sepalani)**. Client patches derived from [sepalani/MH3SP-patcher](https://github.com/sepalani/MH3SP-patcher) under AGPL-3.0. Connects to `mh3sp.com`.

### Recompilation Toolchain: WiiCompiled
> Static PowerPC → C++ translator and ABI bridge based on **WiiCompiled** (commit `85f250155f`). See [`toolchain/ORIGIN.md`](toolchain/ORIGIN.md) for details.

### Additional Dependencies
| Project | Usage | License |
|---|---|---|
| [Aurora](https://github.com/encounter/aurora) | Graphics HAL (SDL3 + OpenGL ES 3.0) | MIT |
| [libSDL3](https://github.com/libsdl-org/SDL) | Windowing, audio, and multi-platform input | zlib |
| [Dolphin Emulator](https://github.com/dolphin-emu/dolphin) | Hardware behavior reference & HD texture pack format | GPL-2.0 |
| [Crypto++](https://github.com/weidai11/cryptopp) | Network cryptography (SHA-1, ECDSA) | BSL-1.0 |
| [pugixml](https://github.com/zeux/pugixml) | XML parser for Riivolution patches | MIT |
| [toml11](https://github.com/ToruNiina/toml11) | Configuration file parser | MIT |

---

## ✨ Features Inherited from v1.5 Base

- **Native Android Keyboard**: Seamlessly opens your software keyboard (Gboard, Samsung Keyboard, etc.) for hunter naming, chat, and equipment naming.
- **Cutscene Skip**: Skip real-time cutscenes and pre-rendered opening THP videos by pressing the **A button** or **+**.
- **Frame Rate Freedom**: Freely switch between 30, 60, 90, or 120 FPS in *Settings → Graphics*.
- **HD Texture Replacement**: Place Dolphin HD texture packs into `/storage/emulated/0/MH3/textures/` with hot-reload support.
- **On-Screen Virtual Controls & Macro Buttons**: Fully customizable touch layout, analog sticks, M1-M4 combo macros, and transparency adjustments.
- **Audio Lifecycle Recovery**: Automatic reconnection of AAudio streams when switching apps or locking the screen.
- **Diagnostic Logging**: Logs saved to `/storage/emulated/0/MH3/logs/` (`game_log.txt`, `oceantri_log.txt`, `oceantri_crash.txt`).

---

## 🛠️ Hardware & OS Requirements

- **Processor**: 64-bit ARMv8-A (Snapdragon, MediaTek Dimensity, Google Tensor, Samsung Exynos).
- **Operating System**: Android 10 (API Level 29) up to Android 15, 16, and 17.
- **Graphics Backend**: OpenGL ES 3.0 or higher.
- **Free Storage**: ~3 GB to 5 GB for game data and optional HD texture packs.
- **Game ROM**: Legally dumped European Monster Hunter Tri ROM with Game ID **`RMHP08`** (`.iso` or `.rvz`).

---

## 🏗️ Building from Source

### Prerequisites
- Linux / Ubuntu 22.04+ (or GitHub Actions runner)
- Android SDK Build-Tools 35.0.0+
- Java JDK 17+
- Python 3

### Fast Repackage Workflow
To recompile Java UI changes and package into the stable v1.5 base:
```bash
# 1. Clone repository
git clone https://github.com/efryansyah29/OceanTriRecomp-Android.git
cd OceanTriRecomp-Android

# 2. Trigger automated GitHub Actions CI
# The workflow automatically fetches the base engine, injects modified bytecode,
# aligns, signs, and publishes the release artifact.
```

---

## ⚖️ License & Disclaimer

### Source Code License
This project is licensed under the **GNU General Public License v3.0 (GPLv3)**. See [LICENSE](LICENSE) for details.

### Legal Disclaimer
- **Monster Hunter** and **Monster Hunter Tri** are registered trademarks of **Capcom Co., Ltd.**
- **Wii** is a registered trademark of **Nintendo Co., Ltd.**
- This project is an independent, non-commercial open-source research and preservation effort. It is not affiliated with, endorsed, or sponsored by Capcom or Nintendo.
- **NO copyrighted game assets, proprietary ROMs, textures, 3D models, or audio are distributed in this repository or its Releases.** Users must provide their own legally acquired copy of *Monster Hunter Tri (PAL RMHP08)*.