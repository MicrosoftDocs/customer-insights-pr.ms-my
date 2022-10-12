---
title: Menganalisis sentimen untuk maklum balas pelanggan (pratonton)
description: Ketahui cara menggunakan model analisis sentimen pada maklum balas pelanggan dalam Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610477"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Menganalisis sentimen dalam maklum balas pelanggan (pratonton)

Analisis sentimen membolehkan anda mensintesis sentimen pelanggan dan mengenal pasti aspek perniagaan sebagai peluang untuk penambahbaikan. Ciri Wawasan Pelanggan ini membantu anda memahami perkara yang berfungsi dengan baik dan perkara yang perlu anda atasi. Ia dapat membantu anda memacu tindakan perniagaan yang membolehkan pengalaman yang menghasilkan kepuasan dan kesetiaan pelanggan yang tinggi.

## <a name="overview"></a>Gambaran keseluruhan

Ciri analisis sentimen menjana dua pandangan yang diperoleh bagi setiap ID pelanggan. Skor sentimen (-5 hingga 5) dan senarai aspek perniagaan yang berkenaan (bidang perniagaan) yang bersama-sama membantu anda memahami maklum balas pelanggan dengan lebih baik.

Analisis ini membantu anda:
- Dapatkan gambaran keseluruhan sentimen pelanggan terhadap jenama atau organisasi
- Kenal pasti pelanggan dengan sentimen negatif untuk menumpukan kempen dan penglibatan anda dan mengoptimumkan pulangan yang lebih tinggi  
- Mengenal pasti aspek perniagaan dengan isu-isu yang ditunjukkan oleh pelanggan  
- Pelanggan segmen berdasarkan sentimen mereka untuk menjalankan kempen yang diperibadikan dengan jualan, pemasaran, dan usaha sokongan yang disasarkan
- Mengoptimumkan operasi perniagaan dengan menangani bidang kebimbangan atau peluang yang disebutkan oleh pelanggan
- Mengiktiraf aspek perniagaan yang dilakukan dengan baik dan memberi ganjaran kepada pelanggan gembira melalui program kesetiaan dan promosi

Model ini menyediakan senarai perkataan yang mempengaruhi keputusan model untuk memberikan skor sentimen tertentu atau aspek perniagaan kepada komen maklum balas.  

Kami menggunakan dua **model** Pemprosesan Bahasa Asli (NLP): Yang pertama memberikan setiap komen maklum balas skor sentimen. Model kedua mengaitkan setiap maklum balas dengan semua aspek perniagaan yang berkenaan. Model-model ini dilatih pada data awam dari sumber di seluruh media sosial, runcit, restoran, produk pengguna, dan industri automotif.
  
Aspek perniagaan yang dipratentukan untuk model mengaitkan dengan data maklum balas termasuk:
- Pengurusan akaun
- Daftar keluar dan pembayaran
- Sokongan pelanggan
- Pengambilan dalam kedai
- Penghantaran dan pengambilan pembungkusan
- Pra-pesanan
- Harga
- Privasi dan keselamatan
- Promosi dan ganjaran
- Resit dan waranti
- Pertukaran pengembalian dan pembatalan
- Ketepatan pemenuhan
- Kualiti laman web/aplikasi

> [!NOTE]
> Pada masa ini, kami hanya menyokong analisis sentimen mengenai maklum balas pelanggan bahasa Inggeris. Lebih banyak bahasa akan disokong pada masa akan datang. Jika maklum balas dalam bahasa lain dimuat naik, model masih akan mengembalikan hasil. Walau bagaimanapun, keputusan ini tidak akan tepat.

## <a name="prerequisites"></a>Prasyarat

- Sekurang-kurangnya [keizinan Penyumbang](permissions.md)
- [Data](data-unification.md) maklum balas teks disatukan. Kami sangat mengesyorkan agar anda [mengkonfigurasi entiti data maklum balas anda sebagai entiti](map-entities.md#select-primary-key-and-semantic-type-for-attributes) aktiviti jenis semantik (jenis Maklum Balas).
- ID Pelanggan Disatukan (UCID) daripada penyatuan data untuk memadankan rekod data maklum balas teks kepada pelanggan individu.
- ID maklum balas
- Cap masa maklum balas
- Teks maklum balas

Wawasan Pelanggan boleh memproses sehingga 10 juta rekod maklum balas untuk satu model dijalankan. Model ini boleh menganalisis komen maklum balas sehingga 128 perkataan. Sekiranya komen maklum balas lebih panjang, analisis hanya mempertimbangkan 128 perkataan pertama.

> [!NOTE]
> Hanya satu entiti maklum balas boleh dikonfigurasi. Sekiranya terdapat banyak entiti maklum balas, gabungkannya Power Query sebelum pengambilan data.

## <a name="configure-a-sentiment-analysis"></a>Mengkonfigurasikan analisis sentimen

1. Pergi ke **Ramalan** > **Perisikan**.

1. Pada tab **Cipta**, pilih **Gunakan model** pada **jubin Analisis sentimen Pelanggan (pratonton**).

1. Pilih **Mulakan**.

1. **Namakan** analisis dan berikan **nama** entiti output aspek Perniagaan dan **nama** entiti output skor Sentimen.

1. Pilih **Seterusnya**.

1. Pilih **Tambah data** untuk **maklum balas** Pelanggan.

1. Pilih jenis **aktiviti semantik Maklum balas** yang mengandungi data maklum balas. Jika aktiviti belum disediakan, pilih **di sini** dan buatnya.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Langkah konfigurasi untuk memilih aktiviti maklum balas untuk analisis sentimen.":::

1. Pilih aktiviti untuk digunakan bagi analisis sentimen ini, kemudian pilih **Seterusnya**.

1. Petakan atribut dalam data anda kepada atribut model. 

1. Pilih **Simpan**.

1. Pilih **Seterusnya**. Langkah **Semak semula dan jalankan** menunjukkan ringkasan konfigurasi dan menyediakan peluang untuk membuat perubahan sebelum anda mencipta analisis.

1. Pilih **Edit** pada sebarang langkah untuk menyemak semula dan membuat sebarang perubahan.

1. Jika anda berpuas hati dengan pilihan anda, pilih **Simpan dan jalankan** untuk mula menjalankan model. Pilih **Selesai**. Tab **Ramalan** saya dipaparkan semasa ramalan sedang dicipta. Proses mungkin mengambil masa beberapa jam untuk dilengkapkan bergantung kepada amaun data yang digunakan dalam ramalan.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Lihat keputusan analisis

1. Pergi ke **Ramalan** > **Perisikan**.

1. Dalam tab **Ramalan** saya, pilih ramalan yang anda ingin lihat.

Terdapat dua tab keputusan.

### <a name="sumary-tab"></a>Tab Sumari

Terdapat empat bahagian utama data dalam halaman hasil carian.

- **Skor sentimen purata**: Skor sentimen membantu anda memahami sentimen keseluruhan di semua pelanggan.
  - **Negatif** (-5 > 2)
  - **Neutral** (-1 > 1)
  - **Positif** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Perwakilan visual sentimen pelanggan keseluruhan.":::

- **Pengedaran pelanggan mengikut skor** sentimen: Pelanggan dikategorikan kepada kumpulan negatif, neutral dan positif berdasarkan skor sentimen mereka. Letakkan penuding di atas bar dalam histogram untuk melihat bilangan pelanggan dan skor sentimen purata dalam setiap kumpulan. Data ini boleh membantu anda [mencipta segmen pelanggan](prediction-based-segment.md) berdasarkan skor sentimen mereka.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Carta bar menunjukkan sentimen pelanggan merentasi tiga kumpulan sentimen.":::

- **Skor sentimen purata dari masa ke masa**: Sentimen pelanggan mungkin berubah dari semasa ke semasa. Kami menyediakan trend sentimen pelanggan anda untuk julat masa data anda. Pandangan ini membantu anda mengukur kesan promosi bermusim, pelancaran produk, atau campur tangan terikat masa lain pada sentimen pelanggan. Lihat graf dengan memilih tahun kepentingan daripada menu juntai bawah.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Carta sejarah dengan skor sentimen dari masa ke masa diwakili sebagai garis.":::

- **Sentimen merentasi aspek** perniagaan: Sentimen purata merentasi aspek perniagaan membantu anda mengukur aspek perniagaan anda yang sudah memuaskan pelanggan atau memerlukan lebih banyak perhatian. Rekod maklum balas yang tidak sejajar dengan mana-mana aspek perniagaan yang disokong dikategorikan di bawah **Lain- lain**. Isih data dengan memilih sebarang lajur.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Senarai aspek perniagaan dengan nilai sentimen yang berkaitan dan bilangan pelanggan yang menyebutnya.":::

  Pilih nama aspek perniagaan untuk melihat cara aspek perniagaan dikenal pasti oleh model:

  - **Kata-kata** berpengaruh: Kata-kata teratas yang mempengaruhi pengenalan model AI aspek perniagaan dalam maklum balas pelanggan.
    **Tunjukkan perkataan yang** menyinggung perasaan: Membolehkan anda memasukkan perkataan yang menyinggung perasaan dalam senarai daripada data maklum balas pelanggan asal. Secara lalai, ia dimatikan.  Topeng perkataan yang menyinggung perasaan dikuasakan oleh model AI dan mungkin tidak mengesan semua perkataan yang menyinggung perasaan. Jika anda mengesan perkataan menyinggung perasaan yang tidak ditapis seperti yang dijangkakan, beritahu kami.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Senarai perkataan berpengaruh dengan togol untuk menunjukkan atau menyembunyikan perkataan yang menyinggung perasaan.":::

  - **Sampel** maklum balas: Rekod maklum balas sebenar dalam data anda. Perkataan dikodkan warna mengikut pengaruhnya terhadap pengenalpastian aspek perniagaan.

### <a name="influential-words-analysis-tab"></a>Tab analisis perkataan berpengaruh

Terdapat tiga bahagian maklumat tambahan yang menerangkan bagaimana model sentimen berfungsi.
  
- **Kata-kata teratas menyumbang kepada sentimen** positif: Kata-kata teratas yang mempengaruhi pengenalan model AI sentimen positif dalam maklum balas pelanggan.  

- **Kata-kata teratas menyumbang kepada sentimen** negatif: Kata-kata teratas yang mempengaruhi pengenalan model AI sentimen negatif dalam maklum balas pelanggan.

- **Sampel** maklum balas: Rekod maklum balas sebenar, satu dengan sentimen negatif dan satu dengan sentimen positif. Kata-kata dalam rekod maklum balas diserlahkan mengikut sumbangan mereka kepada skor sentimen yang diberikan. Kata-kata yang menyumbang kepada skor sentimen positif diserlahkan dalam warna hijau. Kata-kata yang menyumbang kepada skor negatif diserlahkan dengan warna merah.
   Pilih **Lihat lagi** untuk memuatkan lebih banyak sampel maklum balas.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Contoh analisis sentimen mengenai maklum balas pelanggan.":::

**Tunjukkan perkataan yang** menyinggung perasaan: Membolehkan anda memasukkan perkataan yang menyinggung perasaan dalam senarai daripada data maklum balas pelanggan asal. Secara lalai, ia dimatikan.  Topeng perkataan yang menyinggung perasaan dikuasakan oleh model AI dan mungkin tidak mengesan semua perkataan yang menyinggung perasaan. Jika anda mengesan perkataan menyinggung perasaan yang tidak ditapis seperti yang dijangkakan, beritahu kami.

## <a name="act-on-analysis-results"></a>Bertindak ke atas keputusan analisis

Untuk mencipta segmen pelanggan baharu daripada hasil analisis sentimen, pilih **Buat segmen** di bahagian atas halaman hasil model.

## <a name="potential-bias"></a>Berat sebelah yang berpotensi

Seperti mana-mana ciri yang menggunakan kecerdasan buatan ramalan, mungkin terdapat potensi berat sebelah dalam data yang anda gunakan untuk meramalkan sentimen pelanggan. Sebagai contoh, jika anda hanya mengumpulkan maklum balas secara digital, anda mungkin terlepas maklum balas daripada pelanggan yang menjalankan perniagaan dengan anda secara peribadi, yang menjejaskan output ciri tersebut.

Oleh kerana ciri ini menggunakan cara automatik untuk menilai data dan membuat ramalan berdasarkan data tersebut, oleh itu ia mempunyai keupayaan untuk digunakan sebagai kaedah pemprofilan, kerana istilah itu ditakrifkan oleh Peraturan Perlindungan Data Umum ("GDPR"). Penggunaan anda bagi ciri ini untuk memproses data mungkin tertakluk pada GDPR atau perundangan atau peraturan lain. Anda bertanggungjawab untuk memastikan bahawa penggunaan Dynamics 365 Customer Insights anda, termasuk analisis sentimen, mematuhi semua undang-undang dan peraturan yang berkenaan, termasuk undang-undang yang berkaitan dengan privasi, data peribadi, data biometrik, perlindungan data, dan kerahsiaan komunikasi.

[!INCLUDE [footer-include](includes/footer-banner.md)]

