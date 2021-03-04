---
title: Eksport data Customer Insights ke Pengurus Iklan Facebook
description: Ketahui cara mengkonfigurasi sambungan ke Pengurus Iklan Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269985"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Penyambung untuk Pengurus Iklan Facebook (pratonton)

Eksport segmen profil pelanggan disatukan ke Pengurus Iklan Facebook untuk mencipta kempen pada Facebook dan Instagram.

## <a name="prerequisites"></a>Prasyarat

- Anda perlu mempunyai [Akaun Iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) yang merangkumi [Akaun Perniagaan **Facebook**](https://business.facebook.com/).
- Anda perlu menjadi pentadbir pada [Akaun Iklan **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Connect ke Pengurus Iklan Facebook

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah Pengurus Iklan **Facebook**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

1. Pilih **Teruskan dengan Facebook** untuk mendaftar masuk ke Akaun Iklan Facebook.

1. Benarkan keizinan **ads_management** selepas pengesahan dengan Facebook.

1. Pilih **Akaun Iklan Facebook** yang anda ingin kendalikan.

1. Pilih **Khalayak tersuai sedia ada** daripada senarai juntai bawah atau cipta **Khalayak tersuai baharu**. Untuk maklumat lanjut, lihat [**Khalayak dalam Pengurus Iklan Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Seterusnya** untuk konfigurasi eksport.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam **Pilih medan pengecam kunci anda**, pilih **E-mel**, **Nama dan alamat**, atau **Telefon** untuk dihantar ke Pengurus Iklan Facebook.

1. Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.
   > [TIP] Peluang terbaik untuk padanan berlaku jika anda memilih **E-mel** sebagai pengecam kunci. Menambah pengecam tambahan mungkin meningkatkan pemadanan.

1. Pilih **Tambah atribut** bagi memetakan atribut tambahan untuk dihantar ke Pengurus Iklan Facebook. Atribut daripada Pengurus Iklan Facebook dipetakan pada nama mesra pengguna berikut: **FN** = **Nama Pertama**, **LN** = **Nama Terakhir**, **FI** = **Parap Pertama**, **PHONE** = **Telefon**, **GEN** = **Jantina**, **DOB** = **Tarikh lahir**, **ST** = **Negeri**, **CT** = **Bandar**, **ZIP** = **Poskod / Kod Zip**, **COUNTRY** = **Negara / Rantau**

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

## <a name="known-limitations"></a>Had diketahui

- Sehingga 10 juta profil pelanggan setiap eksport ke Pengurus Iklan Facebook 
- Eksport ke Pengurus Iklan Facebook adalah terhad kepada segmen
- Mengeksport segmen dengan jumlah 10 juta profil boleh mengambil masa sehingga 90 minit untuk selesai

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke Pengurus Iklan Facebook, anda membenarkan penghantaran data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa Iklan Facebook memenuhi sebarang kewajipan privasi atau keselamatan yang anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]