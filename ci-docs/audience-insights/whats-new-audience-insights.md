---
title: Ciri baharu dan akan datang
description: Maklumat tentang ciri baharu, penambahbaikan dan pembetulan pepijat.
ms.date: 05/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: c66b37d6e4d6ed830238566fbc09934832892b34
ms.sourcegitcommit: 3f9981df97fa7b1f432a446d3f11936ea4cfbde5
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/06/2021
ms.locfileid: "5988931"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Perkara baharu dalam keupayaan cerapan khalayak Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kami berasa teruja untuk mengumumkan kemas kini terbaharu kami! Artikel ini meringkaskan ciri pratonton awam, penambahbaikan ketersediaan umum dan ciri kemas kini. Untuk melihat pelan ciri jangka panjang, sila lihat pada [Dynamics 365 dan Power Platform pelan keluaran](/dynamics365/release-plans/).

Kami melancarkan kemas kini berasaskan rantau demi rantau. Oleh itu, rantau tertentu mungkin melihat ciri sebelum orang lain. Melainkan dinyatakan berbeza, anda tidak perlu mengambil sebarang tindakan dan kami akan mengemas kini aplikasi secara automatik tanpa masa henti.

> [!TIP]
> Untuk menyerahkan dan mengundi tentang permintaan ciri dan cadangan produk, pergi ke [portal Idea Aplikasi Dynamics 365.](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="april-2021-updates"></a>Kemas kini April 2021

Kemas kini dalam bulan April 2021 termasuk beberapa ciri, peningkatan prestasi dan pembaikan pepijat.

### <a name="data-unification"></a>Penyatuan data
 
- **Pengalaman penggabungan yang dipertingkatkan untuk penyatuan data**    
  
   Kini, kami mempunyai pengalaman pengguna yang dipertingkatkan dalam konfigurasi gabungan untuk proses data penyatuan. Perubahan termasuk penyusunan intuitif bagi medan yang digabungkan dan statistik terperinci pada medan gabungan dan berunsur tunggal.

- **Penyusunan semula entiti dan konfigurasi semua rekod sumber ke dalam entiti Pelanggan**  
      
   Anda kini boleh menyusun semula dan mengalih keluar entiti daripada pelan penggabungan sedia ada dalam proses data penyatuan. Ia memberikan fleksibiliti untuk menyusun semula entiti dalam proses padanan mengikut keperluan perniagaan. Selain itu, kami mendayakan semua rekod tidak dipadankan ke dalam entiti *Pelanggan* yang membenarkannya mentakrif definisi set data profil pelanggannya.

### <a name="enrichments"></a>Pengayaan

 - **Pengayaan baharu: Alamat yang dipertingkatkan**    
  
   Kami gembira untuk memperkenalkan pengayaan baharu bagi meningkatkan alamat dalam data pelanggan anda. Alamat dalam data anda boleh tidak berstruktur, tidak lengkap atau tidak betul. Ciri ini menggunakan model Microsoft untuk menormalkan dan memperkayakan alamat anda ke dalam Format Model Data Tersuai untuk ketepatan dan wawasan yang lebih baik.
 
   Untuk maklumat lanjut, lihat [Pengayaan profil pelanggan dengan alamat yang dipertingkatkan](enrichment-enhanced-addresses.md).

- **Pengalaman konfigurasi berpandu untuk pengayaan**    
  
   Kami melawat semula pengalaman konfigurasi untuk pengayaan dengan pengalaman mudah dan berpandu. Anda kini mempunyai proses langkah demi langkah yang jelas untuk mencipta dan mengedit pengayaan.
 
   Selain itu, kami memisahkan konfigurasi sambungan pengayaan pihak ketiga bagi mendayakan sambungan yang sama untuk digunakan oleh berbilang pengayaan. Hanya pentadbir boleh mengkonfigurasikan sambungan baharu tetapi sambungan yang dicipta tersedia untuk kedua-dua pentadbir dan penyumbang.    

   Untuk maklumat lanjut, lihat [Gambaran keseluruhan sambungan](connections.md).

- **Pelbagai pengayaan untuk jenis yang sama**    
  
   Kami kini membenarkan pengguna untuk mencipta dan mengurus berbilang pengayaan daripada jenis pengayaan yang sama. Contohnya, anda kini boleh mencipta dua pengayaan alamat berasingan untuk memperkayakan dua segmen pelanggan yang berbeza. Had yang digunakan pada bilangan pengayaan daripada jenis yang sama boleh dicipta dan berbeza bergantung pada jenis pengayaan.
  
   Untuk maklumat lanjut, lihat [Pengayaan untuk profil pelanggan](enrichment-hub.md).

## <a name="march-2021-updates"></a>Kemas kini Mac 2021

Kemas kini pada bulan Mac 2021 termasuk beberapa ciri, peningkatan prestasi, dan pembaikan pepijat.

### <a name="activities"></a>Aktiviti

- **Wizard aktiviti dan jenis semantik**

   Kami telah meningkatkan dan mengemas kini pengalaman pemetaan aktiviti kami untuk membimbing dan memudahkan penciptaan pemetaan aktiviti. Dalam pengalaman baharu ini, pengguna mendapat pengalaman berpandu untuk membantu melengkapkan setiap langkah proses. Pada langkah pemetaan aktiviti, selain memilih dari pelbagai jenis aktiviti, pengguna boleh memilih untuk memetakan data secara semantik untuk *Langganan* dan/atau *SalesOrderLine* kepada skema standard industri, yang boleh digunakan untuk penggunaan hiliran.   

   Untuk maklumat lanjut, lihat [Aktiviti pelanggan](activities.md).

### <a name="data-ingestion"></a>Pengingesan data

- **Sambung ke sumber data di premis menggunakan aliran data dan get laluan Power Platform** Kami berbesar hati untuk mengumumkan pratonton untuk aliran data Power Platform dan kesambungan di premis menggunakan get laluan dalam Customer Insights dengan persekitaran Power Platform atau Dataverse yang berkaitan. Sebarang sumber data baharu yang dicipta dalam persekitaran Customer Insights dengan persekitaran Dataverse akan dilalaikan kepada aliran data Power Platform yang dibawa dalam kesambungan data di premis dan set sambungan yang kaya serta keupayaan transformasi.

### <a name="extensibility"></a>Kebolehpanjangan

- **Eksport diatur dalam sambungan dan eskport** Kami telah mengubah nama halaman **Destinasi eksport** kepada **Sambungan** dan menambah halaman berasingan untuk **Eksport**. Sebagai sebahagian daripada kemas kini ini, kami akan mengalih eksport sedia ada ke dalam pasangan sambungan dan eksport menggunakan sambungan tersebut. Pentadbir kini mempunyai lebih banyak kejelasan mengenai data keluar pada halaman **Sambungan**. Semua peranan pengguna mempunyai akses ke halaman **Eksport**, tetapi hanya pentadbir boleh memilih untuk membenarkan penyumbang untuk mengedit eksport tertentu dengan sambungan yang dikongsi.     
  Untuk maklumat lanjut, lihat [Gambaran keseluruhan sambungan](connections.md) dan [Gambaran keseluruhan eksport](export-destinations.md).

- **Eksport segmen ke Campaign Monitor** Kami telah memperluaskan destinasi eksport kami untuk merangkumi Campaign Monitor. Anda kini boleh mengeksport segmen daripada senarai Customer Insights ke Campaign Monitor dan menggunakannya sebagai garis dasar untuk kempen pemasaran anda.    
   Untuk maklumat lanjut, sila lihat [Eksport ke Campaign Monitor](export-campaign-monitor.md).

- **Eksport segmen ke Constant Contact** Kami telah memperluaskan destinasi eksport kami untuk merangkumi Constant Contact. Anda kini boleh mengeksport segmen daripada senarai Customer Insights ke Constant Contact dan menggunakannya sebagai garis dasar untuk kempen pemasaran anda.   
   Untuk maklumat lanjut, sila lihat [Eksport ke Constant Contact](export-constant-contact.md).

- **Eksport segmen ke RollWorks** Kami telah memperluaskan destinasi eksport kami untuk merangkumi RollWorks. Anda kini boleh mengeksport segmen daripada khalayak Customer Insights ke RollWorks dan menggunakannya sebagai garis dasar untuk pengiklanan B2B anda.    
   Untuk maklumat lanjut, sila lihat [Eksport ke RollWorks](export-rollworks.md).

- **Eksport segmen ke Snapchat** Kami telah memperluaskan destinasi eksport kami untuk merangkumi Snapchat. Anda kini boleh mengeksport segmen daripada khalayak Customer Insights ke Snapchat dan menggunakannya sebagai garis dasar untuk pengiklanan anda.     
   Untuk maklumat lanjut, sila lihat [Eksport ke Snapchat](export-snapchat.md).

### <a name="predictions"></a>Ramalan

- **Gunakan penapis produk dalam pengesyoran produk ramalan** Kami telah menambah keupayaan untuk menggunakan penapis produk dalam model pengesyoran produk kami. Anda kini boleh mencipta ramalan yang hanya menggunakan subset produk anda.    
   Untuk maklumat lanjut, lihat [Konfigurasikan penapis produk](predict-product-recommendation.md#configure-product-filters).

- **Cipta segmen daripada ramalan model** Kami telah menambah cara yang cepat untuk mencipta segmen menggunakan hasil model ramalan. Dari halaman hasil model, anda boleh mencipta segmen baharu dengan mudah dengan membuat pilihan **Cipta segmen** baharu.    
  Untuk maklumat lanjut, lihat [Cipta segmen berdasarkan model ramalan](prediction-based-segment.md).

- **Penjelasan untuk pengesyoran produk** Kami telah menambah maklumat yang menjelaskan faktor utama yang dipelajari oleh model AI untuk menjana pengesyoran produk dan sejauh mana faktor-faktor tersebut menyumbang ke arah pengesyoran produk. Maklumat ini ditambah pada skrin hasil model.    
   Untuk mendapatkan maklumat lanjut, lihat [Semak semula status dan keputusan ramalan](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Kemas kini Februari 2021

Kemas kini pada Februari 2021 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

#### <a name="extensibility"></a>Kebolehpanjangan

- **Eksport segmen ke AdRoll**

  Kami telah melanjutkan destinasi eksport kami untuk menyertakan AdRoll. Anda kini boleh mengeksport segmen daripada Customer Insights ke khalayak AdRoll dan menggunakan segmen tersebut sebagai garis dasar untuk pengiklanan anda. Untuk mendapatkan maklumat lanjut, lihat [Penyambung untuk AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmen
 
- **Duplikasikan segmen**
  
  Untuk mencipta segmen baharu berdasarkan segmen yang sedia ada, anda kini boleh menduplikasikan segmen dan mengedit segmen yang diduplikasikan untuk memperhalusi segmen tersebut dengan lebih lanjut. 

- **Tambah atribut tambahan ke segmen**

  Anda kini boleh menyertakan atribut dalam output segmen anda, walaupun atribut ini bukan sebahagian daripada profil pelanggan. Contohnya, termasuk ID langganan dalam segmen walaupun ia merupakan sebahagian daripada entiti langganan yang mempunyai perhubungan M:1 dengan entiti pelanggan. Selagi atribut dimiliki oleh entiti yang berkaitan dengan entiti pelanggan, anda kini boleh menyertakan atribut ini.  

#### <a name="predictions"></a>Ramalan

- **Cipta pengesyoran produk ramalan**

  Memahami perkara yang pelanggan berminat untuk membeli adalah salah satu langkah pertama yang diperlukan untuk meningkatkan pendapatan perniagaan dan membina kesetiaan pelanggan melalui pemeribadian dan penglibatan. Memberikan pengesyoran untuk produk yang tidak sejajar dengan kepentingan pelanggan anda boleh mencipta rasa hubungan terputus antara pelanggan dengan perniagaan anda dan akhirnya mengehadkan keseluruhan hasil dan pengalaman yang berpotensi untuk pelanggan. 

  Menggunakan data anda sendiri, anda kini boleh mencipta ramalan untuk produk yang bakal dibeli oleh pelanggan anda pada masa hadapan. Untuk mendapatkan maklumat lanjut, lihat [Ramalan pengesyoran produk](predict-product-recommendation.md).

#### <a name="system-administration"></a>Pentadbiran sistem

- **Salin persekitaran yang menyokong lebih banyak jenis sumber data**

  Pentadbir boleh menyalin konfigurasi persekitaran ke persekitaran baharu dalam organisasi yang sama. Ciri ini melanjutkan fungsi persekitaran salinan untuk kes yang sumber data berdasarkan himpunan data Common Data Service atau folder Common Data Model digunakan.

## <a name="january-2021-updates"></a>Kemas kini Januari 2021

Kemas kini pada Januari 2021 termasuk beberapa ciri, peningkatan prestasi dan pembetulan pepijat.

#### <a name="extensibility"></a>Kebolehpanjangan

- **Fungsi lanjutan dan prestasi yang dipertingkatkan untuk eksport SFTP** Anda kini boleh mengeksport semua entiti output dari Customer Insights ke hos SFTP. Sebelum ini, eksport terhad kepada entiti segmen. Di samping itu, prestasi eksport SFTP membolehkan lebih banyak jumlah data dalam masa yang kurang, bergantung kepada prestasi hos SFTP anda.    
  Untuk maklumat lanjut, lihat [Penyambung untuk SFTP (pratonton)](export-sftp.md).  

#### <a name="segments"></a>Segmen

- **Pembelajaran mesin dikuasakan telah mencadangkan segmen untuk meningkatkan metrik** Ada cara baharu untuk menemui dan mencipta segmen. Sistem menggunakan model AI untuk mencadangkan segmen yang boleh membantu meningkatkan KPI (ukuran) yang anda sudah jejaki. Kami menunjukkan sejauh mana pengaruh atribut yang anda pilih pada ukuran atau atribut utama lain. Maklumat ini membantu mencari segmen yang berpotensi yang membentangkan peluang.    
  Untuk maklumat lanjut, lihat [Segmen yang dicadangkan (pratonton)](suggested-segments.md).

#### <a name="data-unification"></a>Penyatuan data

- **Pengalaman padanan dipertingkatkan** Dalam kawasan penyatuan data, pengalaman sepadan telah dikemas kini. Ia membolehkan anda mengkonfigurasi dan melihat peraturan padanan, termasuk statistik terperinci untuk menerangkan lebih lanjut cara padanan berfungsi. Terdapat pilihan untuk menyahdayakan peraturan padanan supaya ia tidak lagi aktif sambil mengekalkan peraturan konfigurasi, seret dan lepas padanan, dan banyak lagi.
  Untuk maklumat lanjut, lihat [Padanan entiti](match-entities.md).

- **Output diduakan daripada proses padanan boleh didapati sebagai entiti** Output proses penduaani daripada proses padanana kini ditulis ke dalam entiti yang berasingan untuk analisis lanjut. Entiti ini terdiri daripada medan yang digunakan dalam proses penduaan dan rekod pemenang dan rekod alternatif yang sepadan yang digabungkan dengan rekod pemenang.
  Untuk maklumat lanjut, lihat [Output penduaan sebagai entiti](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Pentadbiran sistem

- **Kongsi data dengan lancar kepada Microsoft Dataverse** Anda kini boleh berkongsi output Customer Insights dengan aplikasi Microsoft Dataverse menggunakan Data Lake Microsoft Dataverse Terurus. Sebaik sahaja anda mengaitkan persekitaran Dataverse dengan Customer Insights, anda mendapat pilihan untuk mendayakan perkongsian data.
  Untuk maklumat lanjut, lihat [Uruskan persekitaran](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]