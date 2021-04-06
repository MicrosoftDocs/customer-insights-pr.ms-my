---
title: Uruskan keizinan pengguna
description: Ketahui mengenai keizinan dan peranan pengguna.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595713"
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
- Eksport segmen dari halaman **Segmen**.
- Pasang dan gunakan papan pemuka **Power BI Customer Insights**.

## <a name="contributor"></a>Penyumbang

- Semua keizinan tersedia untuk Penonton.
- Muatkan dan ubah data menggunakan halaman **Sumber data**.
- Lengkapkan bahagian *Penyatuan Data* (**Peta**, **Padan**, dan **Gabung**) yang menyebabkan entiti profil pelanggan digabungkan.
- Takrif **Perhubungan** dan **Aktiviti**.
- Cipta segmen menggunakan halaman **Segmen**.
- Cipta ukuran menggunakan halaman **Ukuran**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk pengayaan pihak pertama sahaja).

## <a name="administrator"></a>Pentadbir

- Semua keizinan tersedia untuk Penyumbang.
- Tetapan ubah pada halaman **Sistem**, termasuk bahasa bekerja dan jadual segar semula untuk proses sistem anda.
- Lihat dan tambah keizinan menggunakan halaman **Keizinan**.
- Tetapkan takrifan carian dan penapis untuk halaman Pelanggan menggunakan halaman **Carian & tapis indeks** (boleh diakses melalui halaman **Pelanggan**).
- Takrifkan destinasi segmen Dynamics 365 Sales menggunakan halaman **Destinasi eksport**.
- Urus konfigurasi dan perkayakan profil pelanggan daripada halaman **Pengayaan** (untuk semua pengayaan).
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