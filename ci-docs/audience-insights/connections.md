---
title: Sambungan ke perkhidmatan lain daripada Customer Insights.
description: Kongsi data ke perkhidmatan lain.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304983"
---
# <a name="connections-preview-overview"></a>Gambaran keseluruhan sambungan (pratonton)

Sambungan adalah kunci untuk mendayakan perkongsian data ke dan daripada Customer Insights. Setiap sambungan mewujudkan perkongsian data dengan perkhidmatan tertentu. Sambungan adalah asas untuk [mengkonfigurasikan pengayaan pihak ketiga](enrichment-hub.md) dan [mengkonfigurasi eksport](export-destinations.md). Sambungan yang sama boleh digunakan beberapa kali. Sebagai contoh, satu sambungan ke Dynamics 365 Marketing berfungsi untuk berbilang eksport dan satu sambungan Leadspace boleh digunakan untuk beberapa pengayaan.

Pergi ke **Pentadbir** > **Sambungan** untuk mencipta dan melihat sambungan.

Tab **Sambungan** menunjukkan anda semua sambungan aktif. Senarai menunjukkan baris untuk setiap sambungan. 

Dapatkan gambaran keseluruhan pantas, perihalan, dan ketahui perkara yang boleh anda lakukan dengan setiap pilihan kebolehsambungan pad tab **Temui**.

### <a name="exports"></a>Eksport

Hanya pentadbir boleh mengkonfigurasikan sambungan baharu, tetapi mereka boleh memberikan akses kepada penyumbang untuk menggunakan sambungan yang sedia ada. Pentadbir mengawal tempat data boleh pergi, penyumbang mentakrifkan muatan dan kekerapan untuk memenuhi keperluan mereka. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](#allow-contributors-to-use-a-connection-for-exports).

### <a name="enrichments"></a>Pengayaan

Hanya pentadbir boleh mengkonfigurasikan sambungan baharu tetapi sambungan yang dicipta sentiasa tersedia untuk pentadbir dan penyumbang. Pentadbir mengurus kelayakan dan memberi keizinan kepada pemindahan data. Sambungan boleh digunakan oleh pentadbir dan penyumbang untuk pengayaan.

## <a name="add-a-new-connection"></a>Tambah sambungan baharu

Untuk menambah sambungan, anda perlu mempunyai [keizinan pentadbir](permissions.md). Jika anda bersambung ke perkhidmatan Microsoft lain, kami menganggap kedua-dua perkhidmatan berada dalam organisasi yang sama.

1. Pergi ke **Pentadbir** > **Sambungan (pratonton)**.

1. Pergi ke tab **Sambungan**.

1. Pilih **Tambah sambungan** untuk mencipta sambungan baharu. Pilih daripada menu juntai bawah jenis sambungan yang mahu anda cipta.

1. Dalam anak tetingkap **Sediakan sambungan**, berikan butiran yang diperlukan. 
   1. **Nama paparan** dan jenis sambungan yang menerangkan sambungan. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan ini.
   1. Medan sebenar bergantung pada jenis perkhidmatan yang anda bersambung. Anda boleh mengetahui tentang butiran jenis sambungan khusus dalam artikel mengenai perkhidmatan sasaran.

1. Untuk mencipta sambungan, pilih **Simpan**.

Anda juga boleh memilih **Sediakan** pada jubin pada tab **Temui**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Benarkan penyumbang untuk menggunakan sambungan untuk eksport

Apabila menyediakan atau mengedit sambungan eksport, anda memilih pengguna yang dibenarkan untuk menggunakan sambungan khusus ini untuk mentakrifkan [eksport](export-destinations.md). Secara lalai, sambungan tersedia kepada pengguna yang mempunyai peranan pentadbir. Anda boleh mengubah tetapan ini di bawah **Pilih individu yang boleh menggunakan sambungan ini** dan membenarkan pengguna yang mempunyai peranan penyumbang untuk menggunakan sambungan ini.

- Penyumbang tidak akan dapat melihat atau mengedit sambungan. Mereka hanya akan melihat nama paparan dan jenis apabila mencipta eksport.
- Dengan berkongsi sambungan, anda membenarkan penyumbang untuk menggunakan sambungan. Penyumbang akan melihat sambungan dikongsi apabila mereka menyediakan eksport. Mereka boleh mengurus setiap eksport yang menggunakan sambungan khusus ini.
- Anda boleh mengubah tetapan ini di samping mengekalkan eksport yang telah ditakrifkan oleh penyumbang.

## <a name="edit-a-connection"></a>Edit sambungan

1. Pergi ke **Pentadbir** > **Sambungan (pratonton)**.

1. Pergi ke tab **Sambungan**.

1. Pilih elipsis menegak untuk sambungan yang anda mahu edit.

1. Pilih **Edit**.

1. Ubah nilai yang anda mahu kemas kini dan pilih **Simpan**.

## <a name="remove-a-connection"></a>Alih keluar sambungan

Jika sambungan yang anda keluarkan digunakan oleh pengayaan atau eksport, anda perlu mengalih atau mengalihnya keluar. Dialog yang dialih keluar akan membimbing anda kepada pengayaan atau eksport yang berkaitan. 

Pengayaan dan eksport yang dialih menjadi tidak aktif. Anda mengaktifkan semula dengan menambah sambungan lain kepadanya pada halaman [Pengayaan](enrichment-hub.md) atau [Eksport](export-destinations.md).

1. Pergi ke **Pentadbir** > **Sambungan (pratonton)**.

1. Pergi ke tab **Sambungan**.

1. Pilih elipsis menegak untuk sambungan yang anda mahu alih keluar.

1. Pilih **Alih keluar** daripada menu juntai bawah. Dialog pengesahan muncul.

   1. Jika terdapat pengayaan atau eksport menggunakan sambungan ini, pilih butang untuk melihat apa yang menggunakan sambungan.
      - **Eksport:** Anda boleh memilih sama ada untuk mengalih keluar atau nyahsambung eksport supaya dapat mengalih keluar sambungan. Untuk memutuskan sambungan eksport, pentadbir boleh menggunakan tindakan **Putuskan sambungan**. Tindakan ini tersedia untuk individu dan berbilang eksport terpilih. Dengan memutuskan sambungan, anda mengekalkan konfigurasi eksport, tetapi ia tidak akan berjalan sehingga sambungan yang lain ditambah padanya.
      - **Pengayaan:** Anda boleh memilih sama ada untuk mengalih keluar atau menyahaktif pengayaan supaya dapat mengalih keluar sambungan. 
   1. Sebaik sahaja sambungan tidak mempunyai kebergantungan, pergi kembali ke **Pentadbir** > **Sambungan** dan cuba alih keluar sambungan semula.

1. Untuk mengesahkan pemadaman, pilih **Alih keluar**.

