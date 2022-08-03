---
title: Segmen yang dicadangkan berdasarkan langkah-langkah (pratonton)
description: Benarkan pembelajaran mesin membantu anda mencari segmen baharu dan yang menarik berdasarkan atribut pelanggan.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: e3f504827029afa12c65ec6f065a62606aaa823f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170968"
---
# <a name="suggested-segments-based-on-measures-preview"></a>Segmen yang dicadangkan berdasarkan langkah-langkah (pratonton)

Terokai segmen yang menarik bagi pelanggan anda dengan bantuan model AI. Ciri dikuasakan embelajaran mesin ini mencadangkan segmen berdasarkan langkah atau atribut pelanggan. Ia boleh membantu meningkatkan Petunjuk Prestasi Utama (KPI) anda atau lebih memahami pengaruh atribut dalam konteks atribut lain.

> [!NOTE]
> Ciri segmen yang dicadangkan menggunakan cara automatik untuk menilai data dan membuat ramalan berdasarkan data tersebut. Oleh itu, ia mempunyai keupayaan untuk digunakan sebagai kaedah pemprofilan, kerana istilah itu ditakrifkan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan anda bagi ciri ini untuk memproses data mungkin tertakluk pada GDPR atau perundangan atau peraturan lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ciri ini, mematuhi semua undang-undang dan peraturan yang berkaitan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.

:::image type="content" source="media/suggested-segments.png" alt-text="Halaman segmen yang dicadangkan menunjukkan butiran cadangan dalam anak tetingkap sisi.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmen yang dicadangkan untuk meningkatkan KPI anda

Jika anda menggunakan [langkah yang dicipta](measures.md) untuk membantu menjejak KPI anda, cipta segmen untuk melihat pengaruh pada KPI. Anda boleh menggunakan maklumat ini untuk menjalankan kempen yang sangat disasarkan.

Contohnya, anda menjejaki langkah yang dipanggil *TotalSpendPerCustomer*. Sebagai sebuah perniagaan, anda ingin melihat bilangan ini berkembang. Memilih ukuran sebagai atribut utama, pilih atribut yang anda ingin nilai untuk pengaruh. Katakan *peringkat keahlian*, *tempoh keahlian* dan *pekerjaan*. Customer Insights boleh mencadangkan segmen yang memberitahu anda orang pengaruh terbesar antara langkah tersebut. Sebagai contoh, *Akauntan* yang merupakan ahli *Emas*,dan yang telah bersama perniagaan anda *sekurang-kurangnya lima tahun* adalah pempengaruh terbesar *TotalSpendPerCustomer*. Anda akan mendapat anggaran saiz segmen untuk setiap cadangan. Anda boleh menggunakan maklumat ini untuk mencipta kempen bagi khalayak sasaran.

## <a name="understand-what-influences-a-customer-attribute"></a>Memahami perkara yang mempengaruhi atribut pelanggan

Anda boleh memilih atribut pelanggan dan bukannya ukuran sebagai atribut utama. Berdasarkan pada pilihan anda untuk mempengaruhi atribut, model AI mencipta satu siri cadangan yang menunjukkan cara atribut yang dipilih mempengaruhi atribut utama.

Contohnya, anda memilih *Ahli Ganjaran (Ya/Tidak)* sebagai atribut utama. *Tempoh*, *Pekerjaan* dan *Bilangan Tiket Sokongan* ditetapkan sebagai atribut lain yang mempengaruhi. Model AI boleh mencadangkan segmen yang menunjukkan kebanyakan profesional IT yang mempunyai tempoh selama dua tahun adalah ahli ganjaran. Cadangan lain boleh menyerlahkan bahawa akauntan dengan tempoh selama satu tahun dan kurang daripada tiga tiket sokongan adalah ahli ganjaran.

## <a name="artificial-intelligence-usage"></a>Penggunaan kecerdasan buatan

Menggunakan atribut utama dan mempengaruhi atribut, algoritma pohon keputusan mencadangkan segmen yang menarik. Cadangan adalah berdasarkan peraturan atau corak yang diambil oleh algoritma AI. Hanya segmen yang berbeza secara ketara daripada populasi purata ditunjukkan sebagai cadangan. Perbandingan kepada populasi purata adalah berdasarkan ukuran yang dipilih atau atribut utama.

### <a name="responsible-ai"></a>AI Yang Bertanggungjawab

Dengan segmen yang dicadangkan, anda memilih atribut untuk mencipta segmen baharu dan memproses data yang anda pilih. Apabila memilih atribut, termasuk sifat sensitif seperti bangsa, orientasi seksual atau jantina, anda mesti memastikan bahawa anda boleh dan perlu memproses data tersebut. Anda bertanggungjawab untuk mematuhi mana-mana undang-undang yang berkaitan dengan organisasi anda dan mematuhi prinsip dan dasar privasi organisasi anda.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Hasil yang berbeza untuk atribut utama dengan nilai berangka dan berkategori

Cadangan segmen adalah berbeza jika anda memilih atribut berangka atau atribut berkategori sebagai atribut utama. Nilai dalam atribut berkategori mengandungi dua atau lebih kategori atau jenis. Atribut angka mengandungi data kuantitatif dan mempunyai rasa pengukuran yang berkaitan dengannya.

Dengan atribut angka seperti *pendapatan tahunan* atau *tempoh keahlian* sebagai atribut utama, sistem mencadangkan segmen yang mempunyai nilai purata yang lebih tinggi atau lebih rendah pada atribut angka apabila dibandingkan dengan semua pelanggan.

Atribut berkategori seperti *kepuasan pelanggan* sebagai hasil utama dalam segmen yang dicadangkan mempunyai peratusan pelanggan yang lebih tinggi dan lebih rendah mengikut kategori tertentu apabila dibandingkan dengan peratusan semua pelanggan yang dimiliki oleh kategori yang sama. Sebagai contoh, *kepuasan pelanggan* dipilih sebagai atribut utama dan ia terdiri daripada tiga kategori (*Rendah*, *Sederhana* dan *Tinggi*). Bagi setiap kategori, segmen akan dicadangkan yang mempunyai peratusan pelanggan yang lebih tinggi atau lebih rendah yang tergolong dalam kategori tersebut berbanding dengan perkadaran semua pelanggan dalam kategori yang sama. Jika 22% daripada semua pelanggan mempunyai kepuasan *Tinggi*, kemudian, hanya segmen yang mempunyai perkadaran pelanggan yang lebih tinggi atau lebih rendah dengan kepuasan *Tinggi* berbanding dengan 22% akan dicadangkan untuk kategori tersebut. Begitu juga, segmen akan dicadangkan untuk setiap kategori lain (*Rendah* dan *Sederhana*) jika ia mempunyai statistik penting.

> [!NOTE]
> Pada masa ini, kami hanya menyokong atribut pengkategoran utama yang mempunyai sehingga 10 kategori. Jika anda ingin melihat cadangan segmen berdasarkan atribut utama dengan lebih daripada 10 kategori, kami mengesyorkan untuk mengumpulkan beberapa kategori untuk mengurangkan bilangan kategori kepada 10 atau kurang. Pengehadan ini hanya diguna pakai untuk atribut utama. Untuk mempengaruhi atribut berkategori, kami kini menyokong maksimum 100 kategori.

## <a name="generate-suggested-segments"></a>Menjana segmen yang dicadangkan

1. Pergi ke **Segmen** dan pilih **tab Cadangan (pratonton**).

1. Pilih **Cari cadangan** baru dan pilih **Tingkatkan ukuran/metrik**. Pilih **Mula**.

   :::image type="content" source="media/suggested-segments-measure.png" alt-text="Memilih langkah penambahbaikan pada segmen yang dicadangkan.":::

1. Pilih atribut atau ukuran pelanggan sebagai atribut utama dan pilih **Seterusnya**.

1. Pilih atribut yang mempengaruhi dan pilih **Jalankan**.

   > [!TIP]
   > Memilih atribut mempengaruh berganda yang meningkatkan peluang untuk menilai cara ia mempengaruhi atribut utama. Jangan sertakan atribut yang tidak mempunyai pengaruh pada atribut utama. Contohnya, jika semua pelanggan anda daripada negara tertentu, jangan sertakan atribut *negara* kerana ia tidak akan mempunyai sebarang kesan ke atas output tersebut.

Bergantung pada bilangan profil pelanggan dan atribut yang dipilih, ia boleh mengambil masa beberapa minit untuk memproses atribut yang dipilih.

## <a name="manage-suggested-segments"></a>Urus segmen yang dicadangkan

Pergi ke **Segmen** dan pilih **tab Cadangan (pratonton**). **Dalam seksyen Cadangan** segmen berasaskan atribut, pilih segmen yang dicadangkan untuk melihat tindakan yang tersedia.

- **Lihat** butiran segmen yang dicadangkan dan nilai atribut atau peraturan yang dipelajari oleh model AI.
- **Simpan sebagai segmen** cadangan sebagai segmen. Ia dipaparkan pada **tab Semua segmen** dan boleh [disegar semula, diedit atau dipadamkan](segments.md).
- **Edit atribut** dan ubah suai atribut yang dikonfigurasi yang akan menggantikan cadangan semasa.
- **Segar semula cadangan** untuk menyegar semula cadangan sambil mengekalkan atribut yang dikonfigurasi.

## <a name="limitations"></a>Batasan

1. Anggaran saiz segmen tidak sepadan: Jika anda memilih atribut utama yang mengandungi nilai kosong, ia boleh mempengaruhi anggaran saiz segmen dalam cadangan segmen. Apabila menyimpan segmen tersebut, saiz segmen sebenar boleh berbeza mengikut anggaran asal.

2. Atribut utama jenis Boolean tidak berfungsi: Pada masa ini, kami hanya menyokong jenis data rentetan dan berangka sebagai atribut utama.

3. Segmen yang dicadangkan tidak cukup jelas: Perlu diingati bahawa atribut yang dipilih dan pengagihan nilai atribut tersebut mempengaruhi keputusan. Anda boleh mengubah atribut yang mempengaruhi anda atau malah atribut utama anda untuk mendapatkan hasil yang berbeza.

[!INCLUDE [footer-include](includes/footer-banner.md)]