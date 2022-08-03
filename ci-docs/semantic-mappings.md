---
title: Pemetaan semantik (pratonton)
description: Gambaran keseluruhan pemetaan semantik dan cara untuk menggunakannya.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 7c9588ac7a132ca6f43cf26ea3a744109a0dd2b8
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183642"
---
# <a name="semantic-mappings-preview"></a>Pemetaan semantik (pratonton)

Semantik pemetaan membolehkan anda memetakan data bukan aktiviti anda kepada skema yang dipratentukan. Skema ini membantu Wawasan Pelanggan memahami atribut data anda dengan lebih baik. Pemetaan semantik dan data yang disediakan membolehkan cerapan dan ciri baharu dalam Wawasan Pelanggan. Untuk memetakan data aktiviti anda kepada pengguna skema, semak dokumentasi [aktiviti](activities.md).

**Pemetaan semantik pada masa ini didayakan untuk persekitaran berdasarkan akaun perniagaan**. *ContactProfile* adalah satu-satunya jenis pemetaan semantik yang tersedia pada masa ini dalam Wawasan Pelanggan.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Takrifkan pemetaan entiti semantik ContactProfile

1. Pergi ke **pemetaan Semantik Data** > **(pratonton)**.

1. Pilih **Tambah pemetaan semantik** untuk memulakan pengalaman dipandu.

1. Dalam langkah **Data entiti**, tetapkan nilai untuk medan berikut:

   - **Nama** pemetaan entiti semantik: Nama untuk pemetaan entiti semantik anda.
   - **Entiti** Sumber: Entiti yang termasuk data kenalan.
   - **Kekunci utama**: Medan yang mengenal pasti rekod kenalan secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Sediakan pemetaan entiti semantik dengan nama, entiti sumber dan kunci utama.":::

1. Pilih **Seterusnya**.

1. Dalam langkah **Perhubungan**, konfigurasikan butiran untuk menyambungkan data kenalan anda kepada data akaun yang sepadan. Langkah ini menggambarkan sambungan antara entiti.  

   Terdapat dua jenis laluan perhubungan yang boleh dilaksanakan: **Perhubungan langsung** dan **Perhubungan tidak langsung**. Untuk mendapatkan maklumat lanjut, pergi ke [laluan perhubungan langsung dan tidak langsung](relationships.md#relationship-paths).

   1. Pilih **Tambah Perhubungan** untuk mengkonfigurasi perhubungan.
   1. Pilih atribut daripada entiti sumber anda yang menyambungkan entiti kenalan anda ke entiti lain.
   1. Pilih entiti untuk menyambungkan entiti kenalan anda kepada. Pilih entiti daripada **entiti** Akaun atau bahagian **entiti** Perantaraan. Jika anda memilih entiti perantaraan, tentukan perhubungan kedua untuk menyambung ke entiti akaun sasaran anda.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pilih sama ada entiti Akaun atau entiti pertengahan.":::

   1. Berikan **Nama perhubungan**. Jika perhubungan antara entiti anda sudah wujud, nama perhubungan ialah baca sahaja. Jika tiada perhubungan wujud, perhubungan baharu akan dicipta dengan nama yang anda berikan.
   1. Pilih **Gunakan** untuk melengkapkan konfigurasi perhubungan.

   > [!NOTE]
   > Anda boleh mengkonfigurasi lebih banyak perhubungan antara entiti kenalan dan entiti akaun lain dengan entiti pertengahan.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisasi pelbagai perhubungan menyambungkan entiti kenalan kepada entiti akaun.":::

1. Pilih **Seterusnya**.

1. Dalam langkah **Tetapkan jenis semantik**, pilih **Jenis semantik**. Pada masa ini, terdapat satu **Jenis semantik** yang dipanggil *ContactProfile*.

1. Petakan id kenalan anda ke *ID kenalan* jenis **semantik ContactProfile**. Secara pilihan, petakan medan lain seperti nama pertama, nama akhir, jantina atau e-mel.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Petakan atribut data kenalan anda kepada medan yang disediakan dan medan pilihan.":::

1. Pilih **Seterusnya**.

1. **Dalam langkah Semak Semula**, semak konfigurasi pemetaan semantik. Untuk membuat perubahan, pilih **Edit** untuk seksyen yang sepadan.

1. Pilih **Simpan**.

1. Untuk memproses pemetaan semantik, pilih **Jalankan**. Atau pilih **Tutup** untuk menyimpan pemetaan semantik anda tanpa memprosesnya. Untuk menjalankannya kemudian, pilih pemetaan semantik dan pilih **Segar Semula**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Urus pemetaan semantik sedia ada

Pergi ke **pemetaan Semantik Data** > **(pratonton)** untuk melihat pemetaan semantik anda yang disimpan, entiti sumbernya, jenis semantik, jenis pemetaan dan status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Pilihan untuk menguruskan pemetaan semantik.":::

Pilih pemetaan semantik untuk melihat tindakan yang tersedia.
- **Edit** konfigurasi semasa. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.
- **Segar semula** pemetaan semantik untuk memasukkan data terkini. Menyegar semula sebarang pemetaan semantik yang diberikan semantik akan menyegarkan semula semua pemetaan semantik jenis yang sama.
- **Namakan semula** pemetaan semantik. Pilih **Simpan**.
- **Padamkan** pemetaan semantik. Untuk memadam lebih daripada satu pemetaan semantik sekaligus, pilih pemetaan semantik dan ikon padam. Pilih **Padam** untuk mengesahkan pemadaman.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Gunakan pemetaan entiti semantik ContactProfile untuk mencipta aktiviti peringkat hubungan

Selepas membuat *pemetaan entiti semantik ContactProfile*, anda boleh menangkap aktiviti kenalan. Ini membolehkan anda melihat dalam garis masa aktiviti untuk akaun yang kenalan bertanggungjawab untuk setiap aktiviti. Kebanyakan langkah mengikut konfigurasi pemetaan aktiviti biasa.

   > [!NOTE]
   > Untuk aktiviti peringkat hubungan berfungsi, anda mesti mempunyai kedua-dua **atribut AccountID** dan **ContactID** untuk setiap rekod dalam data aktiviti anda.

1. [*Tentukan pemetaan* entiti semantik ContactProfile](#define-a-contactprofile-semantic-entity-mapping) dan jalankan pemetaan semantik.

1. Pergi ke **Aktiviti Data** > **·**.

1. Pilih **Tambah Aktiviti** untuk mencipta aktiviti baharu.

1. Namakan aktiviti, pilih entiti aktiviti sumber dan pilih kunci utama entiti aktiviti.

1. **Dalam langkah Perhubungan**, cipta hubungan tidak langsung antara data sumber aktiviti anda kepada akaun, menggunakan data kenalan anda sebagai entiti perantara. Untuk maklumat lanjut, lihat [laluan](relationships.md#relationship-paths) perhubungan langsung dan tidak langsung.
   - Contoh perhubungan untuk aktiviti yang dipanggil *Pembelian*:
      - **Pembelian Data** > **Hubungan Data** Aktiviti Sumber pada atribut **ContactID**
      - **Data** > **Akaun Kenalan** pada Atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Contoh persediaan perhubungan.":::

1. Selepas menyediakan perhubungan, pilih **Seterusnya** dan lengkapkan konfigurasi pemetaan aktiviti anda. Untuk langkah terperinci tentang penciptaan aktiviti, lihat [mentakrifkan aktiviti](activities.md).

1. Jalankan pemetaan aktiviti anda.

1. Selepas pemetaan aktiviti peringkat kenalan berjalan, pilih **Pelanggan**. Aktiviti peringkat hubungan dipaparkan pada garis masa pelanggan anda.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Keputusan akhir selepas mengkonfigurasi aktiviti hubungan":::

### <a name="contact-level-activity-timeline-filtering"></a>Penapisan garis masa aktiviti peringkat hubungan

Garis masa aktiviti untuk pelanggan anda termasuk ID atau nama mereka, bergantung pada konfigurasi ContactProfile *anda*, untuk aktiviti yang mereka lakukan. Tapis aktiviti mengikut kenalan dalam garis masa untuk melihat kenalan tertentu yang anda minati. Untuk melihat semua aktiviti yang tidak diperuntukkan kepada kenalan tertentu, pilih **Aktiviti yang tidak dipetakan kepada Kenalan**.

:::image type="content" source="media/Contact_Activities3.png" alt-text="Opsyen penapisan tersedia untuk aktiviti peringkat kenalan.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
