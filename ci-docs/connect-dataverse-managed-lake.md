---
title: Sambung ke data dalam data lake terurus Microsoft Dataverse
description: Import data daripada danau data terurus Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609806"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Sambung ke data dalam data lake terurus Microsoft Dataverse

Microsoft Dataverse pengguna boleh dengan cepat menyambung kepada entiti analisis di tasik terurus Microsoft Dataverse. Hanya satu sumber data persekitaran boleh secara serentak menggunakan lake terurus Dataverse yang sama.

> [!NOTE]
> Anda mesti menjadi pentadbir dalam Dataverse organisasi untuk meneruskan dan melihat senarai entiti yang terdapat di tasik terurus.

## <a name="prerequisites"></a>Prasyarat

- Data disimpan dalam perkhidmatan dalam talian seperti Azure Data Lake Storage, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung ke data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

- Hanya Dataverse entiti dengan [penjejakan](/power-platform/admin/enable-change-tracking-control-data-synchronization) perubahan yang didayakan dapat dilihat. Entiti-entiti ini boleh dieksport ke tasik data yang Dataverse diuruskan dan digunakan dalam Wawasan Pelanggan. Jadual luar kotak Dataverse telah mengubah penjejakan yang didayakan secara lalai. Anda perlu menghidupkan penjejakan perubahan untuk jadual tersuai. Untuk menyemak sama Dataverse ada jadual didayakan untuk penjejakan perubahan, pergi ke [Power Apps](https://make.powerapps.com) > **Jadual** > **Data**. Cari jadual minat anda dan pilihnya. Pergi ke **Seting** > **Opsyen** lanjutan dan semak semula **seting Jejak perubahan**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Sambung ke lake diurus Dataverse

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft Dataverse**.

1. **Masukkan Nama** untuk sumber data dan Perihalan **pilihan**.

1. Berikan **alamat Pelayan** untuk organisasi Dataverse dan pilih **Log masuk**.

1. Pilih jadual yang anda ingin makan sebagai entiti untuk Wawasan Pelanggan daripada senarai yang tersedia.

   > [!NOTE]
   > Jika sesetengah jadual telah dipilih, ia mungkin digunakan oleh aplikasi Dynamics 365 lain (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak boleh mengubah pemilihan. Jadual ini akan tersedia sebagai entiti sebaik sahaja sumber data dicipta.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Kotak dialog yang menunjukkan senarai entiti dalam persekitaran Dataverse.":::

1. Simpan pilihan anda untuk mula menyegerakkan jadual terpilih daripada Dataverse. Anda akan menemui sambungan yang baru ditambah pada halaman **Sumber data**. Ia akan dibaris gilir untuk segar semula dan menunjukkan kiraan entiti sebagai 0 sehingga semua jadual yang dipilih disegerakkan.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang ditelan boleh disemak dari [**halaman Entiti**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edit sumber data lake diurus Dataverse

Anda hanya mengedit pemilihan entiti selepas mencipta sumber data. Sebagai contoh, jika entiti tambahan ditambah Dataverse dan anda mahu mengimportnya juga.
Untuk bersambung ke danau data Dataverse yang lain, [cipta sumber data baharu](#connect-to-a-dataverse-managed-lake).

1. Pergi **Data** > **Sumber data**.

1. Di sebelah sumber data yang ingin anda kemas kini, pilih **Edit**.

1. Pilih entiti tambahan dari senarai entiti yang tersedia.

1. Klik **Simpan** untuk menggunakan perubahan anda dan kembali ke **halaman Sumber data**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Sebab biasa untuk kesilapan pengingesan atau data yang rosak

Pemeriksaan berikut berjalan pada data yang diinjes untuk mendedahkan rekod rosak:

- Nilai medan tidak sepadan dengan jenis data lajurnya.
- Medan mengandungi aksara yang menyebabkan lajur tidak sepadan dengan skema yang dijangkakan. Sebagai contoh: sebut harga yang diformatkan dengan salah, sebut harga yang tidak dilepaskan atau aksara baris baharu.
- Jika terdapat lajur datetime/date/datetimeoffset, formatnya mesti ditentukan dalam model jika ia tidak mengikut format ISO standard.

### <a name="schema-or-data-type-mismatch"></a>Skema atau ketidakpadanan jenis data

Jika data tidak mematuhi skema, rekod diklasifikasikan sebagai rasuah. Betulkan sama ada data sumber atau skema dan termakan semula data.

### <a name="datetime-fields-in-the-wrong-format"></a>Medan Datetime dalam format yang salah

Medan datetime dalam entiti tidak berada dalam format ISO atau en-US. Format datetime lalai dalam Wawasan Pelanggan ialah format en-AS. Semua medan datetime dalam entiti hendaklah dalam format yang sama. Wawasan Pelanggan menyokong format lain yang disediakan anotasi atau ciri dibuat di peringkat sumber atau entiti dalam model atau manifest.json. Contohnya: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Dalam manifest.json, format datetime boleh ditentukan di peringkat entiti atau pada tahap atribut. Di peringkat entiti, gunakan "exhibitsTraits" dalam entiti dalam *.manifest.cdm.json untuk menentukan format masa data. Di peringkat atribut, gunakan "appliedTraits" dalam atribut dalam nama entiti.cdm.json.

**Manifest.json di peringkat entiti**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json pada tahap atribut**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
