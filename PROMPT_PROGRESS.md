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
- 2026-10-27: Forked `Kiridor123/OceanTriRecomp-Android` to `efryansyah29/OceanTriRecomp-Android`.
- 2026-10-27: Patched `runtime/src/cheats.cpp` to evaluate active cheats dynamically per-frame instead of static-once.
- 2026-10-27: Extended `TouchSettingsEngine` with 6th navigation tab `Cheats`, bilingual EN/ES labels, and custom chip toggles.
- 2026-10-27: Implemented `ApplyCheats()`, `SaveCheats()`, and `LoadCheats()` for zero-crash cheat persistence.
- 2026-10-27: Updated `.github/workflows/build-apk.yml` to trigger automatic release tag `v1.5.5-cheats` on push.

## ⚠️ Known Blockers & Edge Cases
- Kompilasi APK menggunakan GitHub Actions Cloud Runner untuk menghemat storage dan menghindari ketergantungan toolchain NDK 28 lokal di laptop.
- ROM yang didukung tetap Monster Hunter Tri PAL Game ID `RMHP08`.

## 🚀 Next Steps
1. Commit semua berkas yang telah dimodifikasi dan push ke `origin main`.
2. Monitor jalannya workflow GitHub Actions di repository `efryansyah29/OceanTriRecomp-Android`.
3. Verifikasi hasil APK di halaman GitHub Releases.
