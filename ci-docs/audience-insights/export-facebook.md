---
title: Eksport data Customer Insights ke Pengurus Iklan Facebook
description: Ketahui cara untuk mengkonfigurasikan sambungan dan Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976053"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Eksport senarai segmen ke Facebook Ads Manager (pratonton)

Eksport segmen profil pelanggan disatukan ke Pengurus Iklan Facebook untuk mencipta kempen pada Facebook dan Instagram.

## <a name="prerequisites-for-connection"></a>Prasyarat untuk sambungan

- Anda perlu mempunyai [Akaun iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang termasuk [Akaun Perniagaan **Facebook**](https://business.facebook.com/).
- Anda perlu menjadi pentadbir pada [Akaun Iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Had diketahui

- Sehingga 10 juta profil pelanggan bagi setiap eksport ke Facebook Ads Manager.
- Eksport ke Facebook Ads Manager adalah terhad kepada segmen.
- Cipta atau kemas kini khalayak tersuai dalam Facebook bagi jenis *senarai pelanggan* sahaja.
- Mengeksport segmen dengan jumlah 10 juta profil boleh mengambil masa sehingga 90 minit untuk diselesaikan.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Sediakan sambungan ke Facebook Ads Manager

Sebelum pengguna boleh mencipta eksport, pentadbir mesti mengkonfigurasikan sambungan ke perkhidmatan dan membenarkan penyumbang untuk menggunakan sambungan.

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **Facebook Ads Manager** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi **Pentadbir**. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sahkan dengan Facebook Ads: 

   1. Pilih **Teruskan dengan Facebook** untuk mendaftar masuk ke Akaun Iklan Facebook.

   1. Benarkan keizinan **ads_management** selepas pengesahan dengan Facebook.

   1. Pilih **Akaun Iklan Facebook** yang anda ingin kendalikan.

   1. Pilih **Khalayak tersuai sedia ada** daripada senarai juntai bawah atau cipta **Khalayak tersuai baharu**. Untuk maklumat lanjut, lihat [**Khalayak dalam Pengurus Iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Anda hanya boleh mencipta atau mengemas kini khalayak tersuai di Facebook untuk jenis *senarai pelanggan* dengan eksport ini. Dalam sesetengah kes, anda melihat khalayak tersuai untuk pelbagai jenis dalam senarai juntai bawah. Memilih jenis yang berbeza daripada *senarai pelanggan* akan menggagalkan eksport. 

1. Semak **Privasi data dan pematuhan** dan pilih **Saya bersetuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**. 

1. Dalam **Sambungan untuk eksport**, pilih sambungan daripada bahagian **Facebook Ads Manager**. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam **Pilih medan pengecam kunci anda**, pilih **E-mel**, **Nama dan alamat**, atau **Telefon** untuk dihantar ke Pengurus Iklan Facebook. 

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**.

1. Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.
   > [TIP] Peluang terbaik untuk padanan berlaku jika anda memilih **E-mel** sebagai pengecam kunci. Menambah pengecam tambahan mungkin meningkatkan pemadanan.

1. Pilih **Tambah atribut** untuk memetakan lebih banyak atribut untuk dihantar kepada Facebook Ads Manager. Atribut daripada Facebook Ads Manager dipetakan pada nama mesra pengguna berikut: **FN** = **Nama Pertama**, **LN** = **Nama Keluarga**, **FI** = **Parap Pertama**, **PHONE** = **Telefon**, **GEN** = **Jantina**, **DOB** = **Tarikh Lahir**, **ST** = **Negeri**, **CT** = **Bandar**, **ZIP** = **Poskod/Kod Zip**, **COUNTRY** = **Negara/Rantau**

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Pengurus Iklan Facebook, anda membenarkan penghantaran data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Iklan Facebook memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
