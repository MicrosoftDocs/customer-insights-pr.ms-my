---
title: Ciri baharu dan akan datang
description: Maklumat tentang ciri baharu, penambahbaikan dan pembetulan pepijat.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/30/2020
ms.locfileid: "4650015"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Perkara baharu dalam keupayaan cerapan khalayak Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kami berasa teruja untuk mengumumkan kemas kini terbaharu kami! Artikel ini meringkaskan ciri pratonton awam, penambahbaikan ketersediaan umum dan ciri kemas kini. Untuk melihat pelan ciri jangka panjang, sila lihat pada [Dynamics 365 dan Power Platform pelan keluaran](https://docs.microsoft.com/dynamics365/release-plans/).

Anda juga boleh menonton video berikut untuk mengetahui lebih lanjut tentang keupayaan yang dirancang untuk enam bulan yang lalu.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Kami melancarkan kemas kini berasaskan rantau demi rantau. Oleh itu, rantau tertentu mungkin melihat ciri sebelum orang lain. Melainkan dinyatakan berbeza, anda tidak perlu mengambil sebarang tindakan dan kami akan mengemas kini aplikasi secara automatik tanpa masa henti.

> [!TIP]
> Untuk menyerahkan dan mengundi tentang permintaan ciri dan cadangan produk, pergi ke [portal Idea Aplikasi Dynamics 365.](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Kemas kini November 2020

Kemas kini pada November 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-november-2020"></a>Ciri baharu dan yang dikemas kini pada November 2020

#### <a name="data-enrichment"></a>Pengayaan data

- **Bawa data pengayaan anda sendiri melalui import tersuai Protokol Pemindahan Fail Selamat (SFTP)**
  
  Import tersuai SFTP membolehkan anda untuk mengimport data pengayaan yang tidak perlu melalui proses penyatuan data. Ketahui lebih lanjut tentang import tersuai SFTP.

  Untuk mendapatkan maklumat lanjut, lihat [Memperkayakan profil pelanggan dengan data tersuai (pratonton)](enrichment-SFTP-custom-import.md).
 
- **Memperkayakan data pelanggan anda dengan data lokasi daripada HERE Technologies**

  Dengan perkhidmatan pengayaan data HERE Technologies, anda boleh membina pemahaman lokasi yang lebih tepat tentang pelanggan anda dengan normalisasi alamat, latitud serta pengekstrakan longitud dan banyak lagi. Ketahui lebih lanjut tentang memperkayakan dengan HERE Technologies.

  Untuk mendapatkan maklumat lanjut, lihat [Pengayaan profil pelanggan dengan HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Penyatuan data

- **Kefleksibelan untuk mendayakan pemprofilan data pada entiti dan medan terpilih daripada akaun storan anda**

  Anda boleh menunjukkan entiti dan medan data daripada folder Common Data Model dalam akaun storan Azure Data Lake anda yang anda mahu dayakan pemprofilan data sebagai sebahagian daripada proses pengingesan data.

  Untuk mendapatkan maklumat lanjut, lihat [Sambungkan kepada folder Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Kebolehpanjangan

- **Aktifkan segmen anda melalui Google Ads**

  Eksport segmen daripada senarai khalayak Google Ads dan gunakan senarai ini untuk mengiklankan pada Carian Google, Rangkaian Paparan Google, YouTube dan Gmail. Ketahui lebih lanjut tentang mengaktifkan segmen anda melalui Google Ads.

  Untuk mendapatkan maklumat lanjut, lihat [Penyambung untuk Google Ads](export-google-ads.md).

- **Aktifkan segmen anda melalui Marketo**

  Eksport segmen ke khalayak Marketo dan gunakan khalayak ini untuk automasi pemasaran. Ketahui lebih lanjut tentang mengaktifkan segmen anda melalui Marketo. 

  Untuk mendapatkan maklumat lanjut, lihat [Penyambung untuk Marketo](export-marketo.md).

- **Aktifkan segmen anda melalui DotDigital**

  Eksport segmen ke DotDigital dan gunakan segmen ini untuk tujuan pemasaran. Ketahui lebih lanjut tentang mengaktifkan segmen anda melalui DotDigital. 

  Untuk mendapatkan maklumat lanjut, lihat [Penyambung untuk DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Ramalan

- **Ramalkan pulangan transaksi**

  Ciri ramalan pulangan transaksi membolehkan anda, tanpa bantuan saintis data, untuk meramalkan kemungkinan pelanggan berhenti membeli produk atau perkhidmatan.  Dengan menggunakan skor ramalan, anda boleh menggabungkan maklumat lain tentang pelanggan anda, seperti nilai pelanggan untuk mencipta segmen risiko pulangan tinggi atau pelanggan bernilai tinggi. Gunakan segmen ini untuk menyasarkan pelanggan secara langsung melalui aktiviti pemasaran, sokongan pelanggan dan senario lain untuk mengurangkan risiko pulangan.
 
  Konfigurasikan takrifan pulangan sebagai tetingkap berasaskan masa yang khusus untuk perniagaan anda dan tentukan bila pelanggan dianggap membuat pulangan. Contohnya, sebuah kedai runcit mungkin mahu mempertimbangkan pelanggan membuat pulangan jika mereka tidak membeli apa-apa dalam tempoh 30 hari yang lalu.
 
  Apabila anda meneruskan penciptaan ramalan, kami akan membimbing anda tentang data yang diperlukan dan membolehkan anda memetakan data tentang perniagaan anda kepada medan yang diperlukan untuk meramalkan pulangan bagi pelanggan anda. Anda juga boleh menetapkan jadual untuk melatih semula model berdasarkan maklumat baharu dalam sistem anda untuk disesuaikan dengan perubahan keadaan perniagaan.
 
  Untuk mendapatkan maklumat lanjut, lihat [Ramalan pulangan transaksi (pratonton)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Pentadbiran sistem

- **Tetap semula persekitaran**

  Tetapkan semula semua perkara dalam persekitaran tika yang dipilih untuk membuat permulaan baharu.

  Untuk maklumat lanjut, lihat [Tetapkan semula persekitaran sedia ada](manage-environments.md#reset-an-existing-environment).


- **Sambungkan kepada akaun storan Azure Data Lake anda menggunakan prinsipal perkhidmatan**

  Tulis output data dan baca data daripada akaun storan anda menggunakan prinsipal perkhidmatan Azure. Sambungan akaun storan sedia ada boleh terus menggunakan kunci akaun. Mereka juga menawarkan pilihan naik taraf untuk menggunakan prinsipal perkhidmatan pada masa akan datang. Sambungan baharu akan berdasarkan kaedah pengesahan prinsipal perkhidmatan untuk akaun storan anda.

  Untuk mendapatkan maklumat lanjut, lihat [Sambungkan kepada akaun Gen2 Azure Data Lake Storage dengan prinsipal perkhidmatan Azure untuk cerapan khalayak](connect-service-principal.md).

## <a name="october-2020-updates"></a>Kemas kini Oktober 2020

Kemas kini pada Oktober 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-october-2020"></a>Ciri baharu dan yang dikemas kini pada Oktober 2020

#### <a name="extensibility"></a>Kebolehpanjangan

- **Eksport ke Mailchimp**

Eksport segmen ke senarai khalayak sedia ada dalam Mailchimp bagi menyediakan pengalaman e-mel diperibadikan untuk pelanggan anda.

Untuk mendapatkan maklumat lanjut, lihat [Penyambung untuk Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Pengayaan data

- **Nyahduplikasikan rekod sumber dalam entiti Padanan**

Tentukan peraturan penyahduplikasi pada entiti yang digunakan dalam proses pemadanan untuk mengenal pasti rekod pendua. Gabungkannya dalam satu rekod dan pautkan semua rekod sumber pada rekod yang digabungkan ini. Rekod dinyahduplikasikan ini kemudiannya akan digunakan dalam proses pemadanan silang entiti.

Untuk mendapatkan maklumat lanjut, lihat [Takrifkan penyahduplikasi pada entiti padanan](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Pentadbiran sistem

- **Pengaturan: Pilihan segar semula baharu dalam Gabungan**

Sehingga hari ini, apabila anda menjalankan proses penggabungan, sistem menjalankan semua proses hiliran yang bergantung pada proses gabungan dan yang seterusnya. Kini anda boleh mengesahkan output untuk proses gabungan (entiti pelanggan disatukan) sebelum menggunakannya dalam pemprosesan hiliran seperti segmen atau langkah.
Pada halaman gabungan, anda kini boleh memilih untuk menjalankan langkah gabungan sahaja dan menjalankan proses ini sahaja. Untuk menyegarkan semula semua proses hiliran juga, anda boleh memilih untuk menjalankan proses gabung dan hiliran. 

## <a name="september-2020-updates"></a>Kemas kini September 2020

Kemas kini pada September 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-september-2020"></a>Ciri baharu dan kemas kini pada September 2020

#### <a name="activities"></a>Aktiviti

- **Ramalan pintar semantik atribut**

Ciri baharu ini meramalkan jenis semantik atribut input yang dihantar ke proses penyatuan data. Ia menggunakan model pembelajaran mesin yang meningkatkan ketepatan dan menjimatkan masa.

#### <a name="enrichments"></a>Pengayaan

- **Pengayaan demografi daripada Experian**

Pengayaan demografi daripada Experian kini boleh didapati dalam pratonton. Experian adalah peneraju global dalam pelaporan kredit pengguna dan perniagaan serta perkhidmatan pemasaran. Dengan [perkhidmatan pengayaan data Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), anda boleh membina pemahaman lebih mendalam mengenai pelanggan anda dengan memperkayakan profil pelanggan anda dengan data demografi seperti saiz isi rumah, pendapatan dan banyak lagi.

Untuk menggunakan ciri ini, anda mesti mempunyai langganan Experian yang aktif.

Untuk mendapatkan maklumat lanjut, lihat [Memperkayakan profil pelanggan dengan demografi daripada Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Pentadbiran sistem

- **Anak tetingkap butiran tugas**

Anak tetingkap butiran tugas membolehkan anda melihat butiran mengenai tugas yang sistem jalankan. Ini adalah cara yang berguna untuk mengenal pasti isu dengan konfigurasi dan mencari penyelesaian.
Semak mesej ralat lihat cara anda menangani isu berpotensi.
 
- **Memproses maklumat yang ditambah ke halaman tambahan**

Peningkatan ini menambahkan maklumat mengenai status entiti anda pada halaman **Entiti** dan **Pelanggan**.
 
Selain itu, anda boleh mendapatkan butiran mengenai perkembangan proses, bersama dengan butiran tugas, pada kedua-dua halaman ini.

- **Penambahbaikan ke atas halaman status sistem**

Kami mempertingkatkan struktur jadual butiran status pada **Sistem** > **Status** apabila menyemak eksport data.
 
Selain itu, ralat dalam lajur **Butiran** kini lebih terperinci dan boleh dilaksanakan. 
 
- **Batal kembalikan kerja semula ke keadaan sebelumnya**

Apabila anda membatalkan tugas, contohnya, dalam proses padanan, ia akan kembali semula ke keadaan terkini. Sebagai contoh, jika proses padanan selesai semalam dan anda membatalkannya hari ini, ia akan kembali ke keadaan berjaya semalam.


## <a name="august-2020-updates"></a>Kemas kini Ogos 2020

Kemas kini pada Ogos 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-august-2020"></a>Ciri baharu dan kemas kini pada Ogos 2020

#### <a name="data-unification"></a>Penyatuan data

- **Pengalaman yang ditambah baik untuk peringkat peta semasa data penyatuan**

  Pengalaman ke peringkat peta dalam proses penyatuan data membolehkan anda memilih entiti, atribut dan mentakrifkan semantik dengan cara yang lebih lancar.

  Perubahan termasuk:
  
  - interaksi lebih sedikit diperlukan untuk menambah entiti dan medan
  - keupayaan carian yang ditambah baik pada halaman peta
  - visual dan pengenalpastian mudah bagi jenis medan yang dicadangkan

#### <a name="enrichment"></a>Pengayaan

- **Pengayaan afiniti kepentingan yang tersedia dalam pasaran tambahan**

  Kami meluaskan ketersediaan pengayaan afiniti kepentingan di luar Amerika Syarikat untuk lima pasaran tambahan: Kanada, Australia, United Kingdom, Perancis dan Jerman. Dengan sambungan ini, anda boleh memperkayakan data pelanggan anda dengan minat tambahan yang berkaitan dengan pasaran ini. Kami juga akan memperkayakan profil pelanggan anda yang terletak di pasaran ini menggunakan data proprietari tempatan daripada Microsoft Graph.
  Untuk maklumat lanjut, lihat [Perkayakan profil pelanggan. dengan afiniti jenama dan kepentingan](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Kemas kini Julai 2020

Kemas kini pada Julai 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-july-2020"></a>Ciri baharu dan kemas kini dalam bulan Julai 2020

#### <a name="extensibility"></a>Muai

- Pencetus **Power Automate untuk proses penyatuan yang lengkap**

  Kami telah melanjutkan pencetus kami untuk Power Automate dan membolehkan anda mencipta pemberitahuan atau tindakan apabila segar semula proses penyatuan (peta, padan, gabung) dilengkapkan.    
  Untuk mendapatkan maklumat lanjut, lihat [Penyambung Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Pengayaan

- **Pengayaan afiniti jenama tersedia dalam pasaran tambahan**

  Kami memperluaskan ketersediaan pengayaan afiniti jenama melangkaui Amerika Syarikat kepada lima pasaran tambahan: Kanada, Australia, United Kingdom, Perancis dan Jerman. Dengan perluasan ini, anda boleh memperkayakan data pelanggan anda dengan jenama tempatan dalam pasaran ini. Kami juga akan memperkayakan profil pelanggan anda yang terletak di pasaran ini menggunakan data proprietari tempatan daripada Microsoft Graph.
  Untuk maklumat lanjut, lihat [Perkayakan profil pelanggan. dengan afiniti jenama dan kepentingan](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Kemas kini Jun 2020

Kemas kini pada Jun 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-june-2020"></a>Ciri baharu dan kemas kini dalam bulan Jun 2020

#### <a name="enrichment"></a>Pengayaan

- **Pengayaan dengan data syarikat daripada Leadspace**
  
  Takrifkan medan dalam profil pelanggan yang disatukan yang digunakan untuk mencari data syarikat berkaitan daripada Leadspace. Selepas menjalankan proses pengayaan, profil B2B diperkayakan dengan atribut tambahan termasuk saiz, lokasi, industri syarikat dan banyak lagi.    
  Kerjasama ini membolehkan anda menambah baik kualiti data anda dengan input daripada perkhidmatan pihak ketiga. Untuk menggunakan pengayaan ini, anda memerlukan lesen daripada Leadspace untuk mengakses data syarikat B2Bnya. Sistem akan menggunakan lesen itu untuk memastikan data anda diperkayakan secara berterusan.    
  Untuk maklumat lanjut, lihat [Pengayaan profil syarikat dengan Leadspace](enrichment-leadspace.md).

- **Halaman hab pengayaan**

  Semua pengayaan data yang tersedia daripada pembekal pengayaan pihak pertama dan ketiga dikonfigurasikan di tempat yang sama. Pengkonfigurasian pengayaan data ialah pengalaman lancar yang diuruskan daripada tempat yang sama.    
  Untuk maklumat lanjut, lihat [Pengayaan untuk profil pelanggan](enrichment-hub.md).

- **Asingkan pengayaan afiniti jenama dan kepentingan**

  Afiniti jenama dan kepentingan kini tersedia sebagai dua pengayaan yang bebas. Pengayaan yang diasingkan memberikan anda fleksibiliti untuk mengkonfigurasikan dan menguruskannya secara individu, bergantung pada keperluan perniagaan anda.    
  Untuk maklumat lanjut, lihat [Perkayakan profil pelanggan. dengan afiniti jenama dan kepentingan](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Muai

- **URL boleh klik untuk aktiviti yang disatukan pada Tambahan Kad Pelanggan Dynamics 365**

  Aktiviti disatukan dalam Tambahan Kad Pelanggan kini menunjukkan URL boleh klik jika URL tersebut telah ditakrifkan semasa konfigurasi aktiviti.    
  Untuk mendapatkan maklumat lanjut, lihat [Tambahan Kad Pelanggan](customer-card-add-in.md).

- **Afiniti jenama dan kepentingan tersedia pada Tambahan Kad Pelanggan Dynamics 365**

  Kawalan baharu pada Tambahan Kad Pelanggan Dynamics 365 membolehkan anda menunjukkan pengayaan jenama dan kepentingan pada kenalan anda dalam aplikasi penglibatan pelanggan dalam Dynamics 365.    
  Untuk mendapatkan maklumat lanjut, lihat [Tambahan Kad Pelanggan](customer-card-add-in.md).

- **Pencetus Power Automate tambahan**

  Kami telah memperluaskan pencetus kami untuk Power Automate dan telah menambahkan pencetus yang berikut:
  - Dapatkan pemberitahuan atau lakukan tindakan apabila segar semula penuh yang diautomatikkan (sumber data, penyatuan, segmen, ukuran, eksport) lengkap
  - Takrifkan ambang untuk ukuran perniagaan. Sebagai contoh, anda boleh mencipta pemberitahuan yang dihantar apabila ambang yang ditakrifkan dilepasi. Selain itu, pencetus membawa maklumat yang membolehkan anda membina aliran kerja yang lebih rumit dalam Power Automate.    
  Untuk mendapatkan maklumat lanjut, lihat [Penyambung Power Automate](export-power-automate.md)

- **Eksport ke Pengurus Iklan Facebook**
  
  Keupayaan ini membolehkan anda mengeksport segmen ke Pengurus Iklan Facebook. Segmen akan dieksport sebagai khalayak tersuai untuk menggunakan profil pelanggan disatukan dalam kempen dan iklan pemasaran Facebook. Khalayak tersuai juga berguna untuk mencipta kempen pada Instagram melalui Pengurus Iklan Facebook.    
  Untuk maklumat lanjut, lihat [Penyambung untuk Pengurus Iklan Facebook](export-facebook.md).

#### <a name="predictions"></a>Ramalan

- **Ramalan pulangan langganan**

  Ikut pengalaman berpandu untuk mencipta ramalan pulangan dalam kawasan langganan seperti perkhidmatan awan, keahlian pelanggan dan sektor lain. 

  Ciri ramalan pulangan langganan membolehkan anda meramal kemungkinan pelanggan menghentikan penggunaan produk atau perkhidmatan berdasarkan langganan tanpa melibatkan saintis data. Menggunakan skor ramalan, anda boleh menggabungkan maklumat lain tentang pelanggan anda untuk mencipta segmen risiko pulangan yang tinggi. Dengan bantuan segmen ini, anda boleh menyasarkan pelanggan secara langsung dalam pemasaran, sokongan pelanggan dan senario lain bagi mengurangkan risiko pulangan untuk pelanggan khusus dalam meningkatkan pendapatan dan mengurangkan kos.

  Berdasarkan pengalaman, anda boleh mengkonfigurasikan takrifan pulangan sebagai tetingkap berdasarkan masa khusus untuk perniagaan anda. Contohnya, perniagaan penstriman video yang mempunyai proses langganan bulanan mungkin mahu mempertimbangkan pelanggan anda mendapat pulangan selepas 15 hari selepas langganan mereka tamat tempoh.

  Ketika anda meneruskan melalui ramalan, kami akan membimbing anda melalui data yang diperlukan dan membolehkan anda memetakan data tentang perniagaan anda kepada medan yang diperlukan untuk meramalkan pulangan untuk pelanggan anda. Ketika maklumat perniagaan perubahan, anda juga boleh menetapkan jadual untuk melatih semula mengikut maklumat baharu dalam sistem anda bagi menyesuaikan keadaan perniagaan yang berubah.    
  Untuk maklumat lanjut, lihat [Ramalan pulangan langganan (pratonton)](predict-subscription-churn.md).

#### <a name="segments"></a>Bahagian

- **Cari pelanggan serupa**
  
  Cari pelanggan serupa dalam pangkalan pelanggan anda menggunakan kecerdikan buatan. Model pembelajaran mesin pengelasan perduaan menguntukkan skor keserupaan kepada pelanggan dalam segmen yang dikembangkan. Skor berasaskan pada persamaan kepada pelanggan dalam segmen sumber. Bergantung pada skor keserupaan, profil pelanggan ditambahkan pada segmen yang baharu dicipta.

  Kadang-kala dirujuk sebagai pemodelan serupa dalam pemasaran digital, ia menggunakan model AI untuk membantu mencari pelanggan yang serupa dengan segmen lain pelanggan anda dengan pemfaktoran dalam atribut tambahan. Ia bukan sahaja membolehkan anda memilih atribut tetapi juga membolehkan anda menentukan bilangan maksimum pelanggan yang patut berada dalam segmen baharu ini. Model AI kemudian akan mengira skor keserupaan untuk setiap pelanggan berdasarkan atribut yang anda pilih dan mencari pelanggan dengan skor keserupaan purata yang lebih tinggi. Segmen yang terhasil akan mengandungi pelanggan yang nampak serupa dengan pelanggan dalam segmen asal anda.    
  Untuk maklumat lanjut, lihat [Pelanggan Serupa](find-similar-customer-segments.md).

- **Tindanan dan pembeza segmen**

  Tindanan segmen membolehkan anda melihat jumlah dan pelanggan yang sama dengan dua atau lebih segmen. Contohnya, cara segmen orang berbelanja tinggi bertindan dengan segmen pelanggan kepuasan tinggi atau cara segmen pelanggan penggodakan bertindan dengan segmen pelanggan kepuasan rendah. Selain itu, anda boleh menganalisis cara tindanan berubah berdasarkan atribut tambahan pilihan anda.

  Pembeza segmen mendedahkan perkara yang membezakan satu segmen daripada pelanggan anda yang lain atau daripada segmen yang lain. Anda hanya perlu mengenal pasti segmen dan sistem akan mengenal pasti atribut dan ukuran profil yang membezakan segmen dalam bentuk senarai kedudukan pembeza—dari pembeza paling kuat hingga paling lemah.    
  Untuk maklumat lanjut, lihat [Cerapan segmen (pratonton)](segment-insights.md).

- **Hayat segmen**
  
  Takrifkan jadual untuk mengaktifkan atau menyahaktifkan segmen.    
  Untuk maklumat lanjut, lihat [Urus segmen sedia ada](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Kemas kini Mei 2020

Kemas kini pada Mei 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-may-2020"></a>Ciri baharu dan kemas kini dalam bulan Mei 2020

#### <a name="data-ingestion"></a>Pengingesan data

- **Pengingesan data masa nyata: pandangan sejarah**

  Apabila menggunakan API kami untuk menginges kemas kini masa nyata, anda boleh lihat sehingga 30 hari dari sejarah teragregat untuk kemas kini ini. Anda mempunyai akses untuk mengumpul semua panggilan API yang berjaya atau gagal termasuk hasil, sistem sumber dan metadata berguna lain.    
  Untuk maklumat lanjut, lihat [Pengingesan data masa nyata](real-time-data-ingestion.md).

- **Pengingesan data masa nyata: kemas kini profil**

  Pelanjutan pengingesan data masa nyata ini membolehkan anda melihat, dalam beberapa saat, perubahan pada medan profil pengguna khusus.    
  Selain fungsi masa nyata untuk aktiviti, sistem menyokong kemas kini kependaman rendah untuk medan profil. Kemas kini masa nyata untuk medan profil mempunyai masa tamat tempoh dan oleh itu bukan pengganti untuk menyegar semula yang dijadualkan.    
  Untuk maklumat lanjut, lihat [Pengingesan data masa nyata](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Muai

- **Garis masa dan penghalaman yang dikemas kini pada Tambahan Kad Pelanggan**

  Garis masa penyelesaian Tambahan Kad Pelanggan sepadan dengan garis masa aktiviti. Penghalaman garis masa yang dipertingkatkan, menunjukkan sehingga 50 aktiviti sekaligus. Ia juga membolehkan aktiviti tambahan dimuatkan dalam garis masa.    
  Untuk mendapatkan maklumat lanjut, lihat [Tambahan Kad Pelanggan](customer-card-add-in.md).

- **Power Automate mencetuskan perubahan bahagian**

  Mencetuskan untuk Power Automate mentakrifkan apa yang anda boleh bina dari aliran. Pencetus yang baru ditambah membenarkan anda mentakrifkan ambang untuk bahagian. Sebagai contoh, anda boleh mencipta pemberitahuan yang dihantar apabila ambang yang ditakrifkan dilepasi.    
  Untuk mendapatkan maklumat lanjut, lihat [Power Automate penyambung](export-power-automate.md).

- **Sokongan berbilang penyewa untuk model tersuai**

  Konfigurasikan aliran kerja untuk model tersuai dengan perkhidmatan web bagi penyewa Pembelajaran Mesin Azure yang berbeza. Anda boleh mendaftar masuk ke penyewa Azure Machine Learning semasa mencipta aliran kerja baharu untuk model tersuai. Keupayaan ini adalah tambahan kepada keupayaan sedia ada untuk mengintegrasikan dengan perkhidmatan web Pembelajaran Mesin Azure tersuai anda.    
  Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).

#### <a name="segments"></a>Bahagian

- **Automasi laluan entiti**

  Apabila mencipta segmen, pengguna perlu mentakrifkan laluan entiti. Keupayaan ini mengambil langkah pertama dalam mengautomatikkan definisi laluan entiti supaya anda boleh fokus pada kriteria pembahagian yang anda ada dalam fikiran.    
  Jika entiti yang anda mahu bahagikan pelanggan anda berkaitan secara langsung dengan entiti pelanggan yang disatukan, anda tidak perlu mentakrifkan laluan entiti lagi. Walau bagaimanapun, jika terdapat lebih daripada satu laluan entiti yang mungkin, anda masih perlu mentakrifkannya secara manual.

- **Tindakan pada berbilang bahagian**
  
  Pengguna boleh memilih berbilang bahagian dan mengambil tindakan ke atas mereka, seperti menyegar semula bahagian dengan satu klik.    

- **Segar semula segmen**

  Pengguna boleh menyegarkan semula bahagian tunggal atau memilih hanya bahagian yang mereka mahu segar semula.    

  
- **Peningkatan ke atas bahagian termajmuk**

  Pengguna boleh mencipta, mengedit dan memadamkan bahagian berdasarkan bahagian lain. Sebagai contoh, sebuah bahagian dibina pada bahagian lain yang dibina pada bahagian ketiga.    

- **Halaman senarai bahagian**

  Reka bentuk bahagian baharu untuk halaman menggunakan format senarai yang membolehkan anda melihat lebih banyak bahagian sekaligus. Medan carian ditambah untuk mencari bahagian dengan cepat. Pengguna kini boleh menggunakan tindakan seperti memuat turun atau memadamkan pada berbilang bahagian sekaligus. Pengalaman trend baharu diperkenalkan untuk mengenal pasti dengan cepat perubahan yang ketara pada bahagian.    
  Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

#### <a name="system-administration"></a>Pentadbiran sistem

- **Customer Insights tersedia dalam Microsoft Dynamics 365 Online Government**

  Dengan saluran yang semakin bertambah untuk berinteraksi, data warganegara bertaburan merentasi sistem yang pelbagai, membawa kepada data senyap dan maklumat pandangan terbahagi mengenai interaksi rakyat. Tanpa pandangan lengkap setiap interaksi setiap rakyat merentasi saluran, adalah mustahil untuk kerajaan memodenkan pada skala. Microsoft komited untuk menyokong keperluan teknologi kerajaan untuk mengekalkan jangkaan warga negara untuk pengalaman yang konsisten dan responsif.    
  Dengan gelombang 1 keluaran 2020, Dynamics 365 Customer Insights akan tersedia untuk Awan Komuniti Kerajaan (GCC), persekitaran yang dibina untuk memenuhi keperluan pematuhan yang lebih tinggi agensi kerajaan Amerika Syarikat. Agensi mendapat pandangan rakyat yang disatukan dan menggunakan AI prabina untuk mendapatkan wawasan yang menambah baik interaksi, memperkasakan pekerja dan mengubah komuniti, sambil mengurangkan kerumitan IT dan pematuhan mesyuarat Amerika Syarikat dan piawaian keselamatan. Dynamics 365 Government memenuhi keperluan mendesak Program Pengurusan Risiko Persekutuan AS dan Pengesahan (FedRAMP), mendayakan agensi persekutuan Amerika Syarikat untuk mendapatkan manfaat daripada penjimatan kos dan keselamatan yang ketat dari Microsoft Cloud.

## <a name="april-2020-updates"></a>Kemas kini April 2020

Kemas kini pada April 2020 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

### <a name="new-and-updated-features-in-april-2020"></a>Ciri baharu dan kemas kini dalam bulan April 2020

#### <a name="activities"></a>Aktiviti

- **Peta entiti aktiviti kepada jenis aktiviti standard**
  
  Konfigurasi aktiviti dan storan pada masa ini adalah berdasarkan reka bentuk statik untuk melihatnya dalam garis masa. Maksud semantik aktiviti, yang berpotensi untuk pelbagai kes guna dalam model AI, tidak digunakan sepenuhnya pada masa ini. Kami merancang untuk menjadikan garis masa aktiviti lebih dinamik, berdasarkan jenis aktiviti dan pemahaman semantik aktiviti dengan lebih baik. Ciri ini bertujuan untuk mengenal pasti jenis aktiviti seperti yang ditakrifkan dalam Common Data Model untuk sebarang aktiviti yang diinges.
  Untuk maklumat lanjut, lihat [Aktiviti pelanggan](activities.md).

#### <a name="data-ingestion"></a>Pengingesan data

- **Pengingesan data masa nyata: aktiviti**
  
  Pengingesan data masa nyata menyediakan data dengan serta-merta untuk penggunaan, sehingga segar semula dijadualkan yang seterusnya menarik data ini daripada sumber data.    
  Untuk maklumat lanjut, lihat [Pengingesan data masa nyata](real-time-data-ingestion.md).

- **Penambahbaikan kepada persediaan data**
  
  Ketahui lebih lanjut tentang data yang diinges dalam entiti. Dengan ringkasan data, anda boleh memahami ciri kualiti data yang boleh membantu untuk mengambil tindakan yang sesuai.    
  Untuk maklumat lanjut, lihat [Terokai data entiti](entities.md#exploring-a-specific-entitys-data).

- **Menginges data analitikal dari Dynamics 365 dengan Common Data Service**
  
  Common Data Service tersedia sebagai satu cara untuk mencipta sumber data. Pelanggan Dynamics 365 sedia ada boleh menginges entiti analitikal dari Common Data Service ke Customer Insights. Sumber data tunggal boleh menggunakan Lake diuruskan Common Data Service yang sama secara serentak dalam persekitaran Customer Insights.    
  Untuk maklumat lanjut, lihat [Connect ke data dalam data lake Common Data Service terurus](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Muai

- **Eksport ke LiveRamp**

  Aktifkan data anda dalam LiveRamp® untuk connect dengan lebih 500 platform merentasi ekosistem digital, sosial, dan TV. Manfaatkan data anda dalam LiveRamp untuk mensasarkan, menekan dan memperibadikan kempen iklan.    
  Untuk maklumat lanjut, lanjut [LiveRamp&reg; penyambung](export-liveramp.md).

- **Tambahan Pasukan Customer Insights**
  
  Bot menyediakan keupayaan carian untuk profil pelanggan disatukan. Ia akan menunjukkan kad sehingga 15 medan daripada profil pelanggan yang terhasil. Berbilang padanan mengembalikan senarai hasil di mana anda boleh memilih profil.    
  Untuk maklumat lanjut, lihat [Bot pasukan bagi Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Langkah

- **Ukur halaman senarai**
  
  Penambahbaikan ke halaman langkah termasuk sokongan untuk tindakan pada ukuran tunggal dan berbilang Langkah sekaligus. Selain itu, anda akan menemui medan carian untuk mencari dan menjejaki langkah dengan cepat.    
  Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

- **Penambahbaikan ke atas langkah termajmuk**
  
  Pengguna boleh mencipta, mengedit dan memadamkan langkah berdasarkan langkah lain. Sebagai contoh, langkah dibina pada langkah lain yang dibina pada langkah ketiga.

#### <a name="segments"></a>Bahagian

- **Operator tambahan**
  
  Operator dalam set membolehkan pembahagian untuk pelanggan dengan beberapa nilai rentetan yang mungkin. Sebelum operator ini ditambah, anda perlu membina bahagian tersebut dengan pelbagai ATAU syarat. Operator dalam set ini membenarkan anda melakukannya dengan satu syarat.    
  Untuk maklumat lanjut, lihat: [Cipta dan urus bahagian](segments.md).

#### <a name="system-administration"></a>Pentadbiran sistem

- **Salin tetapan konfigurasi ke persekitaran baharu**
  
  Salin konfigurasi anda daripada satu persekitaran kepada yang lain. Semasa mencipta persekitaran baharu, anda boleh memilih persekitaran sedia ada yang anda ingini untuk menyalin konfigurasi. Pada masa ini, kami menyokong sumber data, penyatuan data, perhubungan, langkah dan bahagian untuk disalin. Kelayakan sumber data dan data sebenar tidak disalin.    
  Untuk maklumat lanjut, lihat [Uruskan persekitaran](manage-environments.md).
