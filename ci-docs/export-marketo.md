---
title: Eksport data Customer Insights ke Marketo
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7354b0aeafbe95e60d172b16c26d83c5dc25fb96
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643954"
---
# <a name="export-segments-to-marketo-preview"></a>Eksport segmen ke Marketo (pratonton)

Eksport segmen profil pelanggan disatukan untuk menjana kempen, menyediakan pemasaran e-mel dan gunakan kumpulan pelanggan tertentu dengan Marketo.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [Akaun Marketo](https://login.marketo.com/) dan kelayakan pentadbir yang berkaitan.
-   Terdapat senarai sedia ada dalam Marketo dan ID yang berkaitan. Untuk maklumat lanjut, lihat [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Anda telah [mengkonfigurasi segmen](segments.md).
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil pelanggan bagi setiap eksport kepada Marketo.
- Mengeksport ke Marketo adalah terhad kepada segmen.
- Mengeksport segmen dengan jumlah 1 juta profil pelanggan boleh mengambil masa hingga 3 jam. 
- Bilangan profil pelanggan yang boleh anda eksport kepada Marketo bergantung dan terhad pada kontrak anda dengan Marketo.

## <a name="set-up-connection-to-marketo"></a>Sediakan sambungan ke Marketo

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Marketo** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **[ID klien Marketo, Rahsia pelanggan dan Nama Hos Titik Tamat REST](https://developers.marketo.com/rest-api/authentication/)** anda. Nama hos Titik tamat REST adalah nama hos sahaja tanpa `https://`. Contoh: `xyz-abc-123.mktorest.com`. 

1. Pilih **Saya setuju** untuk mengesahkan **Privasi data dan pematuhan** dan pilih **Sambung** untuk memulakan sambungan ke Marketo.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian Marketo. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Masukkan **[ID senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** anda. ID senarai adalah semata-mata nilai berangka. Contohnya, jika ID senarai Marketo anda ialah ST12345A7, alih keluar aksara sebelum dan selepas angka dan masukkan `12345`. 

1. **Dalam bahagian Pemadanan** data, pilih sekurang-kurangnya satu medan yang mewakili alamat e-mel pelanggan atau ID Marketo pelanggan. 

1. Selain itu, anda boleh mengeksport **Nama pertama**, **Nama terakhir**, **Bandar**, **Negeri**, dan **Negeri/Rantau**  untuk mencipta e-mel yang diperibadikan. Pilih **Tambah atribut** untuk memetakan medan ini.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta jumlah profil pelanggan ke Marketo.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). Dalam Marketo, anda kini boleh mencari segmen anda di bawah [Senarai Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Marketo, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Marketo memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE [footer-include](includes/footer-banner.md)]
