---
title: Memperkayakan profil pelanggan dengan jenama dan data minat daripada Microsoft (pratonton)
description: Gunakan data proprietari daripada Microsoft untuk memperkayakan data pelanggan anda dengan pertalian dan perkongsian suara.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082706"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Memperkayakan profil pelanggan dengan jenama dan data minat daripada Microsoft (pratonton)

Gunakan data proprietari Microsoft untuk memperkayakan data pelanggan anda dengan pertalian jenama, pertalian minat dan perkongsian suara (SoV). Pertalian dan SoV ini berdasarkan data daripada orang yang mempunyai demografi yang serupa dengan pelanggan anda. Maklumat ini membantu anda untuk lebih memahami dan membahagikan pelanggan anda berdasarkan pertalian mereka atau SoV kepada jenama dan minat tertentu.

## <a name="how-we-determine-affinities-and-sov"></a>Bagaimana kita menentukan pertalian dan SoV

Kami menggunakan data carian dalam talian Microsoft untuk mencari pertalian dan SoV untuk jenama dan minat merentasi pelbagai segmen demografi (ditakrifkan mengikut umur, jantina atau lokasi). Jumlah carian dalam talian untuk jenama atau minat membentuk asas untuk menentukan pertalian atau SoV. Walau bagaimanapun, masing-masing memberikan perspektif yang berbeza untuk memahami pelanggan anda.

- Perkaitan adalah perbandingan merentasi segmen demografi. Anda boleh menggunakan maklumat ini untuk mengenal pasti segmen demografi yang mempunyai pertalian tertinggi untuk jenama atau minat tertentu, berbanding dengan segmen lain.

- Bahagian suara adalah perbandingan merentasi jenama atau minat pilihan anda. Anda boleh menggunakan maklumat ini untuk mengenal pasti jenama atau minat mana yang mempunyai bahagian suara tertinggi untuk segmen demografi tertentu, berbanding dengan jenama atau minat lain yang anda pilih.

## <a name="affinity-level-and-score"></a>Tahap dan skor perkaitan

Pada setiap profil pelanggan yang diperkaya, kami menyediakan dua nilai yang berkaitan: tahap afiniti dan skor afiniti. Nilai ini membantu anda menentukan kekuatan perkaitan itu untuk bahagian demografi profil, untuk jenama atau minat, berbanding dengan segmen demografi lain.

*Tahap perkaitan* terdiri daripada empat peringkat dan *skor perkaitan* akan dikira berdasarkan skala 100 mata yang memetakan kepada tahap perkaitan.

|Peringkat perkaitan |Skor perkaitan  |
|---------|---------|
|Sangat tinggi     | 85-100       |
|Tinggi     | 70-84        |
|Sederhana     | 35-69        |
|Rendah     | 1-34        |

Bergantung pada butiran yang anda mahu untuk mengukur perkaitan, anda boleh menggunakan sama ada tahap atau skor perkaitan. Skor perkaitan memberikan anda kawalan yang lebih tepat.

## <a name="share-of-voice-sov"></a>Bahagian suara (SoV)

Kami mengira SoV pada skala 100 mata. Jumlah SoV di semua jenama atau minat untuk setiap profil pelanggan yang diperkaya menambah sehingga 100. Tidak seperti pertalian, SoV adalah relatif kepada jenama dan minat yang anda pilih. Sebagai contoh, nilai SoV untuk "Microsoft" boleh berbeza jika jenama yang dipilih adalah ('Microsoft', 'GitHub') berbanding ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong

Kami kini menyokong pilihan negara/rantau berikut: Australia, Kanada (Bahasa Inggeris), Perancis, Jerman, United Kingdom atau Amerika Syarikat (Bahasa Inggeris).

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

   - Untuk mengkonfigurasi pertalian jenama dan pengayaan SoV, pilih **Memperkayakan data** saya pada **jubin Jenama**.

   - Untuk mengkonfigurasi pertalian faedah dan pengayaan SoV, pilih **Memperkayakan data** saya pada **jubin Kepentingan**.

   > [!div class="mx-imgBorder"]
   > ![Jubin Jenama dan Minat.](media/BrandsInterest-tile-Hub.png "Jubin Jenama dan Minat")

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Untuk menukar negara atau rantau anda, pilih **Tukar di** sebelah **Negara/Rantau**. **Dalam anak tetingkap Seting** Negara/Rantau, pilih negara/rantau [yang](#supported-countriesregions) disokong dan pilih **Gunakan**.

   > [!NOTE]
   > Apabila memilih jenama anda sendiri, sistem memberikan cadangan berdasarkan negara atau rantau yang dipilih. Apabila memilih industri, anda akan mendapat jenama atau minat yang paling berkaitan berdasarkan negara atau rantau yang dipilih.

1. Pilih sehingga lima jenama atau minat menggunakan satu atau kedua-dua pilihan ini:

   - **Industri**: Pilih industri anda daripada senarai juntai bawah dan kemudian pilih daripada jenama atau minat popular untuk industri tersebut.
   - **Pilih sendiri**: Masukkan jenama atau minat yang berkaitan dengan organisasi anda dan kemudian pilih daripada cadangan yang sepadan. Jika kami tidak menyenaraikan jenama atau minat yang anda cari, hantar maklum balas kepada kami menggunakan pautan **Cadangkan**.

1. Pilih **Seterusnya** dan semak semula keutamaan pengayaan lalai anda dan kemas kininya mengikut keperluan.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Tangkapan skrin tetingkap keutamaan pengayaan.":::

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang anda ingin memperkayakan dengan data daripada Microsoft. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Pilih **Seterusnya**.

1. Petakan medan anda daripada entiti pelanggan bersatu anda kepada data Microsoft.

   > [!NOTE]
   > Sekurang-kurangnya Tarikh Lahir atau Atribut Jantina diperlukan. Negara/Rantau dan sekurang-kurangnya Bandar (dan Negeri/Wilayah) atau Poskod diperlukan. Kami mengesyorkan agar tarikh lahir ditukar kepada jenis DateTime semasa pengambilan data. Sebagai alternatif, ia boleh menjadi rentetan dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ss".

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Berikan nama untuk pengayaan. Nama **entiti** Output dipilih secara automatik.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Halaman semakan dan penamaan minat.":::

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

   Apabila memperkaya profil, kami akan memperkaya semua profil pelanggan yang data diperoleh untuk jenama dan minat yang dipilih, termasuk profil yang tidak berada di negara atau rantau yang dipilih. Sebagai contoh, jika anda memilih Jerman, kami akan memperkayakan profil yang terletak di Amerika Syarikat jika kami mempunyai data yang tersedia untuk jenama dan minat yang dipilih di Amerika Syarikat.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Pratonton hasil selepas menjalankan proses pengayaan.":::

Hasilnya termasuk carta Tahap **Perkaitan atau** Kongsi Suara **.**

Entiti yang dicipta daripada pengayaan disenaraikan di bawah **kumpulan Pengayaan** dalam **Entiti** > **Data**. Data yang diperkaya untuk jenama pergi ke **brandAffinityFromMicrosoft** dan **BrandShareOfVoiceFromMicrosoft** entiti. Data untuk kepentingan adalah dalam **Entiti InterestAffinityFromMicrosoft** dan **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Lihat data pengayaan pada kad pelanggan

Jenama dan minat SoV juga boleh dilihat pada kad pelanggan individu. Pergi ke **Pelanggan** dan pilih profil pelanggan. Dalam kad pelanggan, anda akan menemui carta untuk jenama atau minat SoV berdasarkan orang dalam profil demografi pelanggan tersebut.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya.":::

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
