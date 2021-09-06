---
title: Pengayaan dengan import tersuai SFTP
description: Maklumat umum tentang pengayaan import tersuai SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032723"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Perkayakan profil pelanggan dengan data tersuai (pratonton)

Import tersuai Protokol Pemindahan Fail Selamat (SFTP) mendayakan anda mengimport data yang tidak perlu melalui proses penyatuan data. Ia adalah cara yang fleksibel, selamat dan mudah untuk membawa masuk data anda. Import tersuai SFTP boleh digunakan dalam kombinasi dengan [Eksport SFTP](export-sftp.md) membolehkan anda mengeksport data profil pelanggan yang diperlukan untuk pengayaan. Data kemudiannya boleh diproses dan diperkaya, dan import SFTP tersuai boleh digunakan untuk membawa data yang diperkaya kembali kepada keupayaan cerapan khalayak Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi import tersuai SFTP, prasyarat berikut mesti dipenuhi:

- Anda mempunyai nama fail dan lokasi (laluan) fail yang akan diimport pada hos SFTP.
- Terdapat fail *model.json* yang menentukan [skema Common Data Model](/common-data-model/) untuk data yang akan diimport. Fail ini mestilah dalam direktori yang sama dengan fail untuk diimport.
- Sambungan SFTP telah dikonfigurasikan oleh pentadbir *atau* anda mempunyai keizinan [pentadbir](permissions.md#administrator). Anda memerlukan kelayakan pengguna, URL dan nombor port untuk lokasi SFTP yang mahu diimport data.


## <a name="configure-the-import"></a>Konfigurasikan import

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pada **jubin import tersuai SFTP**, pilih **Perkayakan data saya** dan kemudian pilih **Mari bermula**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Jubin import tersuai SFTP.":::

1. Pilih [sambungan](connections.md) daripada senarai juntai bawah. Hubungi pentadbir jika tiada sambungan tersedia. Jika anda seorang pentadbir, anda boleh mencipta sambungan dengan memilih **Tambah sambungan** dan memilih **Import SFTP Tersuai** daripada senarai juntai bawah.

1. Pilih **Sambung ke Import Tersuai** untuk mengesahkan sambungan yang dipilih.

1.  Pilih **Seterusnya** dan masukkan **Laluan** dan **Nama fail** bagi fail data yang mahu diimport.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Tangkapan skrin semasa memasuki lokasi data.":::

1. Pilih **Seterusnya** dan berikan nama untuk pengayaan dan nama untuk entiti output. 

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurasikan sambungan untuk Import Tersuai SFTP 

Anda perlu menjadi pentadbir untuk mengkonfigurasikan sambungan. Pilih **Tambah sambungan** apabila mengkonfigurasikan pengayaan *atau* pergi ke **Pentadbir** > **Sambungan** dan pilih **Sediakan** pada jubin Import Tersuai.

1. Masukkan nama untuk sambungan dalam kotak **Nama paparan**.

1. Masukkan nama pengguna, kata laluan dan hos URL yang sah untuk pelayan SFTP yang data akan diimport berada.

1. Semak semula dan berikan persetujuan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi.

1. Setelah pengesahan selesai, sambungan boleh disimpan dengan memilih **Simpan**.

   > [!div class="mx-imgBorder"]
   > ![Halaman konfigurasi sambungan Experian.](media/enrichment-SFTP-connection.png "Halaman konfigurasi sambungan Experian")


## <a name="defining-field-mappings"></a>Mentakrifkan pemetaan medan 

Direktori yang mengandungi fail untuk diimport pada pelayan SFTP juga mesti mengandungi fail *model.json*. Fail ini mentakrifkan skema untuk digunakan bagi mengimport data. Skema perlu menggunakan [Common Data Model](/common-data-model/) untuk menentukan pemetaan medan. Contoh mudah fail model.json kelihatan seperti ini:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan akan bergantung pada saiz data yang akan diimport dan sambungan ke pelayan SFTP.

Selepas proses pengayaan selesai, anda boleh menyemak data pengayaan tersuai anda yang baru diimport di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh mengakses pandangan terperinci setiap profil yang diperkayakan dengan memilih **Lihat data yang diperkayakan**.

## <a name="next-steps"></a>Langkah seterusnya

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md) dan [langkah](measures.md) serta [eksport data](export-destinations.md) untuk menyampaikan pengalaman yang diperibadikan kepada pelanggan anda.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
