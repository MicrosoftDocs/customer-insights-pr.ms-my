---
title: Gambaran keseluruhan sambungan (pratonton)
description: Sambungan ke perkhidmatan lain daripada Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245522"
---
# <a name="connections-preview-overview"></a>Gambaran keseluruhan sambungan (pratonton)

Sambungan adalah kunci untuk mendayakan perkongsian data ke dan daripada Customer Insights. Setiap sambungan mewujudkan perkongsian data dengan perkhidmatan tertentu. Gunakan sambungan untuk [mengkonfigurasi pengayaan](enrichment-hub.md) pihak ketiga dan [mengkonfigurasi eksport](export-destinations.md). Sambungan yang sama boleh digunakan beberapa kali. Sebagai contoh, satu sambungan ke Dynamics 365 Marketing berfungsi untuk berbilang eksport dan satu sambungan Leadspace boleh digunakan untuk beberapa pengayaan.

## <a name="export-connections"></a>Eksport sambungan

Hanya pentadbir boleh mengkonfigurasi sambungan baharu, tetapi mereka boleh [memberikan akses kepada penyumbang](#allow-contributors-to-use-a-connection-for-exports) untuk menggunakan sambungan sedia ada. Pentadbir mengawal tempat data boleh pergi, penyumbang mentakrifkan muatan dan kekerapan untuk memenuhi keperluan mereka.

## <a name="enrichment-connections"></a>Sambungan pengayaan

Hanya pentadbir boleh mengkonfigurasi sambungan baru, tetapi sambungan yang dibuat sentiasa tersedia untuk kedua-dua pentadbir dan penyumbang. Pentadbir mengurus kelayakan dan memberi keizinan kepada pemindahan data. Sambungan boleh digunakan oleh pentadbir dan penyumbang untuk pengayaan.

## <a name="add-a-new-connection"></a>Tambah sambungan baharu

### <a name="prerequisites"></a>Prasyarat

- [Keizinan pentadbir](permissions.md)
- Perkhidmatan Microsoft yang lain, jika ada, berada dalam organisasi yang sama

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih jenis sambungan yang anda mahu cipta. Atau, pergi ke tab **Discover** dan pilih **Sediakan** pada jubin sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Masukkan butiran yang diperlukan. Medan yang tepat bergantung pada perkhidmatan yang anda sambungkan. Untuk butiran jenis sambungan tertentu, rujuk artikel mengenai perkhidmatan sasaran.

1. Jika anda [gunakan Key Vault anda sendiri](use-azure-key-vault.md) untuk menyimpan rahsia, aktifkan **Gunakan Key Vault** dan pilih rahsia daripada senarai.

1. Semak privasi dan pematuhan data dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk mencipta sambungan.

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data kepada pihak ketiga atau produk Microsoft lain, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa pihak ketiga memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Pentadbir anda Dynamics 365 Customer Insights boleh mengalih keluar sambungan pada bila-bila masa untuk menghentikan penggunaan kefungsian.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Benarkan penyumbang untuk menggunakan sambungan untuk eksport

Apabila menyediakan atau mengedit sambungan eksport, pilih pengguna mana yang dibenarkan menggunakan sambungan khusus ini untuk mentakrifkan [eksport](export-destinations.md). Secara lalai, sambungan tersedia untuk pengguna dengan peranan pentadbir. Tukar Pilih orang **yang boleh menggunakan seting sambungan** ini untuk membenarkan pengguna dengan peranan penyumbang menggunakan sambungan ini.

- Penyumbang tidak akan dapat melihat atau mengedit sambungan. Mereka hanya akan melihat nama paparan dan jenisnya semasa membuat eksport.
- Dengan berkongsi sambungan, anda membenarkan penyumbang untuk menggunakan sambungan. Penyumbang akan melihat sambungan dikongsi apabila mereka menyediakan eksport. Mereka boleh mengurus setiap eksport yang menggunakan sambungan khusus ini.
- Anda boleh mengubah tetapan ini di samping mengekalkan eksport yang telah ditakrifkan oleh penyumbang.

## <a name="manage-existing-connections"></a>Urus sambungan sedia ada

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih tab **Pengayaan** atau **Eksport** untuk melihat senarai pengayaan atau sambungan eksport, jenis sambungan, apabila ia dicipta dan individu yang mempunyai capaian. Anda boleh mengisih senarai sambungan mengikut mana-mana lajur.

1. Pilih sambungan untuk melihat tindakan yang tersedia.

   - **Edit** sambungan.
   - [**Alih keluar**](#remove-a-connection) sambungan.

### <a name="remove-a-connection"></a>Alih keluar sambungan

Jika sambungan yang anda alih keluar digunakan oleh pengayaan atau eksport, lepaskan dahulu atau alih keluarnya. Dialog alih keluar membimbing anda kepada pengayaan atau eksport yang berkaitan.

> [!TIP]
> Pengayaan yang dinyahaktifkan dan eksport terpisah menjadi tidak aktif. Anda mengaktifkan semula dengan menambah sambungan lain kepadanya pada halaman [Pengayaan](enrichment-hub.md) atau [Eksport](export-destinations.md).

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih tab **Pengayaan** atau **Eksport**.

1. Pilih sambungan yang anda mahu alih keluar.

1. Pilih **Alih keluar** daripada menu juntai bawah. Dialog pengesahan muncul.

   1. Jika terdapat pengayaan atau eksport menggunakan sambungan ini, pilih butang untuk melihat apa yang menggunakan sambungan.
      - **Eksport:** Pilih sama ada **Alih keluar** eksport atau **Tanggalkan sambungan**. Melepaskan sambungan mengekalkan konfigurasi eksport, tetapi ia tidak akan dijalankan sehingga sambungan lain ditambah kepadanya.
      - **Pengayaan:** Pilih sama ada **Padam** atau **Nyahaktifkan** pengayaan.
   1. Sebaik sahaja sambungan tidak mempunyai kebergantungan, pergi kembali ke **Pentadbir** > **Sambungan** dan cuba alih keluar sambungan semula.

1. Untuk mengesahkan pemadaman, pilih **Alih keluar**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Sediakan sambungan dengan rahsia yang diuruskan oleh Key Vault anda sendiri

Sesetengah sambungan memerlukan rahsia seperti kekunci API atau kata laluan. Sesetengah sambungan menyokong rahsia yang disimpan dalam Key Vault anda sendiri. Ketahui lebih lanjut tentang sambungan yang disokong dan cara menyediakan pada [Peti Besi Kunci anda sendiri untuk Wawasan](use-azure-key-vault.md) Pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
