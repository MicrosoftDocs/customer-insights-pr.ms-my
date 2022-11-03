---
title: Aktiviti hubungan pelanggan atau perniagaan
description: Tentukan aktiviti hubungan pelanggan atau perniagaan dan lihatnya dalam garis masa pada profil pelanggan.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723792"
---
# <a name="customer-or-business-contact-activities"></a>Aktiviti hubungan pelanggan atau perniagaan

Aktiviti pelanggan adalah tindakan atau peristiwa yang dilakukan oleh pelanggan atau kenalan perniagaan. Sebagai contoh, transaksi, tempoh panggilan sokongan, ulasan laman web, pembelian, atau pulangan. Aktiviti ini terkandung dalam satu atau lebih sumber data. Dengan Wawasan Pelanggan, gabungkan aktiviti pelanggan anda daripada sumber [data ini](data-sources.md) dan kaitkannya dengan profil pelanggan. Aktiviti ini muncul secara kronologi dalam garis masa pada profil pelanggan. Sertakan [garis masa dalam aplikasi Dynamics 365 dengan penyelesaian tambahan](customer-card-add-in.md) Kad Pelanggan.

## <a name="define-a-customer-activity"></a>Tentukan aktiviti pelanggan

Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** untuk dimasukkan ke dalam garis masa pelanggan. Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.

1. Pergi ke **Aktiviti Data** > **·**.

1. Pilih **Tambah aktiviti** untuk memulakan pengalaman berpandu.

1. **Dalam langkah Data** aktiviti, masukkan maklumat berikut:

   - **Nama aktiviti**: Pilih nama untuk aktiviti anda.
   - **Entiti** aktiviti: Pilih entiti yang termasuk transaksi atau data aktiviti.
   - **Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

     > [!NOTE]
     > Kekunci Utama bagi setiap baris mesti kekal konsisten merentasi segar semula sumber data. Jika kunci Utama untuk baris dikemas kini dalam segar semula sumber data, ia mencipta pendua dalam entiti Aktiviti output. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Sediakan data aktiviti dengan nama, entiti dan kekunci utama.":::

1. Pilih **Seterusnya**.

1. **Dalam langkah Perhubungan**, pilih **Tambah perhubungan** untuk menyambungkan data aktiviti anda kepada rekod pelanggan yang sepadan. Langkah ini menggambarkan sambungan antara entiti.  

   - **Kunci** asing: Bidang asing dalam entiti aktiviti anda yang akan digunakan untuk menjalin hubungan dengan entiti lain.
   - **Kepada nama** entiti: Entiti pelanggan sumber yang sepadan dengan entiti aktiviti anda akan berhubung. Anda hanya boleh dikaitkan dengan entiti pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Nama** hubungan: Jika hubungan antara entiti aktiviti ini dan entiti pelanggan sumber terpilih sudah wujud, nama hubungan akan berada dalam mod baca sahaja. Jika tiada hubungan sedemikian wujud, hubungan baharu akan dicipta dengan nama yang anda berikan dalam kotak ini.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Takrifkan perhubungan entiti.":::

   > [!TIP]
   > Dalam persekitaran niaga-ke-niaga, anda boleh memilih antara entiti akaun dan entiti lain. Jika anda memilih entiti akaun, laluan perhubungan ditetapkan secara automatik. Untuk entiti lain, anda perlu mentakrifkan laluan perhubungan melalui satu atau lebih entiti pertengahan sehingga anda menjangkau entiti akaun.

1. Pilih **Gunakan** untuk mencipta perhubungan.

1. Pilih **Seterusnya**.

1. Dalam langkah **Penyatuan aktiviti**, pilih peristiwa aktiviti dan masa mula aktiviti anda.
   - **Medan diperlukan**
      - **Aktiviti peristiwa**: Medan untuk peristiwa bagi aktiviti ini.
      - **Cap waktu**: Medan yang mewakili masa mula aktiviti anda.

   - **Medan pilihan**
      - **Butiran tambahan**: Medan dengan maklumat berkaitan untuk aktiviti ini.
      - **Ikon**: Ikon yang terbaik mewakili jenis aktiviti ini.
      - **Alamat web**: Medan yang mengandungi URL dengan maklumat tentang aktiviti ini. Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini. URL ini boleh menjadi sebarang medan dari sumber data, atau ia boleh dibina sebagai medan baru menggunakan Power Query transformasi. Data URL akan disimpan dalam entiti *Aktiviti yang Disatukan* yang boleh digunakan secara hiliran menggunakan [API](apis.md).

   - **Tunjukkan dalam garis masa**
      - Pilih jika anda mahu menunjukkan aktiviti ini dalam pandangan garis masa pada profil pelanggan anda. Pilih **Ya** untuk menunjukkan aktiviti dalam garis masa atau **Tidak** untuk menyembunyikannya.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktiviti pelanggan dalam entiti Aktiviti yang Disatukan.":::

1. Pilih **Seterusnya** untuk memilih jenis aktiviti atau pilih **Selesai dan semak semula** untuk menyimpan aktiviti dengan jenis aktiviti yang disetkan kepada **Lain**.

1. Dalam langkah **Jenis Aktiviti**, pilih jenis aktiviti dan secara pilihan, pilih jika anda mahu memetakan secara semantik sebahagian daripada jenis aktiviti untuk digunakan dalam bahagian lain dalam Customer Insights. Pada masa ini, jenis aktiviti Maklum Balas, Kesetiaan, SalesOrder, *·* *SalesOrderLine* *dan* *Langganan* menyokong semantik selepas bersetuju untuk memetakan medan.*·* Jika jenis aktiviti tidak berkaitan dengan aktiviti baharu, anda boleh memilih *Lain-lain* atau *Cipta baharu* untuk jenis aktiviti yang tersuai.

1. Pilih **Seterusnya**.

1. Dalam langkah **Semak**, sahkan pilihan anda. Kembali ke mana-mana langkah sebelumnya dan kemas kini maklumat jika perlu.

1. Pilih **Simpan aktiviti** untuk menggunakan perubahan anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktiviti**. Aktiviti yang dibuat dipaparkan.

1. Selepas mencipta semua aktiviti anda, pilih **Jalankan** untuk memprosesnya.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-customer-activities"></a>Urus aktiviti pelanggan sedia ada

Pergi ke **Aktiviti** > **Data** untuk melihat aktiviti anda yang disimpan, entiti sumbernya, jenis aktiviti dan jika ia disertakan dalam garis masa pelanggan. Anda boleh mengisih senarai aktiviti mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari aktiviti yang ingin anda urus.

Pilih aktiviti untuk melihat tindakan yang tersedia.

- **Edit** aktiviti untuk mengubah konfigurasinya. Konfigurasi dibuka pada langkah semakan. Selepas mengubah konfigurasi, pilih **Simpan aktiviti** dan kemudian pilih **Jalankan** untuk memproses perubahan.
- **Namakan** semula aktiviti tersebut. Pilih **Simpan** untuk menggunakan perubahan anda.
- **Padamkan** aktiviti. Untuk memadamkan lebih daripada satu aktiviti sekaligus, pilih aktiviti **kemudian Padam**. Sahkan pemadaman.

## <a name="view-activity-timelines-on-customer-profiles"></a>Lihat garis masa aktiviti pada profil pelanggan

1. Jika anda memilih **Tunjukkan dalam garis** masa aktiviti dalam konfigurasi aktiviti, pergi ke **Pelanggan** dan pilih profil pelanggan untuk melihat aktiviti pelanggan dalam **seksyen Garis** masa aktiviti.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Lihat aktiviti yang dikonfigurasikan dalam Profil Pelanggan.":::

1. Untuk menapis aktiviti dalam garis masa aktiviti:

   - Pilih satu atau lebih ikon aktiviti untuk memperincikan hasil anda untuk menyertakan jenis yang dipilih sahaja.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Tapis aktiviti mengikut jenis menggunakan ikon.":::

   - Pilih **Penapis** untuk membuka panel penapis untuk mengkonfigurasikan penapis garis masa anda. Tapis mengikut *Jenis* Aktiviti dan/atau *Tarikh*. Pilih **Guna**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gunakan panel penapis untuk mengkonfigurasikan syarat penapis.":::

> [!NOTE]
> Penapis aktiviti akan dialih keluar apabila anda meninggalkan profil pelanggan. Anda perlu menggunakannya setiap kali anda membuka profil pelanggan.

## <a name="define-a-contact-activity"></a>Tentukan aktiviti kenalan

Untuk akaun perniagaan (B-to-B), gunakan *entiti ContactProfile* untuk menangkap aktiviti kenalan. Anda boleh melihat dalam garis masa aktiviti untuk akaun yang kenalan bertanggungjawab untuk setiap aktiviti. Kebanyakan langkah mengikuti konfigurasi pemetaan aktiviti pelanggan.

   > [!NOTE]
   > Untuk menentukan aktiviti peringkat kenalan, entiti ContactProfile *mesti dicipta,* sama ada sebagai [profil](data-unification-contacts.md) kenalan bersatu atau melalui [pemetaan](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) semantik.
   >
   > Anda mesti mempunyai **atribut AccountID dan** ContactID **untuk** setiap rekod dalam data aktiviti anda.
  
1. Pergi ke **Aktiviti Data** > **·**.

1. Pilih **Tambah Aktiviti**.

1. **Dalam langkah Data** aktiviti, masukkan maklumat berikut:

   - **Nama aktiviti**: Pilih nama untuk aktiviti anda.
   - **Entiti** aktiviti: Pilih entiti yang termasuk transaksi atau data aktiviti.
   - **Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

     > [!NOTE]
     > Kekunci Utama bagi setiap baris mesti kekal konsisten merentasi segar semula sumber data. Jika kunci Utama untuk baris dikemas kini dalam segar semula sumber data, ia mencipta pendua dalam entiti Aktiviti output. 


1. **Dalam langkah Perhubungan**, cipta hubungan tidak langsung antara data sumber aktiviti anda ke akaun, menggunakan data kenalan anda sebagai entiti perantara. Untuk maklumat lanjut, lihat [laluan perhubungan langsung dan tidak langsung](relationships.md#relationship-paths).
   - Contoh perhubungan untuk aktiviti yang dipanggil *Pembelian*:
      - **Membeli Data Hubungan Data** > **Aktiviti** Sumber pada atribut **ContactID**
      - **Hubungi Data Akaun Data** > **pada** atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Contoh persediaan perhubungan.":::

1. Selepas menyediakan perhubungan, pilih **Berikut** dan lengkapkan konfigurasi pemetaan aktiviti anda. Untuk langkah terperinci tentang penciptaan aktiviti, lihat [menentukan aktiviti](#define-a-customer-activity) pelanggan.

1. Jalankan pemetaan aktiviti anda.

1. Aktiviti peringkat hubungan anda kini akan kelihatan pada garis masa pelanggan anda.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Hasil akhir selepas mengkonfigurasikan aktiviti kenalan":::

## <a name="contact-level-activity-timeline-filtering"></a>Penapisan garis masa aktiviti peringkat kenalan

Selepas mengkonfigurasi pemetaan aktiviti peringkat kenalan dan menjalankannya, garis masa aktiviti untuk pelanggan anda akan dikemas kini. Ia termasuk ID atau nama mereka, bergantung pada konfigurasi ContactProfile *anda*, untuk aktiviti yang mereka lakukan. Anda boleh menapis aktiviti mengikut kenalan dalam garis masa untuk melihat kenalan tertentu yang anda minati. Selain itu, anda boleh melihat semua aktiviti yang tidak diperuntukkan kepada kenalan tertentu dengan memilih **Aktiviti yang tidak dipetakan pada Kenalan**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Pilihan penapisan tersedia untuk aktiviti peringkat Kenalan.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
