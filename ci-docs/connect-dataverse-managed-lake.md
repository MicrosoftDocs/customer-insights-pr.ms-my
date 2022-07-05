---
title: Sambung ke data dalam data lake terurus Microsoft Dataverse
description: Import data daripada danau data terurus Microsoft Dataverse.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082160"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Sambung ke data dalam data lake terurus Microsoft Dataverse

Microsoft Dataverse pengguna boleh menyambung dengan cepat ke entiti analisis di tasik yang Microsoft Dataverse diuruskan.

> [!NOTE]
> Anda mesti menjadi pentadbir organisasi Dataverse untuk meneruskan dan melihat senarai entiti yang terdapat di tasik yang diuruskan.

## <a name="important-considerations"></a>Pertimbangan penting

1. Data disimpan dalam perkhidmatan dalam talian seperti Azure Data Lake Storage, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung ke data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).
2. Hanya Dataverse entiti dengan [penjejakan](/power-platform/admin/enable-change-tracking-control-data-synchronization) perubahan yang didayakan boleh dilihat. Entiti ini boleh dieksport ke Dataverse tasik data terurus dan digunakan dalam Wawasan Pelanggan. Jadual luar kotak Dataverse telah mengubah penjejakan yang didayakan secara lalai. Anda perlu menghidupkan penjejakan perubahan untuk jadual tersuai. Untuk menyemak sama ada Dataverse jadual didayakan untuk penjejakan perubahan, pergi ke [Power Apps](https://make.powerapps.com) > **Jadual** > **Data**. Cari jadual minat anda dan pilihnya. Pergi ke **Seting** > **Opsyen** lanjutan dan semak semula **seting Jejak perubahan**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Sambung ke lake diurus Dataverse

1. Pergi **Data** > **Sumber data**.

1. Pilih **Tambah sumber data**.

1. Pilih **Microsoft Dataverse**.

1. **Masukkan Nama** untuk sumber data dan Perihalan **pilihan**.

1. Berikan **alamat Pelayan** untuk organisasi Dataverse dan pilih **Log masuk**.

1. Pilih jadual yang anda ingin makan sebagai entiti kepada Wawasan Pelanggan daripada senarai yang tersedia.

   > [!NOTE]
   > Jika sesetengah jadual telah dipilih, ia mungkin digunakan oleh aplikasi Dynamics 365 lain (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak boleh mengubah pemilihan. Jadual ini akan tersedia sebagai entiti sebaik sahaja sumber data dicipta.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Kotak dialog yang menunjukkan senarai entiti dalam persekitaran Dataverse.":::

1. Simpan pilihan anda untuk mula menyegerakkan jadual terpilih daripada Dataverse. Anda akan menemui sambungan yang baru ditambah pada halaman **Sumber data**. Ia akan dibaris gilir untuk segar semula dan menunjukkan kiraan entiti sebagai 0 sehingga semua jadual yang dipilih disegerakkan.

Hanya satu sumber data persekitaran boleh secara serentak menggunakan lake terurus Dataverse yang sama.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edit sumber data lake diurus Dataverse

Anda hanya mengedit pemilihan entiti selepas mencipta sumber data. Sebagai contoh, jika entiti tambahan ditambah Dataverse dan anda mahu mengimportnya juga.
Untuk bersambung ke danau data Dataverse yang lain, [cipta sumber data baharu](#connect-to-a-dataverse-managed-lake).

1. Pergi **Data** > **Sumber data**.

1. Di sebelah sumber data yang anda ingin kemas kini, pilih **Edit**.

1. Pilih entiti tambahan daripada senarai entiti yang tersedia dan pilih **Simpan**.
