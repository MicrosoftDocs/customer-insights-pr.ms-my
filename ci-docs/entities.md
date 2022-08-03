---
title: Entiti dalam Customer Insights
description: Lihat data pada halaman Entiti.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183579"
---
# <a name="entities-in-customer-insights"></a>Entiti dalam Customer Insights

Selepas [mengkonfigurasi sumber data anda](data-sources.md), pergi ke halaman **Entiti** untuk menilai kualiti data yang dimasukkan. Entiti dianggap sebagai set data. Berbilang keupayaan Dynamics 365 Customer Insights dibina sekitar entiti ini. Mengkajinya semula dengan teliti boleh membantu anda mengesahkan output keupayaan tersebut.

Semasa anda bekerja dalam Wawasan Pelanggan memperkayakan data anda atau mencipta segmen, langkah dan aktiviti anda, entiti yang dicipta daripada tindakan tersebut **dipaparkan pada halaman Entiti**.

## <a name="view-a-list-of-entities"></a>Lihat senarai entiti

Pergi ke **Entiti** > **Data** untuk melihat senarai entiti. Maklumat berikut dipaparkan untuk setiap entiti.

- **Nama**: Nama entiti data. Jika anda nampak simbol amaran di sebelah nama entiti, ia bermaksud data untuk entiti tersebut tidak berjaya dimuatkan.
- **Sumber**: Jenis sumber data yang menelan entiti.
- **Dikemas kini**: Masa entiti terakhir dikemas kini.
- **Status**: Butiran mengenai kemas kini terakhir entiti.

## <a name="explore-a-specific-entitys-data"></a>Terokai data entiti khusus

1. Pergi ke **Entiti** > **Data**.
1. Pilih entiti untuk membuka halaman butiran.  
1. Terokai medan dan rekod yang berbeza yang disertakan untuk entiti tersebut.

- Tab **Atribut** dipilih secara lalai dan menunjukkan butiran untuk entiti yang dipilih, seperti nama medan, jenis data dan jenis. Lajur **Jenis** menunjukkan jenis berkaitan Model Data Lazim, yang mana sama ada dikenal pasti secara automatik oleh sistem atau [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis ini ialah jenis semantik yang boleh berbeza daripada jenis data atribut. Contohnya, medan *E-mel* di bawah mempunyai Rentetan *jenis* data tetapi jenis Model Data Biasa (semantik) mungkin *E-mel*, *E-mel* atau *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Jadual medan.":::

   > [!NOTE]
   > Halaman ini hanya menunjukkan sampel data entiti anda. Untuk melihat set data penuh, pergi ke **halaman Sumber data**, pilih entiti, pilih **Edit**, kemudian lihat data entiti ini dengan Power Query editor seperti yang dijelaskan dalam [Sumber data](data-sources.md).

   Untuk mengetahui lebih lanjut tentang data yang ditelan dalam entiti, **lajur Ringkasan** menyediakan beberapa ciri data penting, seperti nol, nilai hilang, nilai unik, kiraan dan pengedaran, apa sahaja yang boleh digunakan untuk data anda. Pilih ikon carta untuk melihat ringkasan data.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Jadual ringkasan data.":::

- Tab **Data** menunjukkan butiran tentang rekod individu entiti. Butiran yang disenaraikan bergantung pada jenis data entiti.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Pilih entiti.":::

- Tab **Laporan** (tersedia untuk sesetengah entiti) membolehkan anda memvisualisasikan data anda dengan mencipta laporan, yang termasuk lajur ini:

  - **Nama laporan**: Nama laporan.
  - **Dicipta oleh**: Nama orang yang mencipta entiti.
  - **Dicipta**: Tarikh dan masa penciptaan entiti.
  - **Diedit oleh**: Nama orang yang mengubah suai entiti.
  - **Diedit**: Tarikh dan masa pengubahsuaian entiti.

## <a name="entity-specific-information"></a>Maklumat entiti tertentu

Bahagian berikut menyediakan maklumat tentang beberapa entiti yang dicipta sistem.

### <a name="corrupted-data-sources"></a>Sumber data rosak

Medan daripada sumber data yang diinges boleh mengandungi data yang rosak. Rekod dengan medan yang rosak terdedah dalam entiti yang dicipta sistem. Mengetahui tentang rekod rosak membantu anda mengenal pasti data yang perlu disemak dan dikemas kini pada sistem sumber. Selepas penyegaran semula sumber data seterusnya, rekod yang dibetulkan diinjes kepada Customer Insights dan diserahkan kepada proses hiliran. 

Sebagai contoh, lajur 'hari jadi' mempunyai jenis data yang ditetapkan sebagai 'tarikh'. Rekod pelanggan mempunyai hari lahir mereka dimasukkan sebagai '01/01/19777'. Sistem akan membenderakan rekod ini sebagai rosak. Seseorang kini boleh menukar hari lahir dalam sistem sumber kepada '1977'. Selepas penyegaran semula sumber data automatik, medan kini mempunyai format yang sah dan rekod akan dialih keluar daripada entiti yang rosak.

Pergi ke **Data** > **Entiti** dan cari entiti yang rosak dalam bahagian **Sistem**. Penamaan skema entiti yang rosak: 'DataSourceName_EntityName_corrupt'. Pilih entiti yang rosak untuk mengenal pasti medan yang rosak dan sebab pada tahap rekod individu.

   :::image type="content" source="media/corruption-reason.png" alt-text="Alasan rasuah.":::

Customer Insights masih memproses rekod yang rosak. Walau bagaimanapun, ia mungkin menyebabkan isu semasa bekerja dengan data disatukan.

Pemeriksaan berikut berjalan pada data yang diinjes untuk mendedahkan rekod rosak:

- Nilai medan tidak sepadan dengan jenis data lajurnya.
- Medan mengandungi aksara yang menyebabkan lajur tidak sepadan dengan skema yang dijangkakan. Sebagai contoh: sebut harga yang diformatkan dengan salah, sebut harga yang tidak dilepaskan atau aksara baris baharu.
- Jika terdapat lajur date/date/datetimeoffset, formatnya perlu ditentukan dalam model jika ia tidak mengikut format ISO standard.

[!INCLUDE [footer-include](includes/footer-banner.md)]
