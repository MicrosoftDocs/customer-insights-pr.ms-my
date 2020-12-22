---
title: Perkayakan profil pelanggan dengan Microsoft Graph
description: Gunakan data proprietari daripada Microsoft Graph untuk mengayakan data pelanggan anda dengan persamaan jenama dan kepentingan .
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406446"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Mengayakan profil pelanggan dengan persamaan jenama dan kepentingan (pratonton)

Gunakan data proprietari daripada Microsoft Graph untuk mengayakan data pelanggan anda dengan persamaan jenama dan kepentingan . Afiniti ini ditentukan berdasarkan data daripada orang dengan demografi yang sama kepada pelanggan anda. Maklumat ini membantu anda untuk memahami dengan lebih baik dan membahagikan pelanggan anda berdasarkan afiniti mereka kepada jenama dan kepentingan khusus.

Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk [mengkonfigurasi dan melihat pengayaan](enrichment-hub.md).

Untuk mengkonfigurasikan pengayaan afiniti jenama pergi ke tab **Temui** dan pilih **Perkayakan data saya** pada jubin **Jenama**.

Untuk mengkonfigurasikan pengayaan afiniti kepentingan, pergi ke tab **Temui** dan pilih **Perkayakan data saya** pada jubin **Kepentingan**.

   > [!div class="mx-imgBorder"]
   > ![Jubin jenama & Minat](media/BrandsInterest-tile-Hub.png "Jubin jenama & Minat")

## <a name="about-microsoft-graph"></a>Tentang Microsoft Graph

Kami menggunakan data carian dalam talian daripada Microsoft Graph untuk mencari persamaan untuk jenama dan kepentingan merentasi pelbagai segmen demografi (ditakrifkan mengikut umur, jantina atau lokasi). Jumlah carian dalam talian untuk sesebuah jenama atau faedah menentukan jumlah persamaan bahagian demografi berbanding segmen lain yang mempunyai persamaan jenama atau kepentingan.

[Ketahui lebih lanjut tentang Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Skor dan keyakinan afiniti

**Skor afiniti** dikira berdasarkan skala 100 mata, dengan 100 mewakili segmen yang mempunyai perkaitan tertinggi untuk jenama atau kepentingan.

**Keyakinan persamaan** juga dikira berdasarkan skala 100 mata. Ia menunjukkan tahap keyakinan sistem yang segmen mempunyai persamaan untuk jenama atau kepentingan. Tahap keyakinan adalah berdasarkan saiz bahagian dan granulariti bahagian. Saiz bahagian ditentukan oleh jumlah data yang kami ada untuk bahagian tertentu. Perincian segmen ditentukan berdasarkan bilangan atribut (umur, jantina, lokasi) yang tersedia dalam profil.

Kami tidak paling menormalkan skor untuk set data anda. Oleh itu, anda tidak boleh melihat semua nilai skor afiniti yang mungkin untuk set data anda. Sebagai contoh, mungkin tiada profil pelanggan diperkaya dengan skor persamaan 100 dalam data anda. Ini mungkin jika tiada pelanggan wujud dalam segmen demografi yang menjaringkan 100 untuk jenama atau minat yang diberikan.

> [!TIP]
> Apabila [mencipta bahagian](segments.md) menggunakan skor afiniti, semak pengagihan skor afiniti untuk set data anda sebelum membuat keputusan pada ambang skor yang sesuai. Sebagai contoh, skor afiniti sebanyak 10 boleh dianggap signifikan dalam set data yang mempunyai skor perkaitan tertinggi hanya 25 untuk jenama atau kepentingan yang diberikan.

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong

Kami kini menyokong pilihan negara/rantau berikut: Australia, Kanada (Bahasa Inggeris), Perancis, Jerman, United Kingdom atau Amerika Syarikat (Bahasa Inggeris).

Untuk memilih negara, buka **Pengayaan jenama** atau **Pengayaan minat** dan pilih **Tukar** bersebelahan dengan **Negara/Rantau**. Dalam anak tetingkap **Tetapan Negara/Rantau**, pilih pilihan dan pilih **Gunakan**.

### <a name="implications-related-to-country-selection"></a>Implikasi berkaitan dengan pemilihan negara

- Apabila [memilih jenama anda sendiri](#define-your-brands-or-interests), kami akan menyediakan cadangan berasaskan pada negara/rantau yang dipilih.

- Apabila [memilih industri](#define-your-brands-or-interests), kami akan mentakrifkan jenama atau minat yang paling relevan berasaskan pada negara/rantau yang dipilih.

- Semasa [memetakan medan anda](#map-your-fields), jika medan Negara/Rantau tidak dipetakan, kami akan menggunakan data Microsoft Graph daripada negara/rantau yang dipilih untuk memperkayakan profil pelanggan anda. Kami juga akan menggunakan pemilihan itu untuk memperkayakan profil pelanggan yang tidak tersedia negara/rantau.

- Semasa [memperkayakan profil](#refresh-enrichment), kami akan memperkayakan profil pelanggan yang kami sediakan data Microsoft Graph untuk jenama dan minat yang dipilih termasuk profil yang tidak berada dalam negara/rantau yang dipilih. Contohnya, jika anda memilih Jerman, kami akan memperkayakan profil yang terletak dalam Amerika Syarikat jika kami mempunyai data Microsoft Graph tersedia untuk jenama dan minat yang dipilih dalam Amerika Syarikat.

## <a name="configure-enrichment"></a>Konfigurasikan Pengayaan

Mengkonfigurasikan pengayaan jenama dan kepentingan terdiri daripada dua langkah:

### <a name="define-your-brands-or-interests"></a>Takrifkan jenama dan kepentingan anda

Pilih salah satu daripada pilihan berikut:

- **Industri**: Sistem mengenal pasti jenama dan kepentingan teratas yang berkaitan dengan industri anda dan mengayakan data pelanggan anda dengannya.
- **Pilih milik anda sendiri**: Pilih sehingga lima item daripada senarai jenama dan kepentingan yang paling berkaitan dengan organisasi anda.

Untuk menambah jenama atau kepentingan, masukkannya ke dalam kawasan input untuk mendapatkan cadangan berdasarkan terma yang sepadan. Jika kami tidak menyenaraikan jenama atau minat yang anda cari, hantar maklum balas kepada kami menggunakan pautan **Cadangkan**.

### <a name="map-your-fields"></a>Petakan medan anda

Peta medan daripada entiti pelanggan disatukan anda kepada sekurang-kurangnya dua atribut untuk mentakrifkan segmen demografi yang anda mahu kami gunakan untuk mengayakan data pelanggan anda. Pilih **Edit** untuk mentakrifkan pemetaan medan dan pilih **Gunakan** apabila anda selesai. Pilih **Simpan** untuk melengkapkan pemetaan medan.

Format dan nilai berikut disokong, nilai bukan sensitif huruf:

- **Tarikh Lahir**: Kami mengesyorkan bahawa tarikh lahir ditukarkan ke jenis DateTime semasa pengingesan data. Secara alternatif, ianya boleh menjadi rentetan dalam format [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "yyyy-MM-dd" atau "yyyy-MM-ddTHH:mm:ssZ".
- **Jantina**: Lelaki, Perempuan,Tidak Diketahui
- **Poskod**: Kod zip lima digit untuk Amerika Syarikat, poskod standard di tempat lain
- **Bandar**: Nama bandar dalam Bahasa Inggeris
- **Negeri/Wilayah**: Singkatan dua huruf untuk Amerika Syarikat dan Kanada. Singkatan dua atau tiga huruf untuk Australia. Tidak terpakai untuk Perancis, Jerman atau UK.
- **Negara/Rantau**:

  - AS: Amerika Syarikat, Amerika Syarikat, USA, AS, Amerika
  - CA: Kanada, CA
  - GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain dan Northern Ireland, United Kingdom of Great Britain
  - AU: Australia, AU, Komanwel Australia
  - FR: Bahasa Perancis, FR, French Republic
  - DE: Jerman, Jerman, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany

## <a name="refresh-enrichment"></a>Pengayaan segar semula

Jalankan pengayaan selepas mengkonfigurasi jenama, kepentingan dan pemetaan medan untuk demografi. Untuk memulakan proses, pilih **Jalankan** pada halaman konfigurasi jenama dan kepentingan. Selain itu, anda boleh membiarkan sistem jalankan pengayaan secara automatik sebagai sebahagian daripada segar semula yang dijadualkan.
Bergantung pada saiz data pelanggan anda, ia mungkin mengambil masa beberapa minit untuk jangka masa pengayaan dilengkapkan.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas menjalankan proses pengayaan, pergi ke **Pengayaan saya** untuk menyemak semula jumlah bilangan pelanggan yang diperkayakan dan pecahan jenama dan kepentingan dalam proses pelanggan yang diperkayakan.

:::image type="content" source="media/my-enrichments.png" alt-text="Pratonton keputusan selepas menjalankan proses pengayaan":::

Kaji semula data yang diperkaya dengan memilih **Lihat data diperkaya** dalam carta. Data diperkaya untuk jenama pergi kepada entiti **PersamaanJenamaDaripadaMicrosoft**. Data untuk kepentingan adalah dalam entiti **PersamaanKepentinganDaripadaMicrosoft**. Anda juga akan menemui entiti ini yang disenaraikan dalam kumpulan **Pengayaan** dalam **Entiti** > **Data**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Lihat data pengayaan pada kad pelanggan

Jenama dan afiniti berkepentingan juga boleh dilihat pada kad pelanggan individu. Pergi ke **Pelanggan** dan pilih profil pelanggan. Dalam kad pelanggan, anda akan menemui carta untuk jenama atau kepentingan yang orang dalam profil demografik pelanggan mempunyai afiniti untuknya.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya":::

## <a name="next-steps"></a>Langkah seterusnya

Bina di atas data pelanggan anda yang diperkaya. Cipta [Langkah-langkah](segments.md), [Bahagain](measures.md) dan juga [eksport data](export-destinations.md) untuk menyampaikan pengalaman peribadi kepada pelanggan anda.
