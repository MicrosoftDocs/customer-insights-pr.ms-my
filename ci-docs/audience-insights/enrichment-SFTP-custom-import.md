---
title: Pengayaan dengan import tersuai SFTP
description: Maklumat umum tentang pengayaan import tersuai SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269617"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Perkayakan profil pelanggan dengan data tersuai (pratonton)

Import tersuai Protokol Pemindahan Fail Selamat (SFTP) mendayakan anda mengimport data yang tidak perlu melalui proses penyatuan data. Ia adalah cara yang fleksibel, selamat dan mudah untuk membawa masuk data anda. Import tersuai SFTP boleh digunakan dalam kombinasi dengan [Eksport SFTP](export-sftp.md) membolehkan anda mengeksport data profil pelanggan yang diperlukan untuk pengayaan. Data kemudian boleh diproses, diperkaya dan import tersuai SFTP boleh digunakan untuk membawa data yang diperkaya kembali kepada keupayaan wawasan khalayak Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi import tersuai SFTP, prasyarat berikut mesti dipenuhi:

- Anda mempunyai kelayakan pengguna (nama pengguna dan kata laluan) untuk lokasi SFTP data yang akan diimport.
- Anda mempunyai URL dan nombor port (kebiasaannya 22) untuk hos STFP.
- Anda mempunyai nama fail dan lokasi fail untuk diimport pada hos SFTP.
- Terdapat fail *model.json* yang menentukan skema untuk data yang akan diimport. Fail ini mestilah dalam direktori yang sama dengan fail untuk diimport.
- Anda mempunyai keizinan [Pentadbir](permissions.md#administrator).

## <a name="configuration"></a>Konfigurasi

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pada **Jubin import tersuai SFTP**, pilih **Perkayakan data saya**.

   > [!div class="mx-imgBorder"]
   > ![Jubin Import tersuai SFTP](media/SFTP_Custom_Import_tile.png "Jubin Import tersuai SFTP")

1. Pilih **Mari Bermula** dan berikan kelayakan dan alamat untuk pelayan SFTP. Contohnya, sftp://mysftpserver.com:22.

1. Masukkan nama fail yang mengandungi data dan laluan ke fail pada pelayan SFTP jika ia bukan dalam folder induk.

1. Sahkan semua input dengan memilih **Sambung ke Import Tersuai**.

   > [!div class="mx-imgBorder"]
   > ![Terbang keluar Konfigurasi Import Tersuai SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Terbang keluar Konfigurasi Import Tersuai SFTP")

## <a name="defining-field-mappings"></a>Mentakrifkan pemetaan medan 

Direktori yang mengandungi fail untuk diimport pada pelayan SFTP juga mesti mengandungi fail *model.json*. Fail ini mentakrifkan skema untuk digunakan bagi mengimport data. Skema perlu menggunakan [Model Data Tersuai](https://docs.microsoft.com/common-data-model/) untuk menentukan pemetaan medan. Contoh mudah fail model.json kelihatan seperti ini:

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

Bina di atas data pelanggan anda yang diperkaya. Cipta [segmen](segments.md), [ukuran](measures.md) dan [eksport data](export-destinations.md) untuk menyampaikan pengalaman diperibadikan kepada pelanggan anda.




[!INCLUDE[footer-include](../includes/footer-banner.md)]