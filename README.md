====================================================================
📌 PUBGM FLASH (Early Access) - Installation Guide (PC ADB & Brevent)
====================================================================

Repository ini berisi berkas dan panduan teknis untuk memasang 
PUBGM FLASH versi Early Access (Package: com.tencent.igfit) pada 
perangkat Android[span_0](start_span)[span_0](end_span).

Ketersediaan Early Access dibatasi untuk model perangkat atau region 
tertentu, sehingga installer biasa sering kali ditolak[span_1](start_span)[span_1](end_span). Repositori ini 
menyediakan file yang sudah dikemas dalam format .zip berisi 3 file 
split APK (com.tencent.igfit.apk, config.arm64_v8a.apk, dan obbassets.apk)[span_2](start_span)[span_2](end_span) 
beserta 2 metode instalasi manualnya:
1. Via PC (ADB Command)
2. Via Android / Tanpa PC (Aplikasi Brevent)

--------------------------------------------------------------------
🔍 Detail Spesifikasi Aplikasi (via Manifest)
--------------------------------------------------------------------
* Name: PUBGM FLASH[span_3](start_span)[span_3](end_span)
* Package Name: com.tencent.igfit[span_4](start_span)[span_4](end_span)
* Version Name / Code: 4.6.0 / 21540[span_5](start_span)[span_5](end_span)
* Target SDK / Min SDK: Android 15 (SDK 35) / Android 5.0 (SDK 21)[span_6](start_span)[span_6](end_span)
* Structure: Multi-split APKs (com.tencent.igfit.apk + config.arm64_v8a.apk + obbassets.apk)[span_7](start_span)[span_7](end_span)

--------------------------------------------------------------------
🛠️ Persiapan File
--------------------------------------------------------------------
1. Unduh file .zip yang tersedia di repositori ini.
2. Ekstrak file .zip tersebut menggunakan ZArchiver, WinRAR, atau File Manager bawaan.
3. Setelah diekstrak, pastikan Anda mendapatkan 3 file APK berikut[span_8](start_span)[span_8](end_span):
   - com.tencent.igfit.apk (Base APK)[span_9](start_span)[span_9](end_span)
   - config.arm64_v8a.apk (Split Config)[span_10](start_span)[span_10](end_span)
   - obbassets.apk (OBB Data Split)[span_11](start_span)[span_11](end_span)

--------------------------------------------------------------------
💻 Metode 1: Instalasi via PC (ADB Command)
--------------------------------------------------------------------
Prasyarat:
- PC / Laptop dengan ADB Tools (Platform Tools).
- Kabel Data USB.
- USB Debugging diaktifkan pada HP Android (Settings > Developer Options > USB Debugging).

Langkah-langkah:
1. Hubungkan HP ke PC menggunakan kabel data USB.
2. Buka Terminal / Command Prompt (CMD) di dalam folder PC tempat 3 file APK hasil ekstrak berada.
3. Verifikasi koneksi perangkat:
   adb devices
4. Pastikan status perangkat Anda terdeteksi (device).
5. Jalankan perintah adb install-multiple untuk menginstal seluruh file split APK sekaligus:
   
   adb install-multiple -r -g -d com.tencent.igfit.apk config.arm64_v8a.apk obbassets.apk[span_12](start_span)[span_12](end_span)

6. Selesai! Buka aplikasi PUBGM FLASH yang sudah terpasang di smartphone Anda[span_13](start_span)[span_13](end_span).

--------------------------------------------------------------------
📱 Metode 2: Instalasi Tanpa PC (Via Aplikasi Brevent)
--------------------------------------------------------------------
Prasyarat:
- Aplikasi Brevent (Dapat diunduh dari Google Play Store).
- Perangkat Android 11+ (Mendukung Wireless Debugging) & terhubung ke jaringan Wi-Fi.

Langkah-langkah:
1. Buat folder baru di memori internal HP, beri nama "pubgflash".
2. Pindahkan 3 file hasil ekstraksi (com.tencent.igfit.apk, config.arm64_v8a.apk, obbassets.apk) ke folder /sdcard/pubgflash/ tersebut[span_14](start_span)[span_14](end_span).
3. Buka Settings > Developer Options di HP Anda, lalu aktifkan Wireless Debugging (Debugging Nirkabel).
4. Buka aplikasi Brevent, pilih opsi Wireless Debugging Port / Pairing, lalu masukkan kode pairing yang muncul pada setelan HP.
5. Di Brevent, buka menu (titik tiga kanan atas) -> pilih Exec command (Jalankan Perintah).
6. Ketikkan perintah instalasi multiple split APK berikut lalu tekan Enter:

   pm install-multiple -r -g -d /sdcard/pubgflash/com.tencent.igfit.apk /sdcard/pubgflash/config.arm64_v8a.apk /sdcard/pubgflash/obbassets.apk[span_15](start_span)[span_15](end_span)

   (Alternatif jika perintah langsung gagal via Session ID):
   - pm install-create -r -g -d
   - pm install-write SESSION_ID 1 /sdcard/pubgflash/com.tencent.igfit.apk[span_16](start_span)[span_16](end_span)
   - pm install-write SESSION_ID 2 /sdcard/pubgflash/config.arm64_v8a.apk[span_17](start_span)[span_17](end_span)
   - pm install-write SESSION_ID 3 /sdcard/pubgflash/obbassets.apk[span_18](start_span)[span_18](end_span)
   - pm install-commit SESSION_ID

7. Selesai! Aplikasi PUBGM FLASH siap dimainkan[span_19](start_span)[span_19](end_span).

--------------------------------------------------------------------
❓ FAQ & Catatan Tambahan
--------------------------------------------------------------------
Q: Apakah perlu memindahkan file OBB secara manual ke /sdcard/Android/obb/?
A: Tidak perlu. Seluruh aset OBB sudah dibungkus di dalam file obbassets.apk dan akan otomatis dipasang oleh sistem Android saat perintah install-multiple dijalankan[span_20](start_span)[span_20](end_span).

Q: Mengapa pesan "File Not Found" muncul di Brevent?
A: Pastikan direktori folder di memori internal sesuai dengan perintah (/sdcard/pubgflash/) dan nama file APK tidak salah ketik[span_21](start_span)[span_21](end_span).

--------------------------------------------------------------------
⚠️ Disclaimer
--------------------------------------------------------------------
Proyek dan panduan ini dibuat khusus untuk keperluan edukasi dan pengujian teknis pada build Early Access PUBGM FLASH. Seluruh hak cipta milik Tencent Games / Krafton.
