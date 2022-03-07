---
title: Pembelajaran mesin dikuasakan segmen yang dicadangkan
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
ms.openlocfilehash: 82345a7d7cf7fd38d74080552799de0b92461d78
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353600"
---
# <a name="suggested-segments-preview"></a>Segmen dicadangkan (pratonton)

Terokai segmen yang menarik bagi pelanggan anda dengan bantuan model AI. Ciri dikuasakan embelajaran mesin ini mencadangkan segmen berdasarkan langkah atau atribut pelanggan. Ia boleh membantu meningkatkan KPI anda atau lebih memahami pengaruh atribut dalam konteks atribut lain. 

> [!NOTE]
> Ciri segmen yang dicadangkan menggunakan cara automatik untuk menilai data dan membuat ramalan berdasarkan data tersebut dan oleh itu mempunyai keupayaan untuk digunakan sebagai kaedah pemprofilan, kerana istilah tersebut ditakrifkan oleh Peraturan Perlindungan Data Am ("GDPR"). Penggunaan anda bagi ciri ini untuk memproses data mungkin tertakluk pada GDPR atau perundangan atau peraturan lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk ciri ini, mematuhi semua undang-undang dan peraturan yang berkaitan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data dan kerahsiaan komunikasi.

:::image type="content" source="media/suggested-segments.png" alt-text="Halaman segmen yang dicadangkan menunjukkan butiran cadangan dalam anak tetingkap sisi.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmen yang dicadangkan untuk meningkatkan KPI anda

Sebagai pengguna wawasan khalayak, anda mungkin mempunyai siri [langkah dicipta](measures.md) yang membantu menjejaki Penunjuk Prestasi Utama (KPI) anda. Ia adalah penting untuk memahami cara sesetengah atribut mempengaruhi KPI ini untuk mencipta segmen dan menjalankan kempen yang amat disasarkan.   
Contohnya, anda menjejaki langkah yang dipanggil *TotalSpendPerCustomer*. Sebagai sebuah perniagaan, anda ingin melihat bilangan ini berkembang. Memilih langkah sebagai atribut utama, membolehkan anda memilih atribut yang anda mahu menilai untuk pengaruh. Katakan *peringkat keahlian*, *tempoh keahlian* dan *pekerjaan*. Customer Insights boleh mencadangkan segmen yang memberitahu anda orang pengaruh terbesar antara langkah tersebut. Sebagai contoh, *Akauntan* yang merupakan ahli *Emas*,dan yang telah bersama perniagaan anda *sekurang-kurangnya lima tahun* adalah pempengaruh terbesar *TotalSpendPerCustomer*. Anda akan mendapat anggaran saiz segmen untuk setiap cadangan. Anda boleh menggunakan maklumat ini untuk mencipta kempen bagi khalayak sasaran.

## <a name="understand-what-influences-a-customer-attribute"></a>Memahami perkara yang mempengaruhi atribut pelanggan

Anda boleh memilih atribut pelanggan dan bukannya ukuran sebagai atribut utama. Berdasarkan pada pilihan anda untuk mempengaruhi atribut, model AI mencipta satu siri cadangan yang menunjukkan cara atribut yang dipilih mempengaruhi atribut utama.   
Contohnya, anda memilih *Ahli Ganjaran (Ya/Tidak)* sebagai atribut utama. *Tempoh*, *Pekerjaan* dan *Bilangan Tiket Sokongan* ditetapkan sebagai atribut lain yang mempengaruhi. Model AI boleh mencadangkan segmen yang menunjukkan kebanyakan profesional IT yang mempunyai tempoh selama dua tahun adalah ahli ganjaran. Cadangan lain boleh menyerlahkan bahawa akauntan dengan tempoh selama satu tahun dan kurang daripada tiga tiket sokongan adalah ahli ganjaran. 

## <a name="artificial-intelligence-usage"></a>Penggunaan kecerdasan buatan

Menggunakan atribut utama dan mempengaruhi atribut, algoritma pohon keputusan mencadangkan segmen yang menarik. Cadangan adalah berdasarkan peraturan atau corak yang diambil oleh algoritma AI. Hanya segmen yang berbeza secara ketara daripada populasi purata ditunjukkan sebagai cadangan. Perbandingan kepada populasi purata adalah berdasarkan ukuran yang dipilih atau atribut utama.

### <a name="responsible-ai"></a>AI Yang Bertanggungjawab

Segmen yang dicadangkan membolehkan anda memilih atribut untuk mencipta segmen baharu dan memproses data yang anda pilih. Apabila memilih atribut, termasuk sifat sensitif seperti bangsa, orientasi seksual atau jantina, anda mesti memastikan bahawa anda boleh dan perlu memproses data tersebut. Anda bertanggungjawab untuk mematuhi mana-mana undang-undang yang berkaitan dengan organisasi anda dan mematuhi prinsip dan dasar privasi organisasi anda.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Hasil yang berbeza untuk atribut utama dengan nilai berangka dan berkategori

Cadangan segmen adalah berbeza jika anda memilih atribut berangka atau atribut berkategori sebagai atribut utama. Nilai dalam atribut berkategori mengandungi dua atau lebih kategori atau jenis. Atribut angka mengandungi data kuantitatif dan mempunyai rasa pengukuran yang berkaitan dengannya.

Dengan atribut angka seperti *pendapatan tahunan* atau *tempoh keahlian* sebagai atribut utama, sistem mencadangkan segmen yang mempunyai nilai purata yang lebih tinggi atau lebih rendah pada atribut angka apabila dibandingkan dengan semua pelanggan.

Atribut berkategori seperti *kepuasan pelanggan* sebagai hasil utama dalam segmen yang dicadangkan mempunyai peratusan pelanggan yang lebih tinggi dan lebih rendah mengikut kategori tertentu apabila dibandingkan dengan peratusan semua pelanggan yang dimiliki oleh kategori yang sama. Sebagai contoh, *kepuasan pelanggan* dipilih sebagai atribut utama dan ia terdiri daripada tiga kategori (*Rendah*, *Sederhana* dan *Tinggi*). Bagi setiap kategori, segmen akan dicadangkan yang mempunyai peratusan pelanggan yang lebih tinggi atau lebih rendah yang dimiliki oleh kategori tersebut berbanding dengan perkadaran semua pelanggan dalam kategori yang sama. Jika 22% daripada semua pelanggan mempunyai kepuasan *Tinggi*, kemudian, hanya segmen yang mempunyai perkadaran pelanggan yang lebih tinggi atau lebih rendah dengan kepuasan *Tinggi* berbanding dengan 22% akan dicadangkan untuk kategori tersebut. Begitu juga, segmen akan dicadangkan untuk setiap kategori lain (*Rendah* dan *Sederhana*) jika ia mempunyai statistik penting.

> [!NOTE]
> Pada masa ini, kami hanya menyokong atribut pengkategoran utama yang mempunyai sehingga 10 kategori. Jika anda mahu melihat cadangan segmen berdasarkan atribut utama dengan lebih daripada 10 kategori, kami mengesyorkan untuk mengumpulkan sebahagian daripada kategori untuk mengurangkan bilangan kategori kepada 10 atau lebih kurang. Pengehadan ini hanya diguna pakai untuk atribut utama. Untuk mempengaruhi atribut berkategori, kami kini menyokong maksimum 100 kategori.

## <a name="generate-suggested-segments"></a>Menjana segmen yang dicadangkan

1. Pergi ke **Segmen**.

1. Pilih tab **Cadangan (pratonton)**.

1. Pilih **Dapatkan cadangan baharu** untuk memulakan pengalaman berpandu.

1. Pilih langkah atau atribut pelanggan sebagai atribut utama dan pilih **Seterusnya**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Memilih atribut utama untuk cadangan mengenai segmen yang dicadangkan.":::

1. Pilih atribut yang mempengaruhi dan pilih **Simpan**.
   
   > [!TIP]
   > Memilih atribut mempengaruh berganda yang meningkatkan peluang untuk menilai cara ia mempengaruhi atribut utama. Jangan sertakan atribut yang tidak mempengaruhi atribut utama. Contohnya, jika semua pelanggan anda daripada negara tertentu, jangan sertakan atribut *negara* kerana ia tidak akan mempunyai sebarang kesan ke atas output tersebut.

1. Bergantung pada bilangan profil pelanggan dan atribut yang dipilih, ia boleh mengambil masa beberapa minit untuk memproses atribut yang dipilih. 

## <a name="view-details-of-a-suggested-segment"></a>Lihat butiran segmen yang dicadangkan

Sebaik sahaja model AI telah menjana cadangan, anda akan mendapati mereka disenaraikan pada **Segmen** > **Cadangan (pratonton)**.
 
Pilih segmen yang dicadangkan untuk semak semula butiran cadangan tersebut. Anda juga boleh menyemak nilai atribut atau peraturan yang dipelajari oleh model AI untuk mencadangkan segmen yang dipilih.

## <a name="save-a-suggestion-as-a-segment"></a>Simpan cadangan sebagai segmen

1. Pergi ke **Segmen** > **Cadangan (pratonton)**.

1. Pilih segmen yang anda mahu simpan. 

1. Dalam anak tetingkap sampingan, pilih **Simpan sebagai segmen**. 

1. Selepas menyimpan segmen itu, ia akan ditunjukkan dalam senarai segmen pada tab **Semua segmen**. Ia kini boleh [disegar semula, diedit atau dipadamkan seperti segmen lain](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Muatkan semula atau edit set cadangan

1. Pergi ke **Segmen** > **Cadangan (pratonton)**.

1. Pilih **Segar semula cadangan** untuk segar semula cadangan sambil menyimpan atribut yang dikonfigurasikan. Atau pilih **Edit atribut** untuk mengubah suai atribut yang dikonfigurasikan. Sistem akan menjalankan semula model AI, menjana cadangan segmen berdasarkan data terkini dan menggantikan cadangan semasa.

## <a name="limitations"></a>Had

1. Anggaran saiz segmen tidak sepadan: Jika anda memilih atribut utama yang mengandungi nilai kosong, ia boleh mempengaruhi anggaran saiz segmen dalam cadangan segmen. Apabila menyimpan segmen tersebut, saiz segmen sebenar boleh berbeza mengikut anggaran asal.
 
2. Atribut utama jenis Boolean tidak berfungsi: Pada masa ini, kami hanya menyokong jenis data rentetan dan berangka sebagai atribut utama.

3. Segmen yang dicadangkan tidak cukup jelas: Perlu diingati bahawa atribut yang dipilih dan pengagihan nilai atribut tersebut mempengaruhi keputusan. Anda boleh mengubah atribut yang mempengaruhi anda atau malah atribut utama anda untuk mendapatkan hasil yang berbeza.



[!INCLUDE[footer-include](../includes/footer-banner.md)]