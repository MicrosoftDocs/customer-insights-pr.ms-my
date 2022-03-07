---
title: Sambungkan kepada jadual dalam Microsoft Dataverse
description: Import data daripada danau data terurus Microsoft Dataverse.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 8e11b60295fa5c187b1ac4877fb347e2d9bb41a1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354153"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Sambung ke data dalam data lake terurus Microsoft Dataverse



Artikel ini menyediakan maklumat tentang bagaimana Dataverse pengguna boleh menyambung dengan cepat ke entiti analisis di tasik terurus Microsoft Dataverse. 

> [!NOTE]
> Anda mesti menjadi pentadbir organisasi Dataverse untuk meneruskan dan melihat senarai entiti yang tersedia dalam tasik terurus.

## <a name="important-considerations"></a>Pertimbangan penting

Data disimpan dalam perkhidmatan dalam talian seperti Azure Data Lake Storage, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung ke data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Sambung ke lake diurus Dataverse

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih **Tambah sumber data**.

3. Pilih **Microsoft Dataverse** dan pilih **Seterusnya**.

4. Masukkan **Name** untuk sumber data dan kemudian pilih **Seterusnya**. 

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
