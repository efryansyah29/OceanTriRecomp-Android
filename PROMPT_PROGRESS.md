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
- 2026-10-27: Successfully compiled and published initial release `v1.5.5-cheats` on GitHub Actions.
- 2026-10-27: Root-caused instant cold-start crash on POCO X6 5G (PixelOS / Android 15+).
- 2026-10-27: Identified compressed `.so` packaging (`jar -uf` instead of `jar -0`) causing failure on Android 15 16KB-page-size dynamic linker.
- 2026-10-27: Patched `build_apk.sh` with `jar -0 -uf` for uncompressed `.so` so `zipalign -P 16 -f 4` achieves true 16KB page alignment.
- 2026-10-27: Adjusted `targetSdkVersion` to 34 in `AndroidManifest.xml` to prevent Android 15 sandbox termination.
- 2026-10-27: Hardened `SDLActivity.java` and `OceanTriActivity.java` with safe async dialogs and JNI library load tracking.
- 2026-10-27: Triggering GitHub Actions CI/CD pipeline for release `v1.5.5-cheats-r3`.

## ⚠️ Known Blockers & Edge Cases
- Tanpa file ROM (`RMHP08`), game tidak memiliki asset grafis/audio untuk dijalankan.
- ROM wajib Monster Hunter Tri PAL Game ID `RMHP08` (`.rvz` atau `.iso`).

## 🚀 Next Steps
1. Push perbaikan 16KB page alignment dan PixelOS fix ke `origin main`.
2. Monitor jalannya workflow GitHub Actions v1.5.5-cheats-r3.
3. Unduh APK baru di POCO X6 5G PixelOS dan verifikasi bahwa aplikasi tidak force close.
