---
title: Entiti dalam Customer Insights
description: Lihat data pada halaman Entiti.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610109"
---
# <a name="entities-in-customer-insights"></a>Entiti dalam Customer Insights

Selepas [mengkonfigurasi sumber data anda](data-sources.md), pergi ke halaman **Entiti** untuk menilai kualiti data yang dimasukkan. Entiti dianggap sebagai set data. Berbilang keupayaan Dynamics 365 Customer Insights dibina sekitar entiti ini. Mengkajinya semula dengan teliti boleh membantu anda mengesahkan output keupayaan tersebut.

Semasa anda bekerja dalam Wawasan Pelanggan yang memperkayakan data anda atau mencipta segmen, ukuran dan aktiviti, entiti yang dicipta daripada tindakan tersebut dipaparkan pada **halaman Entiti**.

## <a name="view-a-list-of-entities"></a>Lihat senarai entiti

Pergi ke **Entiti** > **Data** untuk melihat senarai entiti. Maklumat berikut dipaparkan untuk setiap entiti.

- **Nama**: Nama entiti data. Jika anda nampak simbol amaran di sebelah nama entiti, ia bermaksud data untuk entiti tersebut tidak berjaya dimuatkan.
- **Sumber**: Jenis sumber data yang menelan entiti.
- **Dikemas kini**: Masa entiti terakhir dikemas kini.
- **Status**: Butiran mengenai kemas kini terakhir entiti.

## <a name="explore-a-specific-entitys-data"></a>Terokai data entiti khusus

1. Pergi ke **Entiti** > **Data**.
1. Pilih entiti untuk membuka halaman butiran.  
1. Terokai bidang dan rekod yang berbeza yang disertakan untuk entiti tersebut.

- Tab **Atribut** dipilih secara lalai dan menunjukkan butiran untuk entiti yang dipilih, seperti nama medan, jenis data dan jenis. Lajur **Jenis** menunjukkan jenis berkaitan Model Data Lazim, yang mana sama ada dikenal pasti secara automatik oleh sistem atau [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis ini ialah jenis semantik yang boleh berbeza daripada jenis data atribut. Contohnya, medan *E-mel* di bawah mempunyai jenis *data Rentetan* tetapi jenis Model Data Biasa (semantik) mungkin *E-mel,* E-mel *atau* *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Jadual medan.":::

   > [!NOTE]
   > Halaman ini menunjukkan sampel data entiti anda sahaja. Untuk melihat set data penuh, pergi ke **halaman Sumber data**, pilih entiti, pilih **Edit**, kemudian lihat data entiti ini dengan Power Query editor seperti yang dijelaskan dalam [Sumber](data-sources.md) data.

   Untuk mengetahui lebih lanjut tentang data yang ditelan dalam entiti, **lajur Ringkasan** menyediakan beberapa ciri data penting, seperti nol, nilai hilang, nilai unik, kiraan dan pengedaran, apa sahaja yang berkenaan dengan data anda. Pilih ikon carta untuk melihat ringkasan data.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Jadual ringkasan data.":::

- Tab **Data** menunjukkan butiran tentang rekod individu entiti. Butiran yang disenaraikan bergantung pada jenis data entiti.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Pilih entiti.":::

- Tab **Laporan** (tersedia untuk sesetengah entiti) membolehkan anda menggambarkan data anda dengan mencipta laporan, yang termasuk lajur ini:

  - **Nama laporan**: Nama laporan.
  - **Dicipta oleh**: Nama orang yang mencipta entiti.
  - **Dicipta**: Tarikh dan masa penciptaan entiti.
  - **Diedit oleh**: Nama orang yang mengubah suai entiti.
  - **Diedit**: Tarikh dan masa pengubahsuaian entiti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
