---
title: Aktiviti pelanggan
description: Mentakrifkan aktiviti pelanggan dan melihat aktiviti tersebut dalam garis masa pada profil pelanggan.
ms.date: 07/22/2022
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
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188150"
---
# <a name="customer-activities"></a>Aktiviti pelanggan

Aktiviti pelanggan adalah tindakan atau acara yang dilakukan oleh pelanggan. Contohnya, transaksi, tempoh panggilan sokongan, ulasan laman web, pembelian atau pulangan. Aktiviti-aktiviti ini terkandung dalam satu atau lebih sumber data. Dengan Wawasan Pelanggan, gabungkan aktiviti pelanggan anda daripada sumber [data ini](data-sources.md) dan kaitkannya dengan profil pelanggan. Aktiviti-aktiviti ini muncul secara kronologi dalam garis masa pada profil pelanggan. Sertakan garis masa dalam aplikasi Dynamics 365 dengan [penyelesaian tambahan](customer-card-add-in.md) Kad Pelanggan.

## <a name="define-an-activity"></a>Takrifkan aktiviti

Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** untuk disertakan dalam garis masa pelanggan. Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.

1. Pergi ke **Aktiviti Data** > **·**.

1. Pilih **Tambah aktiviti** untuk memulakan pengalaman berpandu.

1. **Dalam langkah Data** aktiviti, masukkan maklumat berikut:

   - **Nama aktiviti**: Nama untuk aktiviti anda.
   - **Entiti aktiviti**: Entiti yang termasuk data transaksi atau aktiviti.
   - **Kekunci** utama: Medan yang mengenal pasti rekod secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Sediakan data aktiviti dengan nama, entiti dan kekunci utama.":::

1. Pilih **Seterusnya**.

1. **Dalam langkah Perhubungan**, pilih **Tambah perhubungan** untuk menyambungkan data aktiviti anda ke rekod pelanggan yang sepadan dengannya. Langkah ini menggambarkan sambungan antara entiti.  

   - **Kunci asing daripada entiti**: Medan dalam entiti aktiviti anda yang akan digunakan untuk mewujudkan hubungan dengan entiti lain.
   - **Kepada nama** entiti: Entiti pelanggan sumber yang sepadan dengan entiti aktiviti anda akan berada dalam hubungan. Anda hanya boleh dikaitkan dengan entiti pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Nama** perhubungan: Nama mengenal pasti hubungan antara entiti. Jika perhubungan antara entiti aktiviti ini dan entiti pelanggan sumber yang dipilih sudah wujud, nama perhubungan adalah baca sahaja.

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
      - **Alamat web**: Medan yang mengandungi URL dengan maklumat tentang aktiviti ini. Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini. URL ini boleh menjadi mana-mana medan daripada sumber data, atau ia boleh dibina sebagai medan baharu menggunakan Power Query transformasi. Data URL akan disimpan dalam entiti *Aktiviti yang Disatukan* yang boleh digunakan secara hiliran menggunakan [API](apis.md).

   - **Tunjukkan dalam garis masa**
      - Pilih jika anda mahu menunjukkan aktiviti ini dalam pandangan garis masa pada profil pelanggan anda. Pilih **Ya** untuk menunjukkan aktiviti dalam garis masa atau **Tidak** untuk menyembunyikannya.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktiviti pelanggan dalam entiti Aktiviti yang Disatukan.":::

1. Pilih **Seterusnya** untuk memilih jenis aktiviti atau pilih **Selesai dan semak semula** untuk menyimpan aktiviti dengan jenis aktiviti yang disetkan kepada **Lain**.

1. Dalam langkah **Jenis Aktiviti**, pilih jenis aktiviti dan secara pilihan, pilih jika anda mahu memetakan secara semantik sebahagian daripada jenis aktiviti untuk digunakan dalam bahagian lain dalam Customer Insights. *Pada masa ini,* Maklum Balas *,* Kesetiaan *, JurujualOrder*, *SalesOrderLine*, dan *jenis aktiviti Langganan* menyokong semantik selepas bersetuju untuk memetakan medan. Jika jenis aktiviti tidak berkaitan dengan aktiviti baharu, anda boleh memilih *Lain-lain* atau *Cipta baharu* untuk jenis aktiviti yang tersuai.

1. Pilih **Seterusnya**.

1. Dalam langkah **Semak**, sahkan pilihan anda. Kembali ke mana-mana langkah sebelumnya dan kemas kini maklumat jika perlu.

1. Pilih **Simpan aktiviti** untuk menggunakan perubahan anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktiviti**. Paparan aktiviti yang dibuat.

1. Selepas mencipta semua aktiviti anda, pilih **Jalankan** untuk memprosesnya.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Urus aktiviti sedia ada

Pergi ke **Aktiviti** > **Data** untuk melihat aktiviti anda yang disimpan, entiti sumber mereka, jenis aktiviti dan jika ia disertakan dalam garis masa pelanggan. Anda boleh mengisih senarai aktiviti mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari aktiviti yang anda ingin uruskan.

Pilih aktiviti untuk melihat tindakan yang tersedia.

- **Edit** aktiviti untuk mengubah konfigurasinya. Konfigurasi dibuka pada langkah semakan. Selepas mengubah konfigurasi, pilih **Simpan aktiviti** dan kemudian pilih **Jalankan** untuk memproses perubahan.
- **Namakan semula** aktiviti. Pilih **Simpan** untuk menggunakan perubahan anda.
- **Padamkan** aktiviti. Untuk memadamkan lebih daripada satu aktiviti sekaligus, pilih aktiviti dan kemudian **Padam**. Sahkan pemadaman.

## <a name="view-activity-timelines-on-customer-profiles"></a>Lihat garis masa aktiviti pada profil pelanggan

1. Jika anda memilih **Tunjukkan dalam garis masa** aktiviti dalam konfigurasi aktiviti, pergi ke **Pelanggan** dan pilih profil pelanggan untuk melihat aktiviti pelanggan dalam **bahagian Garis masa** Aktiviti.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Lihat aktiviti yang dikonfigurasikan dalam Profil Pelanggan.":::

1. Untuk menapis aktiviti dalam garis masa aktiviti:

   - Pilih satu atau lebih ikon aktiviti untuk memperincikan hasil carian anda untuk memasukkan jenis yang dipilih sahaja.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Tapis aktiviti mengikut jenis menggunakan ikon.":::

   - Pilih **Penapis** untuk membuka panel penapis untuk mengkonfigurasi penapis garis masa anda. Tapis mengikut *Jenis* Aktiviti dan/atau *Tarikh*. Pilih **Guna**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Gunakan panel penapis untuk mengkonfigurasikan syarat penapis.":::

1. Untuk mengalih keluar penapis, pilih **Kosongkan penapis** atau pilih **Tapis** dan kosongkan kotak semak penapis.

> [!NOTE]
> Penapis aktiviti akan dialih keluar apabila anda meninggalkan profil pelanggan. Anda perlu menggunakannya setiap kali anda membuka profil pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
