# 📌 Progress Tracker: OceanTriRecomp-Android (Custom Mod with Cheats Overlay)

## 🎯 Current Objectives
- [x] Fork repositori upstream ke akun pengguna (`efryansyah29/OceanTriRecomp-Android`)
- [x] Selesaikan root-cause force close pada Android 15/17 (PixelOS POCO X6 5G)
- [x] Implementasikan dialog aktivasi cheat interaktif in-game (God Mode, Inf Stamina, Inf Oxygen, Inf Items, Inf Ammo, Zenny)
- [x] Pasang persistensi konfigurasi cheat di `/storage/emulated/0/MH3/cheats.txt`
- [x] Rilis APK stabil siap main `v1.5-cheats-final` ke GitHub Releases
- [x] Terjemahkan dan perbarui `README.md` ke Bahasa Inggris profesional lengkap dengan dokumentasi mod & kredit original

## 🔄 Actions Done (Rolling Window 5–7 items)
- 2026-10-27: Analyzed root cause of cold-start crash: Kiridor's experimental CI built SDL3 statically into `libmain.so`, colliding with `libSDL3.so`. Official `v1.5` binary is confirmed 100% stable on Android 17 / PixelOS POCO X6.
- 2026-10-27: Built direct mod on top of official `v1.5` engine: injected Cheat Engine interactive dialog (God Mode, Inf Stamina, Inf Oxygen, Inf Items, Inf Ammo, Zenny) and `/storage/emulated/0/MH3/cheats.txt` persistence into `OceanTriActivity`.
- 2026-10-27: Fixed `resources.arsc` compression issue in repackaged APK, ensuring flawless installation on Android 17 / PixelOS.
- 2026-10-27: Successfully published working APK `OceanTriRecomp-Android-v1.5-cheats.apk` on release tag `v1.5-cheats-final`.
- 2026-10-27: Verified in-game gameplay and controller support (GameSir Nova Lite / Xbox / Switch Pro layout).
- 2026-10-27: Updated `README.md` to English, adding comprehensive documentation for the Cheats Mod, Android 17 fixes, and preserving all original credits.

## ⚠️ Known Blockers & Edge Cases
- None (Game, Cheats Dialog, dan Controller support berjalan lancar).

## 🚀 Next Steps
1. Nikmati permainan Monster Hunter Tri di Android dengan GameSir Nova Lite!
