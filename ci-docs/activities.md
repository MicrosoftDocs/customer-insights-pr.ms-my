---
title: Aktiviti pelanggan
description: Mentakrifkan aktiviti pelanggan dan melihat aktiviti tersebut dalam garis masa pada profil pelanggan.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755509"
---
# <a name="customer-activities"></a>Aktiviti pelanggan

Gabungkan aktiviti pelanggan daripada [pelbagai sumber data](data-sources.md) dalam Dynamics 365 Customer Insights. Buat garis masa yang menyenaraikan aktiviti secara kronologi. Sertakan garis masa dalam aplikasi Dynamics 365 dengan [penyelesaian tambahan](customer-card-add-in.md) Kad Pelanggan.

## <a name="define-an-activity"></a>Takrifkan aktiviti

Sumber data anda boleh termasuk entiti dengan data transaksi dan aktiviti daripada berbilang sumber data. Kenal pasti entiti ini dan pilih aktiviti yang anda mahu lihat pada garis masa pelanggan. Pilih entiti yang mengandungi sasaran aktiviti atau aktiviti anda.

Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** yang akan dimasukkan dalam garis masa pelanggan dan anda tidak boleh menambah entiti tanpa medan **Tarikh**. Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.

1. Pergi ke **Aktiviti Data** > **·**.

1. Pilih **Tambah aktiviti** untuk memulakan pengalaman berpandu untuk proses persediaan aktiviti.

1. Dalam langkah **Data aktiviti**, tetapkan nilai untuk medan berikut:

   - **Nama aktiviti**: Pilih nama untuk aktiviti anda.
   - **Entiti**: Pilih entiti yang mengandungi data transaksi atau aktiviti.
   - **Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Sediakan data aktiviti dengan nama, entiti dan kekunci utama.":::

1. Pilih **Seterusnya** untuk pergi ke langkah seterusnya.

1. Dalam langkah **Perhubungan**, konfigurasikan butiran untuk menyambungkan data aktiviti anda kepada rekod pelanggan yang sepadan. Langkah ini menggambarkan sambungan antara entiti.  

   - **Pertama**: Medan asing dalam entiti aktiviti anda yang akan digunakan untuk mewujudkan perhubungan dengan entiti lain.
   - **Kedua**: Entiti pelanggan sumber yang sepadan dengan entiti aktiviti anda yang akan berada dalam perhubungan. Anda hanya boleh dikaitkan dengan entiti pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Ketiga**: Jika perhubungan antara entiti aktiviti ini dan entiti pelanggan sumber yang dipilih telah wujud, nama perhubungan akan berada dalam mod baca sahaja. Jika tiada hubungan sedemikian wujud, hubungan baharu akan dicipta dengan nama yang anda berikan dalam kotak ini.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Takrifkan perhubungan entiti.":::

   > [!TIP]
   > Dalam persekitaran niaga-ke-niaga, anda boleh memilih antara entiti akaun dan entiti lain. Jika anda memilih entiti akaun, laluan perhubungan ditetapkan secara automatik. Untuk entiti lain, anda perlu mentakrifkan laluan perhubungan melalui satu atau lebih entiti pertengahan sehingga anda menjangkau entiti akaun.

1. Pilih **Seterusnya** untuk pergi ke langkah seterusnya. 

1. Dalam langkah **Penyatuan aktiviti**, pilih peristiwa aktiviti dan masa mula aktiviti anda. 
   - **Medan diperlukan**
      - **Aktiviti peristiwa**: Medan untuk peristiwa bagi aktiviti ini.
      - **Cap waktu**: Medan yang mewakili masa mula aktiviti anda.

   - **Medan pilihan**
      - **Butiran tambahan**: Medan dengan maklumat berkaitan untuk aktiviti ini.
      - **Ikon**: Ikon yang terbaik mewakili jenis aktiviti ini.
      - **Alamat web**: Medan yang mengandungi URL dengan maklumat tentang aktiviti ini. Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini. URL ini boleh menjadi mana-mana medan daripada sumber data, atau ia boleh dibina sebagai medan baharu menggunakan Power Query transformasi. Data URL akan disimpan dalam entiti *Aktiviti yang Disatukan* yang boleh digunakan secara hiliran menggunakan [API](apis.md).

   - **Tunjukkan dalam garis masa**
      - Pilih jika anda mahu menunjukkan aktiviti ini dalam pandangan garis masa pada profil pelanggan anda. Pilih **Ya** untuk menunjukkan aktiviti dalam garis masa atau **Tidak** untuk menyembunyikannya.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktiviti pelanggan dalam entiti Aktiviti yang Disatukan.":::

1. Pilih **Seterusnya** untuk beralih ke langkah yang seterusnya. Anda boleh memilih **Selesai dan semak** untuk menyimpan aktiviti sekarang dengan jenis aktiviti yang ditetapkan kepada **Lain-lain**. 

1. Dalam langkah **Jenis Aktiviti**, pilih jenis aktiviti dan secara pilihan, pilih jika anda mahu memetakan secara semantik sebahagian daripada jenis aktiviti untuk digunakan dalam bahagian lain dalam Customer Insights. *Pada masa ini,* Maklum Balas *,* Kesetiaan *, JurujualOrder*, *SalesOrderLine*, dan *jenis aktiviti Langganan* menyokong semantik selepas bersetuju untuk memetakan medan. Jika jenis aktiviti tidak berkaitan dengan aktiviti baharu, anda boleh memilih *Lain-lain* atau *Cipta baharu* untuk jenis aktiviti yang tersuai.

1. Pilih **Seterusnya** untuk beralih ke langkah yang seterusnya. 

1. Dalam langkah **Semak**, sahkan pilihan anda. Kembali ke mana-mana langkah sebelumnya dan kemas kini maklumat jika perlu.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Semak medan khusus untuk aktiviti.":::
   
1. Pilih **Simpan aktiviti** untuk menggunakan perubahan anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktiviti**. Di sini, anda melihat aktiviti yang ditetapkan untuk ditunjukkan dalam garis masa. 

1. Pada halaman **Aktiviti**, pilih **Jalankan** untuk memproses aktiviti. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Urus aktiviti sedia ada

Pada **Data** > **Aktiviti**, anda boleh melihat semua aktiviti yang disimpan dan menguruskannya. Setiap aktiviti diwakili oleh baris yang juga termasuk butiran mengenai sumber, entiti dan jenis aktiviti.

Tindakan berikut tersedia apabila anda memilih aktiviti. 

- **Edit**: Buka persediaan aktiviti pada langkah tinjauan. Anda boleh mengubah sebarang atau semua konfigurasi semasa daripada langkah ini. Selepas mengubah konfigurasi, pilih **Simpan aktiviti** dan kemudian pilih **Jalankan** untuk memproses perubahan.

- **Namakan semula**: Buka dialog untuk anda memasukkan nama lain bagi aktiviti yang dipilih. Pilih **Simpan** untuk menggunakan perubahan anda.

- **Padam**: Buka dialog untuk mengesahkan pemadaman aktiviti yang dipilih. Anda juga boleh memadamkan lebih daripada satu aktiviti sekaligus dengan memilih aktiviti dan kemudian memilih ikon padam. Pilih **Padam** untuk mengesahkan pemadaman.

## <a name="view-activity-timelines-on-customer-profiles"></a>Lihat garis masa aktiviti pada profil pelanggan

Selepas anda mengkonfigurasi aktiviti pelanggan, pilih **Tunjuk pada garis masa aktiviti** dalam konfigurasi aktiviti untuk mencari semua aktiviti pelanggan anda pada profil pelanggan mereka.

Untuk membuka garis masa untuk pelanggan, pergi ke **Pelanggan** dan pilih profil pelanggan yang anda mahu lihat.

Jika pelanggan telah mengambil bahagian dalam aktiviti yang dikonfigurasikan, anda akan menemuinya dalam **bahagian Garis masa** Aktiviti.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Lihat aktiviti yang dikonfigurasikan dalam Profil Pelanggan.":::

Terdapat beberapa cara untuk menapis aktiviti dalam garis masa aktiviti:

- Anda boleh memilih satu atau banyak ikon aktiviti untuk memperhalusi hasil anda untuk memasukkan jenis yang dipilih sahaja.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Tapis aktiviti mengikut jenis menggunakan ikon.":::

- Anda boleh memilih **Penapis** untuk membuka panel penapis untuk mengkonfigurasikan penapis garis masa anda.

   1. Anda boleh menapis mengikut *ActivityType* dan *Tarikh*
   1. Pilih **Gunakan** untuk menggunakan penapis dalam garis masa aktiviti.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gunakan panel penapis untuk mengkonfigurasikan syarat penapis.":::

Untuk mengalih keluar penapis, pilih **x** bersebelahan dengan setiap penapis yang digunakan pada garis masa atau pilih **Kosongkan penapis**.


> [!NOTE]
> Penapis aktiviti akan dialih keluar apabila anda meninggalkan profil pelanggan. Anda perlu menggunakannya setiap kali anda membuka pada profil pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
