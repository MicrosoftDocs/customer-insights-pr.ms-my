---
title: Segmen yang dicadangkan berdasarkan pada aktiviti.
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
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354474"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmen yang dicadangkan berdasarkan pada aktiviti (pratonton)

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
Jika anda dalam perniagaan penjagaan kesihatan yang menyediakan penjagaan kesihatan awam dan matlamat anda ialah untuk meminimumkan perbelanjaan bagi pesakit individu. Satu cara untuk berbuat demikian berkemungkinan dengan mengurangkan lawatan berulang yang menyediakan penjagaan terbaik sebaik mungkin dalam kunjungan sekurang mungkin. Dalam kes ini, matlamat anda ialah untuk memastikan kekerapan lawatan rendah dan meminimumkan kos berulang untuk pesakit. Atau anda boleh mengenal pasti segmen pesakit yang mempunyai janji temu yang kerap dan kos berulang yang tinggi dan menganalisis kes ini untuk meningkatkan rawatan individu. 

## <a name="required-data"></a>Data diperlukan

Cadangan dijana berdasarkan pada data input yang dipilih. 

- Profil pelanggan: Semua pelanggan atau ahli segmen tertentu. 

- Tempoh masa: Bulan lepas, tahun lepas atau sebarang tempoh masa tersuai.

- Jenis aktiviti: pembelian, transaksi runcit, transaksi dalam talian, kes sokongan pelanggan, langganan dan sebagainya.  

- Entiti dalam Customer Insights yang mengandungi data aktiviti: Entiti UnifiedActivity atau entiti untuk aktiviti tertentu. 

- Dimensi untuk dimasukkan: Keterkinian, kekerapan atau dimensi kewangan bergantung pada keperluan perniagaan anda.

## <a name="generate-suggested-segments"></a>Menjana segmen yang dicadangkan

1. Pergi ke **Segmen**.

1. Pilih tab **Cadangan (pratonton)**.

1. Pilih **Cari cadangan baharu** dan pilih **Lihat atau jangkakan tingkah laku pelanggan**. Pilih **Mula** untuk menjalankan pengalaman berpandu.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Langkah pertama bagi wizard konfigurasi untuk segmen yang dicadangkan berdasarkan pada aktiviti.":::

1. Sediakan data input yang diperlukan dan pilih **Seterusnya** teruskan.

   - Pilih pelanggan: termasuk semua pelanggan atau segmen tertentu.
   - Pilih aktiviti: Pilih jenis aktiviti dan entiti yang menerangkan aktiviti.
   - Keutamaan: Tetapkan tempoh masa untuk mempertimbangkan faktor bagi cadangan dan petakan atribut.

1. Semak input anda dan pilih **Jalankan** untuk menjalankan model dan menjana cadangan.

1. Bergantung pada bilangan profil pelanggan dan aktiviti yang dipilih, ini boleh mengambil masa beberapa minit untuk diselesaikan. 

Selepas menjana cadangan, anda boleh menapis dengan mengikut dimensi atau nilai yang paling menarik minat anda. 

## <a name="view-details-of-a-suggested-segment"></a>Lihat butiran segmen yang dicadangkan

Sebaik sahaja cadangan dijana, anda akan dapati cadangan disenaraikan pada **Segmen** > **Cadangan (pratonton)** dalam bahagian **Cadangan berasaskan aktiviti**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Anak tetingkap sisi yang dikembangkan menunjukkan data terperinci segmen yang dicadangkan.":::

Pilih **Lihat cadangan** pada segmen yang dicadangkan untuk melihat butiran segmen itu. Anak tetingkap sisi memberikan butiran seperti had setiap dimensi dalam perbandingan ke kumpulan sasaran. Ia juga menyerlahkan bilangan ahli yang berpotensi dalam segmen dan peratusan yang bersamaan dengan jumlah pelanggan. Jika anda mahu menyimpan cadangan sebagai segmen, pilih **Cipta segmen**.    

## <a name="save-a-suggestion-as-a-segment"></a>Simpan cadangan sebagai segmen

1. Pergi ke **Segmen** > **Cadangan (pratonton)**.

1. Pilih segmen yang anda mahu simpan. 

1. Dalam anak tetingkap sisi, pilih **Cipta segmen**. 

1. Selepas menyimpan segmen itu, ia akan ditunjukkan dalam senarai segmen pada tab **Semua segmen**. Ia kini boleh [disegar semula atau dipadam seperti segmen lain](segments.md). Anda tidak boleh mengedit butiran segmen. Walau bagaimanapun, anda boleh mengubah kriteria input untuk cadangan dan menjana cadangan yang berbeza.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Muatkan semula atau edit set cadangan

1. Pergi ke **Segmen** > **Cadangan (pratonton)** dan cari segmen dalam bahagian **Cadangan berasaskan aktiviti**.

1. Pilih **Segar semula cadangan** untuk segar semula cadangan sambil menyimpan atribut yang dikonfigurasikan. Atau pilih **Edit cadangan** untuk mengubah suai atribut yang dikonfigurasi. Sistem akan menjalankan semula proses, menjana cadangan segmen berdasarkan data terkini dan menggantikan cadangan semasa.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
