# 🌀 XyraShell (X77 Engine)

> **Advanced PHP 8.5 Web Shell for Educational & Security Auditing Purposes**

![Version](https://img.shields.io/badge/version-7.0-purple)
![License](https://img.shields.io/badge/license-MIT-blue)
![PHP](https://img.shields.io/badge/PHP-8.5.5-cyan)
![Security](https://img.shields.io/badge/Security-CSRF+RateLimit-red)

**XyraShell** (berbasis engine X77 v7) adalah web shell berbasis PHP modern yang dioptimalkan untuk **PHP 8.5.5**. Tool ini dirancang khusus untuk keperluan **Educational Cybersecurity Lab**, **Red Team Simulation**, dan **Server Maintenance Audit**.

Dengan antarmuka Single Page Application (SPA) yang responsif, XyraShell menyediakan fitur lengkap mulai dari manajemen file, terminal emulator multi-tab, analisis kerentanan real-time (CVE NVD API), hingga forensik log dan audit keamanan sistem.

---

## ⚠️ DISCLAIMER & LEGAL WARNING

> **PENTING: BACA SEBELUM MENGGUNAKAN**

1.  **Tujuan Edukasi:** Tool ini dikembangkan dan didistribusikan **HANYA** untuk tujuan pendidikan, penelitian keamanan, dan pengujian penetrasi yang sah (*authorized penetration testing*).
2.  **Tanggung Jawab Pengguna:** Penulis dan Organisasi **TIDAK BERTANGGUNG JAWAB** atas segala kerusakan, kehilangan data, atau tindakan ilegal yang dilakukan menggunakan tool ini.
3.  **Ilegalitas:** Menggunakan tool ini pada server, jaringan, atau sistem milik orang lain **tanpa izin tertulis** adalah tindakan **ILEGAL** dan melanggar undang-undang siber (termasuk UU ITE di Indonesia dan CFAA di AS).
4.  **Kompatibilitas:** Tool ini membutuhkan **PHP 8.5.5** atau lebih baru untuk memastikan kompatibilitas fungsi dan keamanan terbaru.

**Dengan menggunakan tool ini, Anda menyetujui bahwa Anda bertanggung jawab penuh atas tindakan Anda.**

---

## 🚀 Fitur Utama

### 🖥️ Advanced Terminal Emulator
*   **Multi-Tab & Split Screen:** Jalankan multiple command secara paralel dalam satu sesi.
*   **Autocomplete & History:** Support tab-completion cerdas dan navigasi history.
*   **ANSI Color Support:** Output warna dari command Linux tetap terjaga dengan sempurna.
*   **Command Palette:** Akses cepat command via `Ctrl+P`.
*   **Ghost Text:** Sugesti command berdasarkan history pengetikan.
*   **Queue System:** Antrian eksekusi command otomatis.

### 📁 File Manager Pro
*   **Tree View & Grid/List View:** Navigasi file yang fleksibel dengan preview gambar.
*   **Bulk Operations:** Hapus atau chmod banyak file sekaligus.
*   **Zip/Unzip:** Kompresi dan ekstrak arsip langsung dari browser.
*   **Code Editor:** Edit file dengan syntax highlighting, auto-save, find/replace, dan multi-tab.
*   **Permission Auditor:** Deteksi file/directory dengan permission berbahaya (777, world-writable).

### 🛡️ Security & Forensics Tools
*   **Log Analyzer:** Deteksi suspicious activity (SQLi, XSS, Scanner, Shell Inject) di access log.
*   **Brute Force Detector:** Analisis auth log untuk mendeteksi serangan brute force.
*   **HTTP Header Checker:** Audit security headers (HSTS, CSP, X-Frame-Options) dan berikan skor keamanan.
*   **SSL/TLS Checker:** Validitas sertifikat SSL dan masa berlaku.
*   **PHP Security Checklist:** Cek konfigurasi `php.ini` yang tidak aman pada PHP 8.5.5.
*   **Permission Audit:** Scan directory untuk mencari file dengan permission riskan.

### 📋 CVE Intelligence (Real-time NVD API)
*   **CVE Lookup:** Cari detail vulnerabilitas spesifik via ID (contoh: CVE-2024-1234) langsung dari NIST NVD.
*   **CVE Search:** Cari CVE berdasarkan keyword, tahun, dan severity.
*   **Recent CVEs:** Lihat 20 CVE terbaru yang diterbitkan oleh NIST secara real-time.
*   **Severity Highlighting:** Warna otomatis berdasarkan tingkat keparahan (Critical, High, Medium, Low).

### 🌐 Network & OSINT
*   **Whois Lookup:** Informasi domain.
*   **Reverse IP:** Mencari hostname dari IP.
*   **Port Scanner:** TCP Connect scan untuk port umum.
*   **CMS Detector:** Deteksi WordPress, Joomla, Drupal, Laravel, dll.

### 🔐 Cryptography & Hashing
*   **Hash Generator:** MD5, SHA1, SHA256, SHA512, SHA384, RIPEMD160, CRC32B.
*   **Hash Identifier:** Mendeteksi jenis hash dari string input.
*   **String Tools:** Base64, URL Encode/Decode, Hex, ROT13, HTML Entities, Reverse, dll.

### 🎨 UI/UX Modern (Hacking Aesthetic)
*   **Themes:** Dark, Midnight, Forest, Ember, Light, dan Custom Color Picker.
*   **Responsive:** Bisa digunakan di mobile (dengan keterbatasan).
*   **Loading Animation:** Animasi startup ala cyberpunk.
*   **Toast Notifications:** Notifikasi non-intrusif untuk setiap aksi.

---

## 📋 Prasyarat

*   **Web Server:** Apache, Nginx, atau IIS.
*   **PHP Version:** **>= 8.5.5** (Wajib untuk kompatibilitas penuh).
*   **Extensions:** `proc_open`, `exec`, `shell_exec`, `openssl`, `zip` harus aktif.
*   **Permissions:** User web server harus memiliki hak baca/tulis pada direktori target.

---

## 🛠️ Instalasi & Penggunaan

### 1. Deploy
Upload file `xyrashell.php` (atau nama file yang sudah di-obfuscate) ke direktori web server target.

### 2. Akses
Buka browser dan akses URL: http://target-domain.com/path/to/xyrashell.php


### 3. Login
Gunakan kredensial default (**SEGERA GANTI DI KODE SUMBER**):
*   **Username:** `admin` | **Password:** `admin123`
*   **Username:** `lab` | **Password:** `cyber2024`

### 4. Konfigurasi Keamanan (Wajib)
Sebelum deploy di lingkungan produksi/lab:
1.  Buka file `xyrashell.php`.
2.  Cari array `$USERS` dan ganti password default dengan hash baru:
    ```php
    $USERS = [
        'admin' => password_hash('PASSWORD_BARU_ANDA', PASSWORD_DEFAULT),
    ];
    ```
3.  (Opsional) Isi `$IP_WHITELIST` dengan IP statis Anda untuk membatasi akses:
    ```php
    $IP_WHITELIST = ['192.168.1.100', '10.0.0.5']; 
    ```

---

## 🛡️ Best Practices untuk Red Team / Auditor

1.  **Obfuscation:** Pertimbangkan untuk mengobfuscate kode PHP sebelum upload untuk menghindari deteksi oleh WAF/IDS dasar.
2.  **Rename File:** Jangan gunakan nama `shell.php` atau `backdoor.php`. Gunakan nama yang tidak mencurigakan seperti `config_update.php` atau `theme_editor.php`.
3.  **Hapus Setelah Pakai:** Segera hapus file dari server setelah audit selesai untuk mengurangi jejak (footprint).
4.  **Log Cleaning:** Gunakan fitur internal untuk membersihkan log akses jika diperlukan (hati-hati, ini bisa memicu alert SIEM).
5.  **Session Security:** Tool ini sudah dilengkapi CSRF protection, Rate Limiting, dan Session Fingerprinting. Jangan share session ID Anda.

---

## 🤝 Kontribusi

Kontribusi dibuka untuk fitur keamanan tambahan dan perbaikan bug. Silakan fork repository dan buat Pull Request.

---

## 📄 Lisensi

Project ini dilisensikan di bawah **MIT License**. Lihat file `LICENSE` untuk detail lebih lanjut.

---

**Dikembangkan oleh:** [Xyra-Company/Xyra77]
**Versi:** 7.0
**PHP Requirement:** 8.5.5+
**Last Update:** Mei 2026
