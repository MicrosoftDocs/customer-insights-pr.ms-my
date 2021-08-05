---
title: Pilih sumber data untuk menginges data
description: Ketahui cara mengimport data daripada pelbagai sumber.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 0a017a37777adaaf7de079cf481ec10c70c7adba
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692446"
---
# <a name="data-sources-overview"></a>Gambaran keseluruhan sumber data

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Keupayaan wawasan khalayak dalam Dynamics 365 Customer Insights bersambung ke data daripada set sumber yang luas. Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*. Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.

Anda boleh menambah sumber data dalam tiga cara utama:

- [Melalui berpuluh-puluh penyambung Power Query](connect-power-query.md)
- [Daripada folder Common Data Model](connect-common-data-model.md)
- [Daripada lake Microsoft Dataverse anda sendiri](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Tambah data daripada sumber data di premis

Pengingesan data daripada sumber data di premis dalam cerapan Khalayak disokong berdasarkan pada aliran data Microsoft Power Platform. Aliran data boleh didayakan dalam Customer Insights dengan [menyediakan URL persekitaran Microsoft Dataverse](get-started-paid.md) semasa menyediakan persekitaran.

Sumber data yang dicipta selepas mengaitkan persekitaran Dataverse dengan Customer Insights akan menggunakan aliran data [Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) secara lalai. Aliran data menyokong kesambungan di premis menggunakan get laluan data. Alih keluar dan cipta semula sumber data yang wujud sebelum persekitaran Dataverse  dikaitkan ke [guna get laluan data di premis](/data-integration/gateway/service-gateway-app).

Get laluan data daripada persekitaran Power BI atau Power Apps sedia ada akan kelihatan dan anda boleh menggunakan semula dalam Customer Insights. Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Microsoft Power Platform yang anda boleh melihat dan mengkonfigurasikan get laluan data di premis.

## <a name="review-ingested-data"></a>Semak data yang ditelan

Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut. Anda boleh mengisih senarai sumber data mengikut setiap lajur.

> [!div class="mx-imgBorder"]
> ![Sumber data ditambah.](media/configure-data-datasource-added.png "Sumber Data ditambah")

|Status  |Penerangan  |
|---------|---------|
|Berjaya   |Sumber data berjaya diinges jika masa disebutkan dalam lajur **Disegar semula**.
|Belum dimulakan   |Sumber data belum mempunyai data diinges atau masih dalam mod draf.         |
|Menyegar semula    |Kemasukan data sedang berjalan. Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**. Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.       |
|Gagal     |Kemasukan data mempunyai ralat.         |

Pilih nilai dalam lajur **Status** bagi sebarang sumber data untuk menyemak butiran lanjut. Dalam anak tetingkap **Butiran kemajuan**, kembangkan **Sumber data**. Pilih **Lihat butiran** untuk maklumat lanjut tentang status segar semula termasuk butiran ralat dan kemas kini proses hiliran.

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**. Untuk maklumat lanjut, lihat [Entiti](entities.md).

## <a name="refresh-a-data-source"></a>Menyegar semula sumber data

Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan. 

Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.

Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda segar semula dan pilih **Segar semula** daripada senarai juntai bawah.

3. Sumber data kini dicetuskan untuk segar semula secara manual. Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.

4. Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.

## <a name="delete-a-data-source"></a>Padam sumber data

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda alih keluar dan pilih **Padam** daripada menu juntai bawah.

3. Sahkan pemadaman anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
