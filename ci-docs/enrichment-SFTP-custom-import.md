---
title: Memperkayakan profil pelanggan dengan import tersuai SFTP (pratonton)
description: Maklumat umum tentang pengayaan import tersuai SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195807"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Memperkayakan profil pelanggan dengan import tersuai SFTP (pratonton)

Import tersuai Protokol Pemindahan Fail Selamat (SFTP) mendayakan anda mengimport data yang tidak perlu melalui proses penyatuan data. Ia adalah cara yang fleksibel, selamat dan mudah untuk membawa masuk data anda. Import tersuai SFTP boleh digunakan dalam kombinasi dengan [Eksport SFTP](export-sftp.md) membolehkan anda mengeksport data profil pelanggan yang diperlukan untuk pengayaan. Data kemudiannya boleh diproses dan diperkaya, dan import tersuai SFTP boleh digunakan untuk membawa data yang diperkaya kembali ke Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Prasyarat

- Nama fail dan lokasi (laluan) fail yang akan diimport pada hos SFTP diketahui.

- Fail *model.json* yang menentukan skema Model Data Biasa untuk data yang akan diimport boleh didapati. Fail ini mestilah dalam direktori yang sama dengan fail untuk diimport.

- Sambungan [SFTP](connections.md) dikonfigurasikan [...](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Contoh skema fail

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Konfigurasikan sambungan untuk Import Tersuai SFTP

Anda mesti menjadi [pentadbir](permissions.md#admin) dalam Wawasan Pelanggan dan mempunyai kelayakan pengguna, URL dan nombor port untuk lokasi SFTP di mana anda ingin mengimport data.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Import Tersuai.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Halaman konfigurasi sambungan Import Tersuai.":::

1. Masukkan nama untuk sambungan.

1. Masukkan nama pengguna, kata laluan dan hos URL yang sah untuk pelayan SFTP yang data akan diimport berada.

1. Semak dan berikan persetujuan anda untuk [privasi dan pematuhan Data](#data-privacy-and-compliance) dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data menggunakan Import Tersuai, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa data memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

## <a name="configure-the-import"></a>Konfigurasikan import

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **jubin import** tersuai SFTP.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Jubin import tersuai SFTP.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Pilih **Seterusnya**.

1. **Masukkan Laluan** dan **Nama** Fail fail data yang anda ingin import.

1. Pilih **Seterusnya**.

1. **Berikan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
