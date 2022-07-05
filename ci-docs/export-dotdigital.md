---
title: Eksport segmen ke DotDigital (pratonton)
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: af0cce4edb9d47247c79ae08491366349da98b1c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082937"
---
# <a name="export-segments-to-dotdigital-preview"></a>Eksport segmen ke DotDigital (pratonton)

Eksport segmen profil pelanggan disatukan ke buku alamat DotDigital dan gunakannya untuk kempen, pemasaran e-mel dan untuk membina segmen pelanggan dengan DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

-   Anda mempunyai [Akaun DotDigital](https://dotdigital.com/) dan mencipta [pengguna API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Anda akan memerlukan kelayakan pengguna API untuk mencipta sambungan
-   Terdapat buku alamat sedia ada dalam DotDigital dan ID yang berkaitan. ID boleh ditemui dalam URL apabila anda memilih dan membuka buku alamat. Untuk maklumat lanjut, lihat [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Anda telah [mengkonfigurasi segmen](segments.md) dalam Wawasan Pelanggan.
-   Profil pelanggan disatukan dalam segmen yang dieksport mengandungi medan yang mewakili alamat e-mel.

## <a name="known-limitations"></a>Had diketahui

- Hingga 1 juta profil pelanggan bagi setiap eksport kepada DotDigital.
- Mengeksport ke DotDigital adalah terhad kepada segmen.
- Segmen eksport dengan jumlah 1 juta profil pelanggan boleh mengambil masa hingga 3 jam kerana had pada bahagian pembekal. 
- Bilangan profil pelanggan yang boleh anda eksport kepada DotDigital bergantung dan terhad pada kontrak anda dengan DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Sediakan sambungan ke DotDigital

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **DotDigital** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Masukkan **Nama pengguna dan kata laluan API DotDigital** anda. 

1. Masukkan **[ID buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)** anda.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Sambung** untuk memulakan sambungan ke DotDigital.

1. Pilih **Tambah diri anda sebagai pengguna eksport** dan berikan kelayakan Customer Insights anda.

1. Pilih **Simpan** untuk melengkapkan sambungan. 

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian DotDigital. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.


1. Dalam bahagian **Pemadanan data** dalam medan **E-mel**, pilih medan yang mewakili alamat e-mel pelanggan. Ulangi langkah yang sama untuk medan pilihan lain seperti **Nama pertama**, **Nama akhir**, **Nama penuh**, **Jantina** dan **Poskod**.

1. Pilih segmen yang ingin anda eksport. Anda boleh mengeksport hingga 1 juta profil pelanggan dalam jumlah keseluruhan DotDigital.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 
 
Dalam DotDigital, anda kini boleh mencari segmen anda dalam [Buku alamat DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke DotDigital, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa DotDigital memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE [footer-include](includes/footer-banner.md)]
