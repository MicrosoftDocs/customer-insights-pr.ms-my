---
title: Pilih sumber data untuk menginges data
description: Ketahui cara mengimport data daripada pelbagai sumber.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643060"
---
# <a name="data-sources-overview"></a>Gambaran keseluruhan sumber data



Dynamics 365 Customer Insights menyambung ke data dari set sumber yang luas. Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*. Selepas menelan data, anda boleh [menyatukan](data-unification.md) dan mengambil tindakan ke atasnya.

## <a name="add-a-data-source"></a>Tambahkan sumber data

Rujuk artikel terperinci tentang cara menambah sumber data, bergantung pada pilihan yang anda pilih.

Anda boleh menambah sumber data berikut:

- [Melalui berpuluh-puluh Power Query penyambung](connect-power-query.md)
- [Daripada folder Common Data Model](connect-common-data-model.md)
- [Daripada lake Microsoft Dataverse anda sendiri](connect-dataverse-managed-lake.md)
- [Azure Synapse Analytics Daripada pangkalan data](connect-synapse.md)

> [!NOTE]
> Jika anda menggunakan versi percubaan, seksyen kaedah import termasuk **opsyen pustaka** data Wawasan Pelanggan. Pilih opsyen ini untuk memilih set data sampel yang tersedia untuk pelbagai industri. Untuk maklumat lanjut, lihat [Dynamics 365 Customer Insights percubaan](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Tambah data daripada sumber data di premis

Pengambilan data daripada sumber data di premis disokong berdasarkan Microsoft Power Platform aliran data. Anda boleh mendayakan Aliran Data dalam Wawasan Pelanggan dengan [menyediakan Microsoft Dataverse URL](create-environment.md) persekitaran semasa menyediakan persekitaran.

Sumber data yang dicipta selepas mengaitkan Dataverse persekitaran dengan Wawasan Pelanggan menggunakan [Power Platform aliran](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) data secara lalai. Aliran data menyokong kesambungan di premis menggunakan get laluan data. Anda boleh mengalih keluar dan mencipta semula sumber data yang Dataverse wujud sebelum persekitaran dikaitkan [menggunakan get laluan](/data-integration/gateway/service-gateway-app) data di premis.

Get laluan data daripada persekitaran Power BI atau Power Apps sedia ada akan kelihatan dan anda boleh menggunakan semula dalam Customer Insights. Halaman sumber data menunjukkan pautan untuk pergi ke persekitaran Microsoft Power Platform yang anda boleh melihat dan mengkonfigurasikan get laluan data di premis.

> [!IMPORTANT]
> Pastikan get laluan anda dikemas kini kepada versi terkini. Anda boleh memasang kemas kini dan mengkonfigurasi semula get laluan daripada gesaan yang ditunjukkan pada skrin get laluan secara langsung atau [memuat turun versi](https://powerapps.microsoft.com/downloads/) terkini. Jika anda tidak menggunakan versi get laluan terkini, segar semula aliran data gagal dengan mesej ralat seperti **Kata kunci tidak disokong: sifat konfigurasi. Nama parameter: kata kunci**.

## <a name="review-ingested-data"></a>Semak data yang ditelan
Jika persekitaran anda mengandungi Power Platform aliran data, **halaman Sumber** Data menyenaraikan tiga bahagian: 
- **Dikongsi**: Sumber data yang boleh diuruskan oleh semua pentadbir Wawasan Pelanggan. Power BI aliran data, akaun storan anda sendiri, dan melampirkan ke tasik data terurus Dataverse adalah contoh sumber data yang dikongsi.
- **Diuruskan oleh saya**: Power Platform aliran data dicipta dan boleh diuruskan hanya oleh anda. Pentadbir Wawasan Pelanggan yang lain hanya boleh melihat aliran data ini tetapi tidak mengedit, menyegar semula atau memadamkannya.
- **Diuruskan oleh orang lain**: Power Platform aliran data yang dicipta oleh pentadbir lain. Anda hanya boleh melihatnya. Ia menyenaraikan pemilik aliran data untuk menghubungi sebarang bantuan.
> [!NOTE]
> Semua entiti boleh dilihat dan digunakan oleh pengguna lain. Kontekstualiti pengguna hanya terpakai kepada sumber data dan bukan kepada entiti yang terhasil daripada aliran data ini.

Jika tiada Power Platform aliran data digunakan, anda tidak akan melihat sebarang kumpulan atau bahagian. Halaman **Sumber** Data hanya mengandungi senarai semua sumber data.

Anda akan melihat nama setiap sumber data yang ditelan, status dan masa terakhir data disegar semula untuk sumber tersebut. Anda boleh mengisih senarai sumber data mengikut setiap lajur.

> [!div class="mx-imgBorder"]
> ![Sumber data ditambah.](media/configure-data-datasource-added.png "Sumber Data ditambah")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**. Untuk maklumat lanjut, lihat [Entiti](entities.md).

## <a name="refresh-a-data-source"></a>Menyegar semula sumber data

Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan. 

Pergi ke **Pentadbir** > **Sistem** > [**Jadual**](system.md#schedule-tab) untuk mengkonfigurasi segar semula yang dijadualkan bagi semua sumber data anda yang diinges.

Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:

1. Pergi **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda segar semula dan pilih **Segar semula** daripada senarai juntai bawah.

3. Sumber data kini dicetuskan untuk segar semula secara manual. Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.

4. Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.

## <a name="delete-a-data-source"></a>Padam sumber data

1. Pergi **Data** > **Sumber data**.

2. Pilih elipsis menegak di sebelah sumber data yang ingin anda alih keluar dan pilih **Padam** daripada menu juntai bawah.

3. Sahkan pemadaman anda.


[!INCLUDE [footer-include](includes/footer-banner.md)]
