<p align="center">

  ![Orengefox For Marble](assets/social-preview.png)

</p>

<p align="center">
  <img src="https://img.shields.io/badge/OrangeFox-Recovery-FF6E1E?style=for-the-badge&logo=android&logoColor=white" />
  <img src="https://img.shields.io/badge/Device-marble-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-Apache%202.0-green?style=for-the-badge" />
</p>

<h1 align="center">OrangeFox Recovery — For Marble</h1>
<p align="center">
Build otomatis <b>OrangeFox Recovery Project (OFRP)</b> untuk <b>POCO F5</b> / <b>Redmi Note 12 Turbo</b> (<code>marble</code>) lewat GitHub Actions
</p>

---

## 📖 Tentang repo ini

Repo ini **tidak berisi device tree**. Isinya hanya workflow GitHub Actions yang:

1. Sync source OrangeFox `fox_12.1` dari [OrangeFox sync](https://gitlab.com/OrangeFox/sync)
2. Clone device tree dari **[Ctapchuk/android_device_xiaomi_marble-OFRP](https://github.com/Ctapchuk/android_device_xiaomi_marble-OFRP)** (branch `fox_12.1`)
3. Build recovery, lalu upload **file ZIP installer OrangeFox** ke Releases

| Market Name | Codename |
| --- | --- |
| POCO F5 / Redmi Note 12 Turbo | `marble` |

> ℹ️ ZIP hasil build hanya mengenali codename `marble`. Varian `marblein` (POCO F5 India) belum didukung oleh ZIP ini.

## 📂 Struktur repo

```
.
├── .github/workflows/OrengeFox.yml   # workflow build
├── patches/patch-vendor-twrp-fox_12.1.diff   # patch vendor/twrp (hilang di repo sync upstream)
├── assets/social-preview.png
└── README.md
```

## 🔨 Cara build

1. Buka tab **Actions** → **Recovery OFOX Build (fox_12.1) — marble**
2. Klik **Run workflow** (default input sudah benar untuk `marble`)
3. Tunggu sekitar 40–60 menit
4. Ambil file `OrangeFox-...-marble.zip` di tab **Releases**

Hanya pemilik repo yang bisa menjalankan workflow ini.

## 📥 Instalasi

Release hanya berisi **ZIP installer**. Image `.img` tidak dirilis.

1. Download `OrangeFox-...-marble.zip` dari Releases
2. Boot ke recovery yang sudah ada di perangkat
3. Flash ZIP lewat menu install
4. Reboot ke recovery untuk mengecek hasilnya

> ⚠️ Pastikan bootloader sudah unlocked. Build ini memakai kernel ROM yang aktif (`boot_a`/`boot_b`), jadi image-nya tidak berisi kernel sendiri. Jangan flash image langsung dengan `fastboot flash recovery`.

> 🧪 Status: hasil build belum diuji di semua ROM. Backup dulu sebelum flash.

## 🙏 Credits

- **OrangeFox Recovery Project** — https://orangefox.tech
- Device tree: [Ctapchuk/android_device_xiaomi_marble-OFRP](https://github.com/Ctapchuk/android_device_xiaomi_marble-OFRP)
- Komunitas TWRP/OFRP untuk perangkat Xiaomi `marble`

## ⚠️ Disclaimer

Flash custom recovery bisa membatalkan garansi dan menyebabkan bootloop atau brick jika salah langkah. Gunakan dengan risiko sendiri. Pembuat repo ini tidak bertanggung jawab atas kerusakan perangkat.

## 📄 Lisensi

Apache License 2.0, mengikuti lisensi upstream OrangeFox/TWRP/AOSP. Tambahkan file `LICENSE` di root repo agar badge di atas sesuai.
