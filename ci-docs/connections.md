---
title: Gambaran keseluruhan sambungan (pratonton)
description: Sambungan ke perkhidmatan lain daripada Customer Insights.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: a8b4b8a9bdcf7cf43c47a67d547405dd20dad60d
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082097"
---
# <a name="connections-preview-overview"></a>Gambaran keseluruhan sambungan (pratonton)

Sambungan adalah kunci untuk mendayakan perkongsian data ke dan daripada Customer Insights. Setiap sambungan mewujudkan perkongsian data dengan perkhidmatan tertentu. Sambungan adalah asas untuk [mengkonfigurasikan pengayaan pihak ketiga](enrichment-hub.md) dan [mengkonfigurasi eksport](export-destinations.md). Sambungan yang sama boleh digunakan beberapa kali. Sebagai contoh, satu sambungan ke Dynamics 365 Marketing berfungsi untuk berbilang eksport dan satu sambungan Leadspace boleh digunakan untuk beberapa pengayaan.

Pergi ke **Pentadbir** > **Sambungan** untuk mencipta dan melihat sambungan.

Tab **Sambungan** menunjukkan anda semua sambungan aktif. Senarai menunjukkan baris untuk setiap sambungan.

Dapatkan gambaran keseluruhan pantas, perihalan, dan ketahui perkara yang boleh anda lakukan dengan setiap pilihan kebolehsambungan pad tab **Temui**.

## <a name="exports"></a>Eksport

Hanya pentadbir boleh mengkonfigurasikan sambungan baharu, tetapi mereka boleh memberikan akses kepada penyumbang untuk menggunakan sambungan yang sedia ada. Pentadbir mengawal tempat data boleh pergi, penyumbang mentakrifkan muatan dan kekerapan untuk memenuhi keperluan mereka. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Pengayaan

Hanya pentadbir boleh mengkonfigurasikan sambungan baharu tetapi sambungan yang dicipta sentiasa tersedia untuk pentadbir dan penyumbang. Pentadbir mengurus kelayakan dan memberi keizinan kepada pemindahan data. Sambungan boleh digunakan oleh pentadbir dan penyumbang untuk pengayaan.

## <a name="add-a-new-connection"></a>Tambah sambungan baharu

Untuk menambah sambungan, anda perlu mempunyai [keizinan pentadbir](permissions.md). Jika anda bersambung ke perkhidmatan Microsoft lain, kami menganggap kedua-dua perkhidmatan berada dalam organisasi yang sama.

1. Pergi ke **Pentadbir** > **Sambungan (pratonton)**.

1. Pergi ke tab **Sambungan**.

1. Pilih **Tambah sambungan** untuk mencipta sambungan baharu. Pilih daripada menu juntai bawah jenis sambungan yang mahu anda cipta.

1. Dalam anak tetingkap **Sediakan sambungan**, berikan butiran yang diperlukan.
   1. **Nama paparan** dan jenis sambungan yang menerangkan sambungan. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan ini.
   1. Medan yang tepat bergantung pada perkhidmatan yang anda sambungkan. Anda boleh mengetahui tentang butiran jenis sambungan khusus dalam artikel mengenai perkhidmatan sasaran.
   1. Jika anda [gunakan Key Vault anda sendiri](use-azure-key-vault.md) untuk menyimpan rahsia, aktifkan **Gunakan Key Vault** dan pilih rahsia daripada senarai.

1. Untuk mencipta sambungan, pilih **Simpan**.

Anda juga boleh memilih **Sediakan** pada jubin pada tab **Temui**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Benarkan penyumbang untuk menggunakan sambungan untuk eksport

Apabila menyediakan atau mengedit sambungan eksport, anda memilih pengguna yang dibenarkan untuk menggunakan sambungan khusus ini untuk mentakrifkan [eksport](export-destinations.md). Secara lalai, sambungan tersedia kepada pengguna yang mempunyai peranan pentadbir. Anda boleh mengubah tetapan ini di bawah **Pilih individu yang boleh menggunakan sambungan ini** dan membenarkan pengguna yang mempunyai peranan penyumbang untuk menggunakan sambungan ini.

- Penyumbang tidak akan dapat melihat atau mengedit sambungan. Mereka hanya akan melihat nama paparan dan jenisnya semasa membuat eksport.
- Dengan berkongsi sambungan, anda membenarkan penyumbang untuk menggunakan sambungan. Penyumbang akan melihat sambungan dikongsi apabila mereka menyediakan eksport. Mereka boleh mengurus setiap eksport yang menggunakan sambungan khusus ini.
- Anda boleh mengubah tetapan ini di samping mengekalkan eksport yang telah ditakrifkan oleh penyumbang.

## <a name="edit-a-connection"></a>Edit sambungan

1. Pergi ke **Pentadbir** > **Sambungan (pratonton)**.

1. Pergi ke tab **Sambungan**.

1. Pilih elipsis menegak (&vellip;) untuk sambungan yang anda mahu edit.

1. Pilih **Edit**.

1. Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.

## <a name="remove-a-connection"></a>Alih keluar sambungan

Jika sambungan yang anda alih keluar digunakan oleh pengayaan atau eksport, anda perlu melepaskan atau mengalih keluarnya terlebih dahulu. Dialog yang dialih keluar akan membimbing anda kepada pengayaan atau eksport yang berkaitan.

Pengayaan dan eksport yang dialih menjadi tidak aktif. Anda mengaktifkan semula dengan menambah sambungan lain kepadanya pada halaman [Pengayaan](enrichment-hub.md) atau [Eksport](export-destinations.md).

1. Pergi ke **Pentadbir** > **Sambungan (pratonton)**.

1. Pergi ke tab **Sambungan**.

1. Pilih elipsis menegak (&vellip;) untuk sambungan yang anda ingin alih keluar.

1. Pilih **Alih keluar** daripada menu juntai bawah. Dialog pengesahan muncul.

   1. Jika terdapat pengayaan atau eksport menggunakan sambungan ini, pilih butang untuk melihat apa yang menggunakan sambungan.
      - **Eksport:** Anda boleh memilih sama ada untuk mengalih keluar atau nyahsambung eksport supaya dapat mengalih keluar sambungan. Untuk memutuskan sambungan eksport, pentadbir boleh menggunakan tindakan **Putuskan sambungan**. Tindakan ini tersedia untuk individu dan berbilang eksport terpilih. Dengan memutuskan sambungan, anda mengekalkan konfigurasi eksport, tetapi ia tidak akan berjalan sehingga sambungan yang lain ditambah padanya.
      - **Pengayaan:** Anda boleh memilih sama ada untuk mengalih keluar atau menyahaktif pengayaan supaya dapat mengalih keluar sambungan.
   1. Sebaik sahaja sambungan tidak mempunyai kebergantungan, pergi kembali ke **Pentadbir** > **Sambungan** dan cuba alih keluar sambungan semula.

1. Untuk mengesahkan pemadaman, pilih **Alih keluar**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Sediakan sambungan dengan rahsia yang diuruskan oleh Key Vault anda sendiri

Sesetengah sambungan memerlukan rahsia seperti kekunci API atau kata laluan. Sesetengah sambungan menyokong rahsia yang disimpan dalam Key Vault anda sendiri. Ketahui lebih lanjut tentang sambungan yang disokong dan cara menyediakan peti [besi kunci anda sendiri untuk Wawasan Pelanggan](use-azure-key-vault.md).
