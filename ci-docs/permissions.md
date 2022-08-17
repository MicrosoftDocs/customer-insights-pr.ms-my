---
title: Tugaskan keizinan pengguna
description: Ketahui mengenai keizinan dan peranan pengguna.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245430"
---
# <a name="assign-user-permissions"></a>Tugaskan keizinan pengguna

Capaian kepada Wawasan Pelanggan adalah terhad kepada pengguna dalam organisasi anda yang ditambahkan pada aplikasi oleh pentadbir. Pentadbir boleh menambah, mengedit atau mengalih keluar pengguna. Pengguna boleh menjadi pengguna, kumpulan atau aplikasi tunggal. Terdapat tiga jenis peranan yang boleh dimiliki oleh pengguna:

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
- Penyatuan **Data Lengkap** yang menghasilkan entiti profil pelanggan yang bersatu.
- Takrif **Perhubungan** dan **Aktiviti**.
- Cipta segmen menggunakan halaman **Segmen**.
- Cipta ukuran menggunakan halaman **Ukuran**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk pengayaan pihak pertama sahaja).
- Urus dan cipta eksport berdasarkan [sambungan yang dikongsi dengan penyumbang](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Pentadbiran

- Semua keizinan tersedia untuk Penyumbang.
- Tukar seting pada **halaman Sistem**, termasuk bahasa kerja, segar semula jadual untuk proses sistem anda dan mengeksport log diagnostik.
- Tukar seting pada **halaman Keselamatan**, termasuk pengguna, kekunci API, pautan peribadi dan peti besi kunci.
- Tetapkan takrifan carian dan penapis untuk halaman Pelanggan menggunakan halaman **Carian & tapis indeks** (boleh diakses melalui halaman **Pelanggan**).
- Uruskan sambungan dan benarkannya untuk peranan pengguna lain pada halaman **Sambungan**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk semua pengayaan).
- Urus dan cipta eksport pada halaman **Eksport**.
- Pasang dan guna **Tambahan Kad Pelanggan**.
- Tambah dan gunakan **Power Apps penyambung**.
- Mendayakan penggunaan [Customer Insights API](apis.md).
- [Memperuntukkan pemilikan](manage-environments.md#change-the-owner-of-an-environment) persekitaran kepada pentadbir lain.

## <a name="admin-owner"></a>Pentadbir (pemilik)

- Semua keizinan tersedia kepada Pentadbir.
- [Tetapkan semula dan padamkan](manage-environments.md#reset-an-existing-environment-preview) persekitaran.

## <a name="add-users"></a>Tambah pengguna

1. Pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **Pengguna**.

1. Pilih **Tambah pengguna** untuk membuka anak tetingkap **Tambah/Edit keizinan**.

1. **Gunakan medan Carian** untuk mencari pengguna atau kumpulan yang Azure Active Directory anda ingin tambah. Pilih **Peranan** untuk ditugaskan kepada pengguna atau kumpulan tersebut.

1. Pilih **Simpan**. Persekitaran semasa dikongsi secara automatik dengan pengguna atau ahli kumpulan. Pengguna boleh mengakses aplikasi Customer Insights dan bekerja mengikut peranan tertentu mereka.

## <a name="view-current-permissions"></a>Lihat keizinan semasa

Pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **Pengguna** untuk melihat senarai pengguna aktif dan tugasan peranan mereka. Anda boleh mengisih senarai pengguna mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari pengguna tertentu.

## <a name="manage-current-users"></a>Uruskan pengguna semasa

Pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **Pengguna**. Anda boleh mengisih senarai pengguna mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari pengguna yang anda ingin uruskan.

Pilih pengguna untuk melihat tindakan yang tersedia.

- **Edit** untuk mengedit peranan pengguna dalam Wawasan Pelanggan. Pilih **Simpan** untuk mengesahkan perubahan.
- **Alih keluar** untuk mengalih keluar pengguna daripada mempunyai akses kepada Wawasan Pelanggan. Pilih **Padam** untuk mengesahkan pemadaman.

[!INCLUDE [footer-include](includes/footer-banner.md)]
