---
title: Gambaran keseluruhan sumber data
description: Ketahui cara mengimport atau menelan data daripada pelbagai sumber.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610063"
---
# <a name="data-sources-overview"></a>Gambaran keseluruhan sumber data

Dynamics 365 Customer Insights menyediakan sambungan untuk membawa data daripada satu set sumber yang luas. Menyambung kepada sumber data sering dirujukkan sebagai proses *menelan data*. Selepas menelan data, anda boleh [menyatukan](data-unification.md), menjana wawasan dan mengaktifkan data untuk membina pengalaman diperibadikan.

## <a name="add-or-edit-data-sources"></a>Menambah atau mengedit sumber data

Anda boleh melampirkan atau mengimport sumber data ke Wawasan Pelanggan. Pautan di bawah menyediakan arahan tentang menambah dan mengedit sumber data.

**Lampirkan sumber data**

Jika anda mempunyai data yang disediakan dalam salah satu perkhidmatan data Azure Microsoft, Wawasan Pelanggan boleh bersambung ke sumber data dengan mudah tanpa perlu menelan semula data. Pilih salah satu daripada pilihan berikut:
- [Azure Data Lake Storage(fail csv atau parket dalam folder Model Data Biasa)](connect-common-data-model.md)
- [Azure Synapse Analytics(Pangkalan data tasik)](connect-synapse.md)
- [Microsoft Dataverse tasik data](connect-dataverse-managed-lake.md)

**Import dan ubah**

Jika anda menggunakan sumber data pada premis, Microsoft atau data pihak ketiga, import dan ubah data menggunakan Power Query penyambung.
- [Power Query Penyambung](connect-power-query.md)

## <a name="review-data-sources"></a>Menyemak semula sumber data

Jika persekitaran anda telah dikonfigurasikan untuk menggunakan storan Wawasan Pelanggan dan anda menggunakan sumber data pada premis, anda menggunakan Power Platform aliran data. Dengan Power Platform aliran data, anda boleh melihat sumber data kongsi dan sumber data yang diuruskan oleh orang lain. Halaman **Sumber** Data menyenaraikan sumber data dalam tiga seksyen:
- **Dikongsi**: Sumber data yang boleh diuruskan oleh semua pentadbir Wawasan Pelanggan. Power Platform aliran data, akaun storan anda sendiri dan melampirkan ke tasik data terurus Dataverse adalah contoh sumber data yang dikongsi.
- **Diuruskan oleh saya**: Power Platform aliran data yang dicipta dan diuruskan oleh anda sahaja. Pentadbir Wawasan Pelanggan lain hanya boleh melihat aliran data ini tetapi tidak mengedit, menyegar semula atau memadamkannya.
- **Diuruskan oleh orang lain**: Power Platform aliran data yang dicipta oleh pentadbir lain. Anda hanya boleh melihatnya. Ia menyenaraikan pemilik aliran data untuk dihubungi untuk sebarang bantuan.
> [!NOTE]
> Semua entiti boleh dilihat dan digunakan oleh pengguna lain. Walaupun sumber data dimiliki oleh pengguna yang menciptanya, entiti yang terhasil daripada pengingesan data boleh digunakan oleh setiap pengguna Wawasan Pelanggan.

Jika persekitaran anda tidak menggunakan Power Platform aliran data, **halaman Sumber** Data hanya mengandungi senarai semua sumber data. Tiada paparan seksyen.

## <a name="manage-existing-data-sources"></a>Menguruskan sumber data sedia ada

Pergi ke **Sumber** > **Data Data** untuk melihat nama setiap sumber data yang ditelan, statusnya dan kali terakhir data disegar semula untuk sumber tersebut. Anda boleh mengisih senarai sumber data mengikut sebarang lajur atau menggunakan kotak carian untuk mencari sumber data yang anda ingin uruskan.

Pilih sumber data untuk melihat tindakan yang tersedia.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Sumber data ditambah.":::

- [**Edit**](#add-or-edit-data-sources) sumber data untuk mengubah sifatnya.
- [**Menyegar semula**](#refresh-data-sources) sumber data untuk memasukkan data terkini.
- [**Memperkayakan**](data-sources-enrichment.md) sumber data sebelum penyatuan.
- **Padamkan** sumber data. Sumber data boleh dipadamkan hanya jika data tidak digunakan dalam sebarang pemprosesan seperti penyatuan, wawasan, pengaktifan atau eksport.

## <a name="refresh-data-sources"></a>Segar semula sumber data

Sumber data boleh disegar semula mengikut jadual automatik atau disegar semula secara manual berdasarkan permintaan. [Sumber](connect-power-query.md#add-data-from-on-premises-data-sources) data pada premis menyegar semula jadual mereka sendiri yang disediakan semasa pengingesan data. Untuk petua penyelesaian masalah, lihat [Menyelesaikan masalah isu Power Query segar semula sumber data berasaskan PPDF](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Untuk sumber data yang dilampirkan, pengingesan data menggunakan data terkini yang tersedia daripada sumber data tersebut.

Pergi ke **Jadual** > **Sistem** > [**Pentadbir**](schedule-refresh.md) untuk mengkonfigurasikan segar semula berjadual sistem bagi sumber data tertelan anda.

Untuk menyegar semula sumber data atas permintaan:

1. Pergi **Data** > **Sumber data**.

1. Pilih sumber data yang anda ingin segar semula dan pilih **Segar Semula**. Sumber data kini dicetuskan untuk segar semula secara manual. Menyegarkan semula sumber data akan mengemas kini kedua-dua skema entiti dan data untuk semua entiti yang dinyatakan dalam sumber data.

1. Pilih status untuk membuka **anak tetingkap butiran** Kemajuan dan lihat kemajuan. Untuk membatalkan tugas, pilih **Batalkan kerja** di bahagian bawah anak tetingkap.

## <a name="corrupt-data-sources"></a>Sumber data rasuah

Data yang ditelan mungkin mempunyai rekod rasuah yang boleh menyebabkan proses pengambilan data selesai dengan kesilapan atau amaran.

> [!NOTE]
> Jika pengingesan data selesai dengan ralat, pemprosesan seterusnya (seperti penyatuan atau penciptaan aktiviti) yang memanfaatkan sumber data ini akan dilangkau. Sekiranya pengingesan selesai dengan amaran, pemprosesan berikutnya berterusan tetapi beberapa rekod mungkin tidak disertakan.

Ralat ini boleh dilihat dalam butiran tugas.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Butiran tugas menunjukkan ralat data yang rosak.":::

Rekod rasuah ditunjukkan dalam entiti yang dicipta oleh sistem.

### <a name="fix-corrupt-data"></a>Betulkan data yang rosak

1. Untuk melihat data yang rosak, pergi ke **Entiti** > **Data** dan cari entiti yang rosak di bahagian **Sistem**. Skema penamaan entiti yang rosak: 'DataSourceName_EntityName_corrupt'.

1. Pilih entiti yang rosak kemudian tab **Data**.

1. Kenal pasti bidang rasuah dalam rekod dan sebabnya.

   :::image type="content" source="media/corruption-reason.png" alt-text="Sebab rasuah." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Entiti** > **Data** hanya menunjukkan sebahagian daripada rekod rasuah. Untuk melihat semua rekod rasuah, eksport fail ke bekas dalam akaun storan menggunakan [proses](export-destinations.md) eksport Wawasan Pelanggan. Jika anda menggunakan akaun storan anda sendiri, anda juga boleh melihat folder Wawasan Pelanggan dalam akaun storan anda.

1. Betulkan data yang rosak. Contohnya, untuk sumber data Azure Data Lake, [betulkan data dalam Storan Tasik Data atau kemas kini jenis data dalam fail](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data) manifest/model.json. Untuk Power Query sumber data, betulkan data dalam fail sumber dan [betulkan jenis data langkah](connect-power-query.md#data-type-does-not-match-data) transformasi pada **Power Query halaman Edit pertanyaan**.

Selepas penyegaran semula sumber data seterusnya, rekod yang dibetulkan diinjes kepada Customer Insights dan diserahkan kepada proses hiliran.

Sebagai contoh, lajur 'hari jadi' mempunyai jenis data yang ditetapkan sebagai 'tarikh'. Rekod pelanggan mempunyai hari lahir mereka dimasukkan sebagai '01/01/19777'. Sistem ini menandakan rekod ini sebagai rasuah. Tukar hari lahir dalam sistem sumber kepada '1977'. Selepas segar semula sumber data automatik, medan kini mempunyai format yang sah dan rekod dialih keluar daripada entiti yang rosak.

[!INCLUDE [footer-include](includes/footer-banner.md)]
