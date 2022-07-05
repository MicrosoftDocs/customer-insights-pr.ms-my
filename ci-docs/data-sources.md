---
title: Gambaran keseluruhan sumber data
description: Ketahui cara mengimport atau menelan data daripada pelbagai sumber.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: fbe44f655bdbc20ef7f0956022395e2dcb570adf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051464"
---
# <a name="data-sources-overview"></a>Gambaran keseluruhan sumber data

Dynamics 365 Customer Insights menyediakan sambungan untuk membawa data daripada set sumber yang luas. Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*. Selepas menelan data, anda boleh [menyatukan](data-unification.md), menjana cerapan dan mengaktifkan data untuk membina pengalaman yang diperibadikan.

## <a name="add-data-sources"></a>Tambah sumber data

Anda boleh melampirkan atau mengimport sumber data ke dalam Wawasan Pelanggan. Pautan di bawah memberikan arahan untuk menambah sumber data.

**Lampirkan sumber data**

Jika anda mempunyai data yang disediakan dalam salah satu perkhidmatan data Azure Microsoft, Wawasan Pelanggan boleh menyambung ke sumber data dengan mudah tanpa perlu menelan semula data. Pilih salah satu daripada pilihan berikut:
- [Azure Data Lake Storage(fail csv atau parket dalam folder Model Data Biasa)](connect-common-data-model.md)
- [Azure Synapse Analytics(Pangkalan data Lake)](connect-synapse.md)
- [Microsoft Dataverse tasik data](connect-dataverse-managed-lake.md)

**Import dan ubah**

Jika anda menggunakan sumber data pada premis, Microsoft atau data pihak ketiga, import dan ubah data menggunakan Power Query penyambung.
- [Power Query Penyambung](connect-power-query.md)

## <a name="review-data-sources"></a>Semak sumber data

Jika persekitaran anda dikonfigurasikan untuk menggunakan storan Wawasan Pelanggan dan anda menggunakan sumber data pada premis, anda menggunakan Power Platform aliran data. Dengan Power Platform aliran data, anda boleh melihat sumber data dan sumber data yang dikongsi yang diuruskan oleh orang lain. Halaman **Sumber** Data menyenaraikan sumber data dalam tiga bahagian:
- **Dikongsi**: Sumber data yang boleh diuruskan oleh semua pentadbir Wawasan Pelanggan. Power Platform aliran data, akaun storan anda sendiri, dan melampirkan ke tasik data terurus Dataverse adalah contoh sumber data yang dikongsi.
- **Diuruskan oleh saya**: Power Platform aliran data yang dibuat dan diuruskan hanya oleh anda. Pentadbir Wawasan Pelanggan yang lain hanya boleh melihat aliran data ini tetapi tidak mengedit, menyegar semula atau memadamkannya.
- **Diuruskan oleh orang lain**: Power Platform aliran data yang dicipta oleh pentadbir lain. Anda hanya boleh melihatnya. Ia menyenaraikan pemilik aliran data untuk menghubungi sebarang bantuan.
> [!NOTE]
> Semua entiti boleh dilihat dan digunakan oleh pengguna lain. Walaupun sumber data dimiliki oleh pengguna yang menciptanya, entiti yang terhasil daripada pengambilan data boleh digunakan oleh setiap pengguna Wawasan Pelanggan.

Jika persekitaran anda tidak menggunakan Power Platform aliran data, **halaman Sumber** Data hanya mengandungi senarai semua sumber data. Tiada bahagian dipaparkan.

Pergi ke **sumber** > **Data Data** untuk melihat nama setiap sumber data yang ditelan, statusnya dan kali terakhir data disegar semula untuk sumber tersebut. Anda boleh mengisih senarai sumber data mengikut setiap lajur.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Sumber data ditambah.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Memuatkan data boleh mengambil masa. Selepas segar semula berjaya, data yang dimasukkan boleh disemak daripada halaman **Entiti**. Untuk maklumat lanjut, lihat [Entiti](entities.md).

## <a name="refresh-data-sources"></a>Segar semula sumber data

Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan. [Sumber](connect-power-query.md#add-data-from-on-premises-data-sources) data di premis menyegarkan semula jadual mereka sendiri yang disediakan semasa pengambilan data. Untuk sumber data yang dilampirkan, pengambilan data menggunakan data terkini yang tersedia daripada sumber data tersebut.

Pergi ke **Jadual** > **Sistem** > [**Pentadbir**](system.md#schedule-tab) untuk mengkonfigurasi segar semula berjadual sistem sumber data anda yang ditelan.

Untuk menyegar semula sumber data mengikut permintaan, ikuti langkah ini:

1. Pergi **Data** > **Sumber data**.

1. Pilih elipsis menegak (&vellip;) di sebelah sumber data yang anda ingin segar semula dan pilih **Segar Semula** daripada senarai juntai bawah. Sumber data kini dicetuskan untuk segar semula secara manual. Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.

1. Pilih **Berhenti menyegar semula** jika anda mahu membatalkan segar semula sedia ada dan sumber data akan bertukar kembali ke status segar semula terakhir.

## <a name="delete-a-data-source"></a>Padam sumber data

Satu sumber data boleh dipadamkan hanya jika data tidak digunakan dalam sebarang pemprosesan seperti penyatuan, cerapan, pengaktifan atau eksport.

1. Pergi **Data** > **Sumber data**.

2. Pilih elipsis menegak (&vellip;) di sebelah sumber data yang anda mahu alih keluar dan pilih **Padam** daripada menu juntai bawah.

3. Sahkan pemadaman anda.


[!INCLUDE [footer-include](includes/footer-banner.md)]
