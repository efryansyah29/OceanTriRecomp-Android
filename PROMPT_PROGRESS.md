# 📌 Progress Tracker: OceanTriRecomp-Android (Custom Mod with Cheats Overlay)

## 🎯 Current Objectives
- [x] Fork repositori upstream ke akun pengguna (`efryansyah29/OceanTriRecomp-Android`)
- [x] Clone repositori lokal ke `C:\DevOps\OceanTriRecomp-Android`
- [x] Perbaiki bug static caching cheat evaluator pada `runtime/src/cheats.cpp` agar respon dinamis saat runtime
- [x] Rancang dan implementasikan Tab ke-6 "Cheats" di UI Menu Pengaturan (`TouchSettingsEngine` di `runtime/src/touch_controls.cpp`)
- [x] Implementasikan handler sentuhan, sinkronisasi state switch dengan `LauncherCheats`, `Cheats`, dan `PlayerHealth`
- [x] Implementasikan auto-save dan auto-load konfigurasi cheat ke `/storage/emulated/0/MH3/MH3UI.cheats`
- [x] Pasang proteksi keamanan otomatis: Menonaktifkan cheat jika pengguna terhubung ke server online Loc Lac (`mh3sp.com`)
- [x] Konfigurasi workflow GitHub Actions CI/CD (`.github/workflows/build-apk.yml`) untuk kompilasi APK otomatis dan perilisan ke GitHub Releases
- [ ] Lakukan commit dan push ke remote repository `origin main` untuk memicu proses build di cloud GitHub Actions

## 🔄 Actions Done (Rolling Window 5–7 items)
- 2026-10-27: Analyzed root cause of cold-start crash: Kiridor's experimental CI built SDL3 statically into `libmain.so`, colliding with `libSDL3.so`. Official `v1.5` binary is confirmed 100% stable on Android 17 / PixelOS POCO X6.
- 2026-10-27: Built direct mod on top of official `v1.5` engine: injected Cheat Engine interactive dialog (God Mode, Inf Stamina, Inf Oxygen, Inf Items, Inf Ammo, Zenny) and `/storage/emulated/0/MH3/cheats.txt` persistence into `OceanTriActivity`.
- 2026-10-27: Created ultra-fast repackaging pipeline compiling Java classes with `d8` and preserving original official native `.so` libraries.

## ⚠️ Known Blockers & Edge Cases
- Tanpa file ROM (`RMHP08`), game tidak memiliki asset grafis/audio untuk dijalankan.
- ROM wajib Monster Hunter Tri PAL Game ID `RMHP08` (`.rvz` atau `.iso`).

## 🚀 Next Steps
1. Push perbaikan 16KB page alignment dan PixelOS fix ke `origin main`.
2. Monitor jalannya workflow GitHub Actions v1.5.5-cheats-r3.
3. Unduh APK baru di POCO X6 5G PixelOS dan verifikasi bahwa aplikasi tidak force close.
