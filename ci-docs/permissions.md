---
title: Uruskan keizinan pengguna
description: Ketahui mengenai keizinan dan peranan pengguna.
ms.date: 02/09/2022
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
ms.openlocfilehash: 74c7ff7cda8431c04dd34713becefa7e346331b4
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740914"
---
# <a name="user-permissions"></a>Keizinan pengguna

Halaman **Keizinan** ialah tempat anda akan menyediakan peranan dan keizinan untuk menggunakan Wawasan Pelanggan.

Anda perlu mempunyai keizinan pentadbir untuk melihat halaman. Untuk mencapai halaman keizinan, pergi ke **Pengguna Keselamatan** > **Pentadbir** > **·**.

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
- Lengkapkan ***Penyatuan** Data yang menghasilkan entiti profil pelanggan yang bersatu.
- Takrif **Perhubungan** dan **Aktiviti**.
- Cipta segmen menggunakan halaman **Segmen**.
- Cipta ukuran menggunakan halaman **Ukuran**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk pengayaan pihak pertama sahaja).
- Urus dan cipta eksport berdasarkan sambungan yang dikongsi dengan penyumbang. [Ketahui lebih lanjut tentang cara pentadbir membenarkan penyumbang menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Pentadbiran

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
- [Memperuntukkan pemilikan](manage-environments.md#change-the-owner-of-an-environment) persekitaran kepada pentadbir lain.

## <a name="admin-owner"></a>Pentadbir (pemilik)

- Semua keizinan tersedia untuk Pentadbir.
- [Tetapkan semula dan padamkan](manage-environments.md#reset-an-existing-environment) persekitaran.

## <a name="assign-roles-and-permissions"></a>Tugaskan peranan dan keizinan

1. Pergi ke **> Keselamatan** > **Pentadbir****Pengguna***.

1. Pilih **Tambah pengguna** untuk membuka anak tetingkap **Tambah/Edit keizinan**.

1. Gunakan medan **Cari** untuk mencari pengguna atau kumpulan Azure Active Directory yang keizinannya anda mahu laraskan. Pilih **Peranan** untuk ditugaskan kepada pengguna atau kumpulan tersebut.

1. Pilih **Simpan**. Persekitaran semasa akan dikongsi secara automatik dengan pengguna atau ahli kumpulan yang mana keizinan anda telah berubah. Pengguna boleh mengakses aplikasi Customer Insights dan bekerja mengikut peranan tertentu mereka.

## <a name="view-current-permissions"></a>Lihat keizinan semasa

Pergi ke **Pengguna** > **Keselamatan** > **Pentadbir** untuk melihat tugasan peranan yang sedang aktif.

- Lajur **Jenis** menentukan pengguna tunggal, kumpulan, atau aplikasi. Sistem menyokong pengguna atau kumpulan individu.
- Peranan ditentukan di bawah lajur **Peranan**.
- Sila sebarang tajuk lajur untuk mengisihkan hasil mengikut nilai lajur tersebut.
- Gunakan medan **Cari** di bahagian atas halaman untuk mengesan pengguna tertentu.


[!INCLUDE [footer-include](includes/footer-banner.md)]
