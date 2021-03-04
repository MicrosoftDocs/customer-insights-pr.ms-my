---
title: Sambung kepada entiti dalam lake terurus Common Data Service
description: Import data daripada danau data terurus Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267825"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Sambung ke data dalam data lake terurus Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Artikel ini memberikan maklumat tentang cara pelanggan Dynamics 365 boleh bersambung dengan dengan cepat entiti analitis dalam danau terurus Common Data Service. Anda mesti menjadi pentadbir dalam organisasi Common Data Service untuk meneruskan dan melihat senarai entiti yang tersedia dalam danau terurus.

## <a name="important-considerations"></a>Pertimbangan penting

Data disimpan dalam perkhidmatan dalam talian seperti Azure Data Lake Storage, mungkin disimpan di lokasi lain daripada tempat data diproses atau disimpan dalam Dynamics 365 Customer Insights.Dengan mengimport atau menyambung kepada data yang disimpan dalam perkhidmatan dalam talian, anda bersetuju bahawa data boleh dipindahkan ke dan disimpan dengan Dynamics 365 Customer Insights. [Ketahui lebih lanjut di Pusat Amanah Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Sambung ke lake diurus Common Data Service

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih **Tambah sumber data**.

3. Pilih **Sambung ke Common Data Service** dan pilih **Seterusnya**.

4. Masukkan **Name** untuk sumber data dan kemudian pilih **Seterusnya**. Namakan garis panduan: 
   - Bermula dengan huruf.
   - Gunakan huruf dan nombor sahaja. Aksara khas dan ruang idak dibenarkan.
   - Gunakan antara 3 dan 64 aksara.

5. Berikan **Alamat pelayan** untuk organisasi Common Data Service anda dan pilih **Daftar masuk**.

   > [!div class="mx-imgBorder"]
   > ![Kotak dialog untuk memasukkan alamat pelayan Common Data Service](media/enter-CDS-org-details.png)

6. Pilih entiti yang anda mahu inges daripada senarai yang tersedia.    

   > [!NOTE]
   > Jika sesetengah entiti sudah dipilih, ia mungkin akan digunakan oleh aplikasi Dynamics 365 lain (seperti Dynamics 365 Sales Insights atau Customer Service Insights). Anda tidak boleh mengubah pemilihan. Entiti ini akan tersedia sebaik sahaja sumber data dicipta.

   > [!div class="mx-imgBorder"]
   > ![Kotak dialog menunjukkan senarai entiti dalam organisasi Common Data Service](media/select-analytical-entities.png)

7. Simpan pilihan anda untuk mula menyegerakkan entiti yang dipilih ke lake diurus Common Data Service. Anda akan menemui sambungan yang baru ditambah pada halaman **Sumber data**. Ia akan dibariskan untuk segar semula dan menunjukkan entiti dikira sebagai 0 sehingga semua entiti disegerakkan.

Hanya satu sumber data persekitaran boleh secara serentak menggunakan lake terurus Common Data Service yang sama.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Edit sumber data lake diurus Common Data Service

Anda hanya mengedit pemilihan entiti selepas mencipta sumber data. Sebagai contoh, jika entiti tambahan ditambah Common Data Service dan anda mahu mengimportnya juga.    
Untuk mencipta Common Data Service berbeza, [cipta sumber data baharu](#connect-to-a-common-data-service-managed-lake).

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Bersebelahan dengan sumber data yang anda mahu kemas kini, pilih elipsis.

3. Pilih pilihan **Edit** daripada senarai.

4. Pilih entiti tambahan daripada senarai entiti yang tersedia dan pilih **Simpan**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]