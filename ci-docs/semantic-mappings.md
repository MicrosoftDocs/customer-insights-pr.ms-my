---
title: Pemetaan semantik (Pratonton)
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
ms.openlocfilehash: a60855f6d5616ca9b958752836d1071ae3433db0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643534"
---
# <a name="semantic-mappings-preview"></a>Pemetaan semantik (Pratonton)

Semantik pemetaan membolehkan anda memetakan data bukan aktiviti anda kepada skema yang dipratentukan. Skema ini membantu Wawasan Pelanggan untuk memahami atribut data anda dengan lebih baik. Pemetaan semantik dan data yang disediakan membolehkan cerapan dan ciri baharu dalam Wawasan Pelanggan. Untuk memetakan data aktiviti anda kepada pengguna skema, semak dokumentasi [aktiviti](activities.md).

**Pemetaan semantik pada masa ini didayakan untuk persekitaran berdasarkan akaun perniagaan**. *ContactProfile* adalah satu-satunya jenis pemetaan semantik yang tersedia pada masa ini dalam Wawasan Pelanggan.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Takrifkan pemetaan entiti semantik ContactProfile

1. Pergi ke **pemetaan DataSemantik** > **(pratonton)**.

1. Pilih **Tambah pemetaan semantik** untuk memulakan pengalaman dipandu.

1. Dalam langkah **Data entiti**, tetapkan nilai untuk medan berikut:

   - **Nama pemetaan entiti semantik** : Berikan nama untuk pemetaan entiti semantik anda.
   - **Entiti sumber** : Pilih entiti yang termasuk data kenalan.
   - **Kunci Utama**: Pilih medan yang mengenal pasti rekod kenalan secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Sediakan pemetaan entiti semantik dengan nama, entiti sumber dan kunci utama.":::

1. Pilih **Seterusnya** untuk teruskan.

1. Dalam langkah **Perhubungan**, konfigurasikan butiran untuk menyambungkan data kenalan anda kepada data akaun yang sepadan. Langkah ini menggambarkan sambungan antara entiti.  

   Terdapat dua jenis laluan perhubungan yang boleh dilaksanakan: **Perhubungan langsung** dan **Perhubungan tidak langsung**. Untuk mendapatkan maklumat lanjut, pergi ke [laluan perhubungan langsung dan tidak langsung](relationships.md#relationship-paths).

   1. Pilih **Tambah Perhubungan** konfigurasi perhubungan.
   1. Pilih atribut daripada entiti sumber anda yang menyambungkan entiti kenalan anda ke entiti lain.
   1. Pilih entiti untuk menyambungkan entiti kenalan anda kepada. Anda boleh memilih entiti daripada **Entiti akaun** atau bahagian **Entiti pertengahan**. Jika anda memilih entiti pertengahan, anda perlu mentakrifkan perhubungan kedua untuk menyambung kepada entiti akaun sasaran anda.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pilih sama ada entiti Akaun atau entiti pertengahan.":::

   1. Berikan **Nama perhubungan**. Jika perhubungan antara entiti anda sudah wujud, nama perhubungan ialah baca sahaja. Jika tiada perhubungan wujud, perhubungan baharu akan dicipta dengan nama yang anda berikan.
   1. Pilih **Gunakan** untuk melengkapkan konfigurasi perhubungan.

   > [!NOTE]
   > Anda boleh mengkonfigurasi lebih banyak perhubungan antara entiti kenalan dan entiti akaun lain dengan entiti pertengahan.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisasi pelbagai perhubungan menyambungkan entiti kenalan kepada entiti akaun.":::

1. Pilih **Seterusnya** apabila anda selesai dengan konfigurasi perhubungan.

1. Dalam langkah **Tetapkan jenis semantik**, pilih **Jenis semantik**. Pada masa ini, terdapat satu **Jenis semantik** yang dipanggil *ContactProfile*.

1. Petakan data anda kepada *ContactProfile* **Jenis semantik** untuk medan yang ditunjukkan.
   - Medan diperlukan: ID kenalan
   - Medan pilihan: Nama pertama, Nama akhir, tarikh lahir, jantina, E-mel utama dan Telefon utama

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Petakan atribut data kenalan anda kepada medan yang disediakan dan medan pilihan.":::

1. Pilih **Seterusnya** untuk teruskan.

1. Dalam langkah **Semakan**, sila lihat pada konfigurasi pemetaan semantik. Pilih **Edit** untuk bahagian yang sepadan untuk membuat perubahan.

1. Pilih **Simpan** untuk menyimpan **pemetaan semantik** baharu anda.

1. Selepas menyimpan, anda boleh memilih proses **Jalankan** pemetaan semantik atau anda boleh memilih **Dekat** untuk menyimpan pemetaan semantik anda tanpa pemprosesan.

1. Untuk menjalankan pemetaan semantik pada titik kemudian, pilih pemetaan semantik dan pilih **Segar semula**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Urus pemetaan semantik sedia ada

Pada **Data** > **Pemetaan semantik (pratonton)**, anda boleh melihat semua pemetaan anda yang disimpan dan menguruskannya. Setiap pemetaan semantik diwakili oleh baris yang berasingan. Anda akan mencari butiran tentang entiti sumber, jenis semantik, jenis pemetaan dan statusnya.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Pilihan untuk menguruskan pemetaan semantik.":::

- **Edit**: Buka konfigurasi persediaan pemetaan semantik dalam langkah semakan. Anda boleh mengubah konfigurasi semasa. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

- **Segar semula** : Menyegar semula pemetaan semantik terpilih dengan data yang terkini daripada entiti yang merupakan sebahagian daripada konfigurasi. Menyegar semula sebarang pemetaan semantik yang diberikan semantik akan menyegarkan semula semua pemetaan semantik jenis yang sama.

- **Namakan semula** : Buka dialog yang mana anda boleh memasukkan nama yang berbeza untuk pemetaan semantik yang dipilih. Pilih **Simpan** untuk menggunakan perubahan anda.

- **Padam** : Buka dialog untuk mengesahkan pemadaman pemetaan semantik yang dipilih. Anda juga boleh memadam lebih daripada satu pemetaan semantik sekaligus dengan memilih pemetaan semantik dan ikon padam. Pilih **Padam** untuk mengesahkan pemadaman.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Gunakan pemetaan entiti semantik ContactProfile untuk mencipta aktiviti peringkat hubungan

Selepas membuat *pemetaan entiti semantik ContactProfile*, anda boleh menangkap aktiviti kenalan. Ini membolehkan anda melihat dalam garis masa aktiviti untuk akaun yang kenalan bertanggungjawab untuk setiap aktiviti. Kebanyakan langkah mengikut konfigurasi pemetaan aktiviti biasa.

   > [!NOTE]
   > Untuk aktiviti peringkat hubungan berfungsi, anda mesti mempunyai kedua-dua **atribut AccountID** dan **ContactID** untuk setiap rekod dalam data aktiviti anda.

1. [*Tentukan pemetaan entiti semantik ContactProfile*.](#define-a-contactprofile-semantic-entity-mapping) Dan jalankan pemetaan semantik.

1. Pergi ke **DataActivities** > **·**.

1. Pilih **Tambah Aktiviti** untuk mencipta aktiviti baharu.

1. Namakan aktiviti, pilih entiti aktiviti sumber dan pilih kunci utama entiti aktiviti.

1. **Dalam langkah Perhubungan**, cipta hubungan tidak langsung antara data sumber aktiviti anda kepada akaun, menggunakan data kenalan anda sebagai entiti perantara. Untuk maklumat lanjut, lihat [laluan](relationships.md#relationship-paths) perhubungan langsung dan tidak langsung.
   - Contoh perhubungan untuk aktiviti yang dipanggil *Pembelian*:
      - **Pembelian Data** > **Aktiviti SumberContact Data** pada atribut **ContactID**
      - **Hubungi Data Akaun Data** > **pada** Atribut **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Contoh persediaan perhubungan.":::

1. Selepas menyediakan perhubungan, pilih **Seterusnya** dan lengkapkan konfigurasi pemetaan aktiviti anda. Untuk langkah terperinci tentang penciptaan aktiviti, lihat [mentakrifkan aktiviti](activities.md).

1. Jalankan pemetaan aktiviti anda.

1. Aktiviti peringkat hubungan anda kini akan kelihatan pada garis masa pelanggan anda.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Keputusan akhir selepas mengkonfigurasi aktiviti hubungan":::

### <a name="contact-level-activity-timeline-filtering"></a>Penapisan garis masa aktiviti peringkat hubungan

Selepas mengkonfigurasi pemetaan aktiviti peringkat kenalan dan menjalankannya, garis masa aktiviti untuk pelanggan anda akan dikemas kini. Ia termasuk ID atau nama mereka, bergantung pada konfigurasi ContactProfile *anda*, untuk aktiviti yang mereka lakukan. Anda boleh menapis aktiviti mengikut kenalan dalam garis masa untuk melihat kenalan tertentu yang anda minati. Selain itu, anda boleh melihat semua aktiviti yang tidak diberikan kepada kenalan tertentu dengan memilih Aktiviti yang **tidak dipetakan kepada Kenalan**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opsyen penapisan tersedia untuk aktiviti peringkat kenalan.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
