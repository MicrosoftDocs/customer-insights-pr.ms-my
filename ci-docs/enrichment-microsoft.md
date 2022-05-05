---
title: Perkayakan profil pelanggan dengan data daripada Microsoft
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
ms.openlocfilehash: 5c016a394fdf485057a190d03bfed9ce5481f435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643290"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Memperkayakan profil pelanggan dengan pertalian dan perkongsian suara (pratonton)

Gunakan data proprietari Microsoft untuk memperkayakan data pelanggan anda dengan pertalian jenama, pertalian minat dan perkongsian suara (SoV). Pertalian dan SoV ini berdasarkan data daripada orang yang mempunyai demografi yang serupa dengan pelanggan anda. Maklumat ini membantu anda untuk lebih memahami dan membahagikan pelanggan anda berdasarkan pertalian mereka atau SoV kepada jenama dan minat tertentu.

Pergi ke **DataEnrichment** > **untuk** [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).

Untuk mengkonfigurasi pertalian jenama dan pengayaan SoV, pergi ke tab Discover **dan pilih** Memperkayakan data **saya pada** jubin Jenama **.**

Untuk mengkonfigurasi pertalian faedah dan pengayaan SoV, pergi ke tab Discover **dan pilih** Memperkayakan data **saya pada** jubin Kepentingan **.**

   > [!div class="mx-imgBorder"]
   > ![Jubin Jenama dan Minat.](media/BrandsInterest-tile-Hub.png "Jubin Jenama dan Minat")

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

Untuk memilih negara atau rantau, buka **Pengayaan jenama** atau **Pengayaan minat** dan pilih **Tukar** di sebelah **Negara/Rantau**. Dalam anak tetingkap **Tetapan Negara/Rantau**, pilih pilihan dan pilih **Gunakan**.

### <a name="implications-related-to-country-selection"></a>Implikasi berkaitan dengan pemilihan negara

- Apabila [memilih jenama anda sendiri](#define-your-brands-or-interests), sistem memberikan cadangan berdasarkan negara atau rantau yang dipilih.

- Apabila [memilih industri](#define-your-brands-or-interests), anda akan mendapat jenama atau minat yang paling berkaitan berdasarkan negara atau rantau yang dipilih.

- Apabila [memperkaya profil](#refresh-enrichment), kami akan memperkaya semua profil pelanggan yang data diperoleh untuk jenama dan minat yang dipilih, termasuk profil yang tidak berada di negara atau rantau yang dipilih. Sebagai contoh, jika anda memilih Jerman, kami akan memperkayakan profil yang terletak di Amerika Syarikat jika kami mempunyai data yang tersedia untuk jenama dan minat yang dipilih di Amerika Syarikat.

## <a name="configure-enrichment"></a>Konfigurasikan pengayaan

Pengalaman berpandu membantu anda melalui konfigurasi pengayaan. 

### <a name="define-your-brands-or-interests"></a>Takrifkan jenama dan kepentingan anda

Pilih sehingga lima jenama atau minat menggunakan satu atau kedua-dua pilihan ini:

- **Industri**: Pilih industri anda daripada senarai juntai bawah dan kemudian pilih daripada jenama atau minat popular untuk industri tersebut.
- **Pilih sendiri**: Masukkan jenama atau minat yang berkaitan dengan organisasi anda dan kemudian pilih daripada cadangan yang sepadan. Jika kami tidak menyenaraikan jenama atau minat yang anda cari, hantar maklum balas kepada kami menggunakan pautan **Cadangkan**.

### <a name="review-enrichment-preferences"></a>Semak keutamaan pengayaan

Semak keutamaan pengayaan lalai anda dan kemas kini apabila diperlukan.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Tangkapan skrin tetingkap keutamaan pengayaan.":::

### <a name="select-entity-to-enrich"></a>Pilih entiti untuk memperkaya

Pilih **Entiti** diperkaya dan pilih set data yang anda ingin perkayakan dengan data daripada Microsoft. Anda boleh memilih entiti Pelanggan untuk memperkayakan semua profil pelanggan anda atau pilih entiti segmen untuk memperkayakan hanya profil pelanggan yang terkandung dalam segmen tersebut.

### <a name="map-your-fields"></a>Petakan medan anda

Medan peta daripada entiti pelanggan disatukan anda untuk mentakrifkan segmen demografi yang anda mahu sistem gunakan untuk memperkaya data pelanggan anda. Peta Negara/Rantau dan sekurang-kurangnya atribut Tarikh Lahir atau Jantina. Di samping itu, anda mesti memetakan sekurang-kurangnya satu daripada Bandar (dan Negeri/Wilayah) atau Poskod. Pilih **Edit** untuk mentakrifkan pemetaan medan dan pilih **Gunakan** apabila anda selesai. Pilih **Simpan** untuk melengkapkan pemetaan medan.

Format dan nilai berikut disokong (nilai tidak sensitif huruf):

- **Tarikh Lahir**: Kami mengesyorkan bahawa tarikh lahir ditukarkan ke jenis DateTime semasa pengingesan data. Sebagai alternatif, ia boleh menjadi rentetan dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ss".
- **Jantina**: Lelaki, Perempuan,Tidak Diketahui.
- **Poskod**: Kod ZIP lima digit untuk Amerika Syarikat, poskod standard di mana-mana sahaja.
- **Bandar**: Nama bandar dalam bahasa Inggeris.
- **Negeri/Wilayah**: Singkatan dua huruf untuk Amerika Syarikat dan Kanada. Singkatan dua atau tiga huruf untuk Australia. Tidak terpakai untuk Perancis, Jerman atau UK.
- **Negara/Rantau**:

  - AS: Amerika Syarikat, Amerika Syarikat, USA, AS, Amerika
  - CA: Kanada, CA
  - GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain dan Northern Ireland, United Kingdom of Great Britain
  - AU: Australia, AU, Komanwel Australia
  - FR: Bahasa Perancis, FR, French Republic
  - DE: Jerman, Jerman, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany

## <a name="review-and-name-the-enrichment"></a>Semak dan namakan pengayaan

Akhir sekali, anda boleh menyemak maklumat dan memberikan nama untuk pengayaan.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Halaman semakan dan penamaan minat.":::

## <a name="refresh-enrichment"></a>Pengayaan segar semula

Jalankan pengayaan selepas mengkonfigurasi jenama, kepentingan dan pemetaan medan untuk demografi. Untuk memulakan proses, pilih **Jalankan** pada halaman konfigurasi jenama dan kepentingan. Selain itu, anda boleh membiarkan sistem jalankan pengayaan secara automatik sebagai sebahagian daripada segar semula yang dijadualkan.

Bergantung pada saiz data pelanggan anda, ia mungkin mengambil masa beberapa minit untuk jangka masa pengayaan dilengkapkan.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas menjalankan proses pengayaan, pergi ke **Pengayaan saya** untuk menyemak semula jumlah bilangan pelanggan yang diperkayakan dan pecahan jenama dan kepentingan dalam proses pelanggan yang diperkayakan.

:::image type="content" source="media/my-enrichments.png" alt-text="Pratonton hasil selepas menjalankan proses pengayaan.":::

Anda akan menemui carta dengan bilangan profil pelanggan yang diperkaya dari masa ke masa dan pratonton entiti yang diperkaya. Semak data yang diperkaya dengan **memilih Lihat lebih lanjut** dalam **carta Tahap** Perkaitan atau **Kongsi Suara**. Data yang diperkaya untuk jenama pergi ke **brandAffinityFromMicrosoft** dan **BrandShareOfVoiceFromMicrosoft** entiti. Data untuk kepentingan adalah dalam **Entiti InterestAffinityFromMicrosoft** dan **InterestShareOfVoiceFromMicrosoft**. Anda juga akan menemui entiti ini yang disenaraikan dalam kumpulan **Pengayaan** dalam **Entiti** > **Data**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Lihat data pengayaan pada kad pelanggan

Jenama dan minat SoV juga boleh dilihat pada kad pelanggan individu. Pergi ke **Pelanggan** dan pilih profil pelanggan. Dalam kad pelanggan, anda akan menemui carta untuk jenama atau minat SoV berdasarkan orang dalam profil demografi pelanggan tersebut.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya.":::

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
