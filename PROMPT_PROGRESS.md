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
- 2026-10-27: Implemented `ApplyCheats()`, `SaveCheats()`, and `LoadCheats()` for zero-crash cheat persistence.
- 2026-10-27: Patched `runtime/src/cheats.cpp` to evaluate active cheats dynamically per-frame instead of static-once.
- 2026-10-27: Successfully compiled and published initial release `v1.5.5-cheats` on GitHub Actions.
- 2026-10-27: Root-caused instant cold-start crash: `super.onCreate()` called after dialog trigger, causing `WindowManager.BadTokenException`.
- 2026-10-27: Patched `OceanTriActivity.java` lifecycle flow, safe dialog handlers, and deferred ROM verification to `onResume()`.
- 2026-10-27: Updated GitHub Actions workflow for release tag `v1.5.5-cheats-r2`.

## ⚠️ Known Blockers & Edge Cases
- Tanpa file ROM (`RMHP08`), game tidak memiliki asset grafis/audio untuk dijalankan.
- ROM wajib Monster Hunter Tri PAL Game ID `RMHP08` (`.rvz` atau `.iso`).

## 🚀 Next Steps
1. Push perbaikan cold-start crash ke `origin main` untuk memicu build APK v1.5.5-r2.
2. Unduh file ROM Monster Hunter Tri PAL `RMHP08.rvz` ke HP di folder `/storage/emulated/0/MH3/`.
3. Pasang APK baru dan jalankan game.
