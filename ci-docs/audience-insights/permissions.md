---
title: Uruskan keizinan pengguna
description: Ketahui mengenai keizinan dan peranan pengguna.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760384"
---
# <a name="user-permissions"></a>Keizinan pengguna

Halaman **Keizinan** ialah tempat anda akan menyediakan peranan dan keizinan untuk menggunakan wawasan khalayak.

Anda perlu mempunyai keizinan pentadbir untuk melihat halaman. Untuk mengakses halaman keizinan dalam wawasan khalayak, pergi ke **Pentadbir** > **Keizinan**.

Terdapat tiga jenis peranan:

## <a name="viewer"></a>Penonton

- Teroka wawasan dan bahagian dalam halaman **Laman Utama** dan **Bahagian**.
- Cari dan tapis profil pelanggan menggunakan halaman **Pelanggan**. Medan mesti boleh dicari.
- Lihat dan terokai halaman **Pengayaan**.
- Teroka dan eksport entiti menggunakan halaman **Entiti**.
- Lihat status proses sistem menggunakan halaman **Sistem**.
- Lihat eksport dalam halaman **Eksport**.
- Pasang dan gunakan papan pemuka **Power BI Customer Insights**.

## <a name="contributor"></a>Penyumbang

- Semua keizinan tersedia untuk Penonton.
- Muatkan dan ubah data menggunakan halaman **Sumber data**.
- Lengkapkan bahagian *Penyatuan Data* (**Peta**, **Padan**, dan **Gabung**) yang menyebabkan entiti profil pelanggan digabungkan.
- Takrif **Perhubungan** dan **Aktiviti**.
- Cipta segmen menggunakan halaman **Segmen**.
- Cipta ukuran menggunakan halaman **Ukuran**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk pengayaan pihak pertama sahaja).
- Urus dan cipta eksport berdasarkan sambungan yang dikongsi dengan penyumbang. [Ketahui lebih lanjut tentang cara pentadbir membenarkan penyumbang menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="administrator"></a>Pentadbir

- Semua keizinan tersedia untuk Penyumbang.
- Tetapan ubah pada halaman **Sistem**, termasuk bahasa bekerja dan jadual segar semula untuk proses sistem anda.
- Lihat dan tambah keizinan menggunakan halaman **Keizinan**.
- Tetapkan takrifan carian dan penapis untuk halaman Pelanggan menggunakan halaman **Carian & tapis indeks** (boleh diakses melalui halaman **Pelanggan**).
- Uruskan sambungan dan benarkannya untuk peranan pengguna lain pada halaman **Sambungan**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk semua pengayaan).
- Urus dan cipta eksport pada halaman **Eksport**.
- Pasang dan guna **Tambahan Kad Pelanggan**.
- Tambah dan gunakan **Power Apps penyambung**.
- Mendayakan penggunaan [Customer Insights API](apis.md).

## <a name="assign-roles-and-permissions"></a>Tugaskan peranan dan keizinan

1. Dalam Insights khalayak, pergi ke **Pentadbir** > **Keizinan**.

1. Pilih **Tambah pengguna** untuk membuka anak tetingkap **Tambah/Edit keizinan**.

1. Gunakan medan **Cari** untuk mencari pengguna atau kumpulan Azure Active Directory yang keizinannya anda mahu laraskan. Pilih **Peranan** untuk ditugaskan kepada pengguna atau kumpulan tersebut.

1. Pilih **Simpan**. Persekitaran semasa akan dikongsi secara automatik dengan pengguna atau ahli kumpulan yang mana keizinan anda telah berubah. Pengguna boleh mengakses aplikasi Customer Insights dan bekerja mengikut peranan tertentu mereka.

## <a name="view-current-permissions"></a>Lihat keizinan semasa

Dalam wawasan khalayak, pergi ke **Pentadbir** > **Keizinan** untuk melihat tugasan peranan yang sedang aktif.

- Lajur **Jenis** menentukan pengguna tunggal, kumpulan, atau aplikasi. Sistem menyokong pengguna atau kumpulan individu.
- Peranan ditentukan di bawah lajur **Peranan**.
- Sila sebarang tajuk lajur untuk mengisihkan hasil mengikut nilai lajur tersebut.
- Gunakan medan **Cari** di bahagian atas halaman untuk mengesan pengguna tertentu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
