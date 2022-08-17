---
title: Gambaran keseluruhan sumber data
description: Ketahui cara mengimport atau menelan data daripada pelbagai sumber.
ms.date: 07/26/2022
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
ms.openlocfilehash: 591353bf1ba2f9ca05ddd137e1cf29dc0b0fba97
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245660"
---
# <a name="data-sources-overview"></a>Gambaran keseluruhan sumber data

Dynamics 365 Customer Insights menyediakan sambungan untuk membawa data daripada set sumber yang luas. Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*. Selepas menelan data, anda boleh [menyatukan](data-unification.md), menjana cerapan dan mengaktifkan data untuk membina pengalaman yang diperibadikan.

## <a name="add-or-edit-data-sources"></a>Menambah atau mengedit sumber data

Anda boleh melampirkan atau mengimport sumber data ke dalam Wawasan Pelanggan. Pautan di bawah memberikan arahan untuk menambah dan mengedit sumber data.

**Lampirkan sumber data**

Jika anda mempunyai data yang disediakan dalam salah satu perkhidmatan data Azure Microsoft, Wawasan Pelanggan boleh menyambung dengan mudah ke sumber data tanpa perlu menelan semula data. Pilih salah satu daripada pilihan berikut:
- [Azure Data Lake Storage(fail csv atau parket dalam folder Model Data Biasa)](connect-common-data-model.md)
- [Azure Synapse Analytics(Pangkalan data Lake)](connect-synapse.md)
- [Microsoft Dataverse tasik data](connect-dataverse-managed-lake.md)

**Import dan ubah**

Jika anda menggunakan sumber data pada premis, Microsoft atau data pihak ketiga, import dan ubah data menggunakan Power Query penyambung.
- [Power Query Penyambung](connect-power-query.md)

## <a name="review-data-sources"></a>Semak semula sumber data

Jika persekitaran anda dikonfigurasikan untuk menggunakan storan Wawasan Pelanggan dan anda menggunakan sumber data pada premis, anda menggunakan Power Platform aliran data. Dengan Power Platform aliran data, anda boleh melihat sumber data dikongsi dan sumber data yang diuruskan oleh orang lain. Halaman **Sumber** Data menyenaraikan sumber data dalam tiga bahagian:
- **Dikongsi**: Sumber data yang boleh diuruskan oleh semua pentadbir Wawasan Pelanggan. Power Platform aliran data, akaun storan anda sendiri dan melampirkan ke tasik data yang diuruskan adalah contoh sumber data yang Dataverse dikongsi.
- **Diuruskan oleh saya**: Power Platform aliran data dicipta dan diuruskan hanya oleh anda. Pentadbir Wawasan Pelanggan yang lain hanya boleh melihat aliran data ini tetapi tidak mengedit, menyegar semula atau memadamkannya.
- **Diuruskan oleh orang lain**: Power Platform aliran data yang dicipta oleh pentadbir lain. Anda hanya boleh melihatnya. Ia menyenaraikan pemilik aliran data untuk dihubungi untuk sebarang bantuan.
> [!NOTE]
> Semua entiti boleh dilihat dan digunakan oleh pengguna lain. Walaupun sumber data dimiliki oleh pengguna yang menciptanya, entiti yang terhasil daripada pengingesan data boleh digunakan oleh setiap pengguna Wawasan Pelanggan.

Jika persekitaran anda tidak menggunakan Power Platform aliran data, **halaman Sumber** Data hanya mengandungi senarai semua sumber data. Tiada paparan seksyen.

## <a name="manage-existing-data-sources"></a>Menguruskan sumber data sedia ada

Pergi ke **sumber** > **Data Data** untuk melihat nama setiap sumber data yang ditelan, statusnya dan kali terakhir data disegar semula untuk sumber tersebut. Anda boleh mengisih senarai sumber data mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari sumber data yang anda ingin uruskan.

Pilih sumber data untuk melihat tindakan yang tersedia.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Sumber data ditambah.":::

- [**Edit**](#add-or-edit-data-sources) sumber data untuk menukar sifatnya.
- [**Segar semula**](#refresh-data-sources) sumber data untuk memasukkan data terkini.
- [**Memperkayakan**](data-sources-enrichment.md) sumber data sebelum penyatuan.
- **Hapuskan** sumber data. Soalan sumber data boleh dipadamkan hanya jika data tidak digunakan dalam sebarang pemprosesan seperti penyatuan, cerapan, pengaktifan atau eksport.

## <a name="refresh-data-sources"></a>Segar semula sumber data

Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan. [Sumber](connect-power-query.md#add-data-from-on-premises-data-sources) data pada premis menyegar semula jadual mereka sendiri yang disediakan semasa pengambilan data. Untuk sumber data yang dilampirkan, pengingesan data menggunakan data terkini yang tersedia dari sumber data tersebut.

Pergi ke **Jadual** > **Sistem** > [**Pentadbir**](schedule-refresh.md) untuk mengkonfigurasikan segar semula berjadual sistem bagi sumber data anda yang ditelan.

Untuk menyegarkan sumber data atas permintaan:

1. Pergi **Data** > **Sumber data**.

1. Pilih sumber data anda mahu segar semula dan pilih **Segar Semula**. Sumber data kini dicetuskan untuk segar semula secara manual. Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.

1. Pilih status untuk membuka **anak tetingkap Butiran** kemajuan dan lihat kemajuan. Untuk membatalkan kerja, pilih **Batalkan kerja** di bahagian bawah anak tetingkap.

[!INCLUDE [footer-include](includes/footer-banner.md)]
