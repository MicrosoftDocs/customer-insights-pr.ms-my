---
title: Sambungkan kepada jadual dalam Microsoft Dataverse
description: Import data daripada danau data terurus Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033091"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Sambung ke data dalam data lake terurus Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Artikel ini menyediakan maklumat tentang cara pengguna Dataverse boleh bersambung kepada entiti analitis mereka dengan cepat daam tasik yang diuruskan Dataverse. Anda mesti menjadi pentadbir dalam organisasi Dataverse untuk meneruskan dan melihat senarai entiti yang tersedia dalam danau terurus.

## <a name="important-considerations"></a>Pertimbangan penting

Data disimpan dalam perkhidmatan dalam talian seperti Azure Data Lake Storage, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung kepada data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan ke dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Sambung ke lake diurus Dataverse

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih **Tambah sumber data**.

3. Pilih **Sambung ke danau diuruskan Microsoft Dataverse** dan pilih **Seterusnya**.

4. Masukkan **Name** untuk sumber data dan kemudian pilih **Seterusnya**. Namakan garis panduan: 
   - Bermula dengan huruf.
   - Gunakan huruf dan nombor sahaja. Aksara khas dan ruang idak dibenarkan.
   - Gunakan antara 3 dan 64 aksara.

5. Berikan **alamat Pelayan** untuk organisasi Dataverse dan pilih **Log masuk**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Skrin dalam langkah pengingesan data yang pengguna boleh masuk ke dalam persekitaran URL Dataverse.":::

6. Pilih jadual yang anda mahu injes sebagai entiti kepada cerapan khalayak daripada senarai yang tersedia.    

   > [!NOTE]
   > Jika sesetengah jadual telah dipilih, ia mungkin digunakan oleh aplikasi Dynamics 365 lain (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak boleh mengubah pemilihan. Jadual ini akan tersedia sebagai entiti sebaik sahaja sumber data dicipta.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Kotak dialog yang menunjukkan senarai entiti dalam persekitaran Dataverse.":::

7. Simpan pilihan anda untuk mula menyegerakkan jadual terpilih daripada Dataverse. Anda akan menemui sambungan yang baru ditambah pada halaman **Sumber data**. Ia akan dibaris gilir untuk segar semula dan menunjukkan kiraan entiti sebagai 0 sehingga semua jadual yang dipilih disegerakkan.

Hanya satu sumber data persekitaran boleh secara serentak menggunakan lake terurus Dataverse yang sama.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edit sumber data lake diurus Dataverse

Anda hanya mengedit pemilihan entiti selepas mencipta sumber data. Sebagai contoh, jika entiti tambahan ditambah Dataverse dan anda mahu mengimportnya juga.    
Untuk bersambung ke danau data Dataverse yang lain, [cipta sumber data baharu](#connect-to-a-dataverse-managed-lake).

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Bersebelahan dengan sumber data yang anda mahu kemas kini, pilih elipsis.

3. Pilih pilihan **Edit** daripada senarai.

4. Pilih entiti tambahan daripada senarai entiti yang tersedia dan pilih **Simpan**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]