# 🛡️ LoJax Malware Overview

**UEFI Bootkit – Advanced Persistent Threat (APT)**
Referensi lengkap teknis tersedia pada dokumen: **ESET-LoJax.pdf**

---

## 📌 Ringkasan

**LoJax** adalah malware kelas **UEFI bootkit** yang dikembangkan dan digunakan oleh grup *APT28 / Fancy Bear* dalam operasi spionase tingkat tinggi.

Malware ini dikenal sebagai:

* **UEFI rootkit pertama yang ditemukan aktif digunakan di dunia nyata**
* **Sangat persisten**, tetap hidup meskipun:

  * Windows di-install ulang
  * Hard disk diganti
  * Sistem di-format ulang
* **Beroperasi di level firmware**, lebih tinggi dari kernel OS

Dokumen lengkap mengenai analisis teknis LoJax dapat ditemukan pada:
📄 **ESET-LoJax.pdf**

---

## 🧠 Apa itu LoJax?

LoJax adalah malware yang menargetkan firmware **UEFI** (Unified Extensible Firmware Interface) melalui manipulasi chip SPI Flash pada motherboard.

### Karakteristik:

* Bootkit level firmware
* Persisten melewati reinstall OS
* Digunakan oleh aktor negara (nation-state APT)
* Tidak bisa dihapus dengan antivirus konvensional

---

## ⚙️ Bagaimana LoJax Bekerja?

Berikut mekanisme kerja umum LoJax:

1. **Menulis modul jahat ke firmware UEFI**
   (menggantikan modul firmware legal)

2. **Menjalankan code sebelum OS booting**
   → memberikan akses penuh ke sistem

3. **Men-download dan menjalankan backdoor lain**
   untuk kontrol jarak jauh

4. **Persisten di SPI Flash** sehingga sulit dihapus

Detail teknis lengkap dapat dipelajari melalui:
📄 *ESET-LoJax.pdf*

---

## ⚠️ Dampak Keamanan

* Ancaman tingkat **kritikal** (firmware-level attack)
* Menyebabkan **kompromi total sistem**
* Berpotensi:

  * Mengambil alih OS
  * Mencuri data
  * Menanamkan backdoor permanen
  * Memodifikasi bootchain
  * Menonaktifkan Secure Boot

---

## 🛡️ Cara Deteksi LoJax

1. **Cek firmware integrity**

   * Menggunakan vendor BIOS integrity checker
   * Bandingkan hash SPI flash dengan firmware resmi

2. **Gunakan tools ESET UEFI Scanner**

3. **Analisis anomali boot chain**

   * Perubahan pada DXE driver
   * Modul UEFI yang tidak sesuai vendor

4. **Cek file Windows sistem berikut:**

   * `rpcnetp.exe`
   * `rpcnet.dll`
     (komponen digunakan oleh LoJack/Computrace versi modifikasi)

Untuk metode lengkap, lihat:
📄 **ESET-LoJax.pdf – Bagian: Detection & Analysis**

---

## 🔧 Cara Menghapus LoJax

Karena LoJax berada di firmware, metode penghapusan adalah:

### 1. **Reflash BIOS/UEFI** (Paling efektif)

* Download firmware resmi dari vendor
* Flash ulang menggunakan utilitas resmi

### 2. **SPI Flash Recovery**

* Menggunakan programmer hardware (jika firmware rusak)

### 3. **Clear Secure Boot keys** (opsional)

### Tidak dapat dihapus dengan:

❌ Install ulang Windows
❌ Format hard disk
❌ Mengganti hard disk
❌ Antivirus standar

Detail teknik pembersihan firmware ada di:
📄 *ESET-LoJax.pdf – Chapter: Remediation*

---

## 🛑 Cara Mencegah Infeksi LoJax

* Aktifkan **Secure Boot**
* Update firmware BIOS secara berkala
* Gunakan OS dengan proteksi bootchain (Windows 10+ atau Linux modern)
* Jangan instal driver atau program dari sumber tidak tepercaya
* Gunakan AV/EDR dengan modul **UEFI Scanner**

---

## 📚 Referensi

Semua penjelasan teknis mendalam tersedia dalam dokumen:
📄 **ESET-LoJax.pdf**
[Document]()

---

## 📝 Lisensi

Dokumen ini bersifat informatif dan hanya dapat digunakan untuk keperluan "edukasi atau penelitian keamanan".
