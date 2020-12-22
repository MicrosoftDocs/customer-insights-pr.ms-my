---
title: Pilih sumber data untuk menginges data
description: Ketahui cara mengimport data daripada pelbagai sumber.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643964"
---
# <a name="overview-about-data-sources"></a>Gambaran keseluruhan tentang sumber data

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Keupayaan wawasan khalayak dalam Dynamics 365 Customer Insights bersambung ke data daripada set sumber yang luas. Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*. Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.

Anda boleh menambah sumber data dalam tiga cara utama:

- [Melalui berpuluh-puluh penyambung Power Query](connect-power-query.md)
- [Daripada folder Common Data Model](connect-common-data-model.md)
- [Daripada lake Common Data Service anda sendiri](connect-common-data-service-lake.md)

> [!NOTE]
> Anda tidak boleh menambah data daripada sumber data di premis lagi.

## <a name="review-ingested-data"></a>Semak data yang ditelan

Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut. Anda boleh mengisih senarai sumber data mengikut setiap lajur.

> [!div class="mx-imgBorder"]
> ![Sumber Data ditambah](media/configure-data-datasource-added.png "Sumber Data ditambah")

|Status  |Penerangan   |
|---------|---------|
|Berjaya   |Sumber data berjaya diinges jika masa disebutkan dalam lajur **Disegar semula**.
|Belum dimulakan   |Sumber data belum mempunyai data diinges atau masih dalam mod draf.         |
|Menyegar semula    |Kemasukan data sedang berjalan. Anda boleh membatalkan operasi ini dengan memilih **Hentikan menyegar semula** di dalam lajur **Tindakan**. Hentikan segar semula sumber data akan kembali ke keadaan segar semula terakhir.       |
|Gagal     |Kemasukan data mempunyai ralat.         |

Pilih **Status segar semula** untuk menyemak lebih banyak butiran tentang status segar semula termasuk butiran ralat dan kemas kini proses hiliran.

Muatan data boleh mengambil masa sedikit. Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**. Untuk maklumat lanjut, lihat [Entiti](entities.md).

## <a name="refresh-a-data-source"></a>Menyegar semula sumber data

Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan. 

Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.

Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:

1. Dalam Insights khalayak, pergi ke **Data** > **Sumber data**

2. Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu segar semula dan pilih **Segar semula** daripada senarai juntai bawah.

3. Sumber data kini dicetuskan untuk segar semula secara manual. Menyegar semula sumber data akan mengemas kini skema entiti serta data untuk semua entiti yang ditentukan dalam sumber data.

4. Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.

## <a name="delete-a-data-source"></a>Padam sumber data

1. Dalam cerapan khalayak, pergi ke **Data** > **Sumber data**.

2. Pilih elipsis menegak bersebelahan dengan sumber data yang anda mahu alih keluar dan pilih **Padam** daripada menu juntai bawah.

3. Sahkan pemadaman anda.
