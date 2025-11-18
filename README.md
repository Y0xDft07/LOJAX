# 🦠 **Apa itu LoJax?**

**LoJax adalah malware jenis UEFI rootkit/bootkit** yang digunakan oleh kelompok hacker negara (*APT28 / Fancy Bear*) untuk menyerang sistem Windows.

Ini sangat berbahaya karena:

### ✅ **Menginfeksi UEFI / BIOS**

Artinya LoJax tertanam **di firmware motherboard**, bukan hanya di Windows.

### ✅ **Tidak hilang meskipun Windows di-install ulang**

Karena berada di BIOS, reinstall OS tidak menghapusnya.

### ✅ **Bisa bertahan setelah format hard disk**

Firmware tetap terinfeksi walaupun HDD/SSD diganti.

### ✅ **Digunakan untuk spionase**

Dipakai oleh grup peretas Rusia untuk serangan intelijen tingkat tinggi.

---

# 🔍 **Bagaimana LoJax Bekerja?**

1. Menyuntikkan dirinya ke **UEFI firmware** (flash SPI chip motherboard).
2. Menginstal driver jahat sehingga malware tetap hidup sebelum OS booting.
3. Setelah sistem menyala, ia men-download malware lain (C2 communication).
4. Memberikan akses penuh kepada penyerang.

---

# ⚠️ **Mengapa LoJax Berbahaya?**

Karena:

✔ Tidak bisa dimusnahkan dengan antivirus biasa
✔ Tidak hilang dengan install ulang
✔ Tidak hilang dengan mengganti hard disk
✔ Tingkat akses **lebih tinggi dari administrator OS**

Ini level malware **paling berbahaya**, kategori "firmware persistence".

---

# 🔐 **Bagaimana Cara Menghapus LoJax?**

Hanya bisa dilakukan dengan:

### 🔧 1. Reflash BIOS/UEFI

Menggunakan file firmware asli dari vendor laptop/motherboard.

### 🧹 2. Clear CMOS + Flash SPI Recovery

Jika SPI chip sudah dimodifikasi.

### 💻 3. Menggunakan Firmware Update via vendor

Lenovo, Acer, Asus memiliki tools update resmi.

### ❌ Anti-virus & format hard disk tidak akan membantu.

---

# 🛡 **Bagaimana Cara Mencegah LoJax?**

* Aktifkan **Secure Boot**
* Update BIOS secara berkala
* Gunakan Windows Defender Core Isolation
* Jangan install driver/software tidak resmi
* Gunakan firmware anti-tamper jika tersedia

---

# 📌 Document

[Untuk lebih detail nya]()
