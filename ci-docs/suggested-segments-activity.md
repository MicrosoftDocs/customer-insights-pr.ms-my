---
title: Segmen yang dicadangkan berdasarkan aktiviti (pratonton)
description: Biarkan pembelajaran mesin membantu anda mencari segmen baharu dan segmen yang menarik berdasarkan aktiviti pelanggan.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170600"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmen yang dicadangkan berdasarkan aktiviti (pratonton)

Terokai segmen yang menarik bagi pelanggan anda berdasarkan pada data aktiviti pelanggan yang diinges ke Customer Insights. Contoh data aktiviti ialah transaksi, tempoh panggilan sokongan, pembelian atau pulangan. Untuk mencadangkan segmen, data aktiviti akan dianalisis untuk keterkinian, kekerapan dan nilai kewangan (atau tempoh). Sebagai alternatif, anda boleh menjana [segmen yang dicadangkan untuk meningkatkan ukuran atau pemahaman yang lebih baik tentang perkara yang mempengaruhi atribut](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Tab segmen yang dicadangkan menunjukkan cadangan segmen untuk segmen berasaskan aktiviti dan berasaskan atribut.":::

## <a name="categorize-customers-by-activity"></a>Kategorikan pelanggan mengikut aktiviti

Dengan [data aktiviti](activities.md) tersedia dalam Customer Insights, kami boleh menjana cadangan yang mewakili kumpulan pelanggan:

- pelanggan yang paling aktif 
- pelanggan yang telah membuat pembelian paling banyak 
- pelanggan yang menjana hasil paling banyak 
- pelanggan yang belum aktif sejak kebelakangan ini 
- pelanggan yang kerap berinteraksi dengan perniagaan anda  

Jika anda mempunyai perniagaan runcit, anda boleh mengetahui pelanggan yang menjana hasil dan ganjaran mereka paling banyak dengan kupon. Atau anda boleh mengenal pasti pelanggan sekali-sekala dan menawarkan mereka menyertai program ganjaran supaya mereka melawat perniagaan anda dengan lebih kerap.
Jika anda menyediakan penjagaan kesihatan awam dan matlamat anda adalah untuk meminimumkan perbelanjaan untuk pesakit individu, anda boleh cuba mengurangkan lawatan berulang dengan menyediakan penjagaan yang terbaik dalam beberapa lawatan yang mungkin. Dalam kes ini, matlamat anda ialah untuk memastikan kekerapan lawatan rendah dan meminimumkan kos berulang untuk pesakit. Atau anda boleh mengenal pasti segmen pesakit yang mempunyai janji temu yang kerap dan kos berulang yang tinggi dan menganalisis kes ini untuk meningkatkan rawatan individu.

## <a name="required-data"></a>Data diperlukan

Cadangan dijana berdasarkan pada data input yang dipilih.

- Profil pelanggan: Semua pelanggan atau ahli segmen tertentu.

- Tempoh masa: Bulan lepas, tahun lepas atau sebarang tempoh masa tersuai.

- Jenis aktiviti: pembelian, transaksi runcit, transaksi dalam talian, kes sokongan pelanggan, langganan dan sebagainya.  

- Entiti dalam Customer Insights yang mengandungi data aktiviti: Entiti UnifiedActivity atau entiti untuk aktiviti tertentu.

- Dimensi untuk dimasukkan: Keterkinian, kekerapan atau dimensi kewangan bergantung pada keperluan perniagaan anda.

## <a name="generate-suggested-segments"></a>Menjana segmen yang dicadangkan

1. Pergi ke **Segmen** dan pilih **tab Cadangan (pratonton**).

1. Pilih **Cari cadangan baharu** dan pilih **Lihat atau jangkakan tingkah laku pelanggan**. Pilih **Mula**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Langkah pertama bagi wizard konfigurasi untuk segmen yang dicadangkan berdasarkan pada aktiviti.":::

1. Sediakan data input yang diperlukan dan pilih **Seterusnya**.

   - Pilih pelanggan: termasuk semua pelanggan atau segmen tertentu.
   - Pilih aktiviti: Pilih jenis aktiviti dan entiti yang menerangkan aktiviti.
   - Keutamaan: Tetapkan tempoh masa untuk mempertimbangkan faktor bagi cadangan dan petakan atribut.

1. Semak input anda dan pilih **Jalankan** untuk menjalankan model dan menjana cadangan.

Bergantung pada bilangan profil pelanggan dan aktiviti yang dipilih, ini boleh mengambil masa beberapa minit untuk diselesaikan.

Selepas menjana cadangan, anda boleh menapis dengan mengikut dimensi atau nilai yang paling menarik minat anda.

## <a name="manage-suggested-segments"></a>Urus segmen yang dicadangkan

Pergi ke **Segmen** dan pilih **tab Cadangan (pratonton**). Dalam seksyen **Cadangan** berasaskan aktiviti, pilih segmen yang dicadangkan untuk melihat tindakan yang tersedia.

- **Lihat cadangan** untuk melihat butiran segmen tersebut seperti tahap setiap dimensi berbanding dengan kumpulan sasaran. Ia juga menyerlahkan bilangan ahli yang berpotensi dalam segmen dan peratusan yang bersamaan dengan jumlah pelanggan.
- **Buat segmen** untuk menyimpan yang dicadangkan sebagai segmen. Ia dipaparkan pada **tab Semua segmen** dan boleh [disegar semula atau dipadamkan](segments.md). Anda tidak boleh mengedit butiran segmen. Walau bagaimanapun, anda boleh mengubah kriteria input untuk cadangan dan menjana cadangan yang berbeza.
- **Edit cadangan** untuk mengubah suai atribut yang dikonfigurasi yang akan menggantikan cadangan semasa.
- **Segar semula cadangan** untuk menyegar semula cadangan sambil mengekalkan atribut yang dikonfigurasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
