---
title: Pemetaan semantik (pratonton)
description: Gambaran keseluruhan pemetaan semantik dan cara untuk menggunakannya.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: 8780c11c8b091717349f0fd75a36b99c3a63ab49
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303887"
---
# <a name="semantic-mappings-preview"></a>Pemetaan semantik (pratonton)

> [!NOTE]
> Halaman **Pemetaan** Semantik hanya tersedia untuk persekitaran perniagaan (B-to-B) di mana profil kenalan telah dibuat menggunakan halaman ini. Anda boleh terus membuat dan menguruskan profil kenalan individu menggunakan **halaman Pemetaan** Semantik. Atau, [menyatukan data](data-unification-contacts.md) kenalan anda untuk mengalih keluar pendua, mengenal pasti padanan merentas entiti dan mencipta satu profil hubungan bersatu. Anda kemudian boleh menggunakan profil kenalan disatukan untuk mencipta aktiviti peringkat kenalan.

Semantik pemetaan membolehkan anda memetakan data bukan aktiviti anda kepada skema yang dipratentukan. Skema ini membantu Wawasan Pelanggan untuk lebih memahami atribut data anda. Pemetaan semantik dan data yang disediakan membolehkan pandangan dan ciri baru dalam Wawasan Pelanggan. Untuk memetakan data aktiviti anda kepada pengguna skema, semak dokumentasi [aktiviti](activities.md).

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Takrifkan pemetaan entiti semantik ContactProfile

1. Pergi ke **Pemetaan Semantik Data** > **(pratonton)**.

1. Pilih **Tambah pemetaan semantik** untuk memulakan pengalaman dipandu.

1. Dalam langkah **Data entiti**, tetapkan nilai untuk medan berikut:

   - **Nama** pemetaan entiti semantik: Nama untuk pemetaan entiti semantik anda.
   - **Entiti** Sumber: Entiti yang termasuk data kenalan.
   - **Kekunci primer**: Medan yang mengenal pasti rekod kenalan secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Sediakan pemetaan entiti semantik dengan nama, entiti sumber dan kunci utama.":::

1. Pilih **Seterusnya**.

1. Dalam langkah **Perhubungan**, konfigurasikan butiran untuk menyambungkan data kenalan anda kepada data akaun yang sepadan. Langkah ini menggambarkan sambungan antara entiti.  

   Terdapat dua jenis laluan perhubungan yang boleh dilaksanakan: **Perhubungan langsung** dan **Perhubungan tidak langsung**. Untuk mendapatkan maklumat lanjut, pergi ke [laluan perhubungan langsung dan tidak langsung](relationships.md#relationship-paths).

   1. Pilih **Tambah Perhubungan** untuk mengkonfigurasikan perhubungan.
   1. Pilih atribut daripada entiti sumber anda yang menyambungkan entiti kenalan anda ke entiti lain.
   1. Pilih entiti untuk menyambungkan entiti kenalan anda kepada. Pilih entiti daripada **entiti** Akaun atau bahagian **Entiti** Perantaraan. Jika anda memilih entiti perantaraan, tentukan hubungan kedua untuk disambungkan ke entiti akaun sasaran anda.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Pilih sama ada entiti Akaun atau entiti pertengahan.":::

   1. Berikan **Nama perhubungan**. Jika perhubungan antara entiti anda sudah wujud, nama perhubungan ialah baca sahaja. Jika tiada perhubungan wujud, perhubungan baharu akan dicipta dengan nama yang anda berikan.
   1. Pilih **Gunakan** untuk melengkapkan konfigurasi perhubungan.

   > [!NOTE]
   > Anda boleh mengkonfigurasi lebih banyak perhubungan antara entiti kenalan dan entiti akaun lain dengan entiti pertengahan.
   
     :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="Visualisasi pelbagai perhubungan menyambungkan entiti kenalan kepada entiti akaun.":::

1. Pilih **Seterusnya**.

1. Dalam langkah **Tetapkan jenis semantik**, pilih **Jenis semantik**. Pada masa ini, terdapat satu **Jenis semantik** yang dipanggil *ContactProfile*.

1. Petakan *id kenalan anda kepada ID* Kenalan jenis **semantik ContactProfile**. Secara pilihan, petakan medan lain seperti nama pertama, nama akhir, jantina atau e-mel.

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Petakan atribut data kenalan anda kepada medan yang disediakan dan medan pilihan.":::

1. Pilih **Seterusnya**.

1. **Dalam langkah Semakan**, semak semula konfigurasi pemetaan semantik. Untuk membuat perubahan, pilih **Edit** untuk seksyen yang sepadan.

1. Pilih **Simpan**.

1. Untuk memproses pemetaan semantik, pilih **Jalankan**. Atau pilih **Tutup** untuk menyimpan pemetaan semantik anda tanpa memprosesnya. Untuk menjalankannya kemudian, pilih pemetaan semantik dan pilih **Segar Semula**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Urus pemetaan semantik sedia ada

Pergi ke **Pemetaan Semantik Data** > **(pratonton)** untuk melihat pemetaan semantik anda yang disimpan, entiti sumbernya, jenis semantik, jenis pemetaan dan status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Pilihan untuk menguruskan pemetaan semantik.":::

Pilih pemetaan semantik untuk melihat tindakan yang ada.
- **Edit** konfigurasi semasa. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.
- **Menyegar semula** pemetaan semantik untuk memasukkan data terkini. Menyegar semula sebarang pemetaan semantik yang diberikan semantik akan menyegarkan semula semua pemetaan semantik jenis yang sama.
- **Namakan semula** pemetaan semantik. Pilih **Simpan**.
- **Padamkan** pemetaan semantik. Untuk memadam lebih daripada satu pemetaan semantik sekaligus, pilih pemetaan semantik dan ikon padam. Pilih **Padam** untuk mengesahkan pemadaman.

[!INCLUDE [footer-include](includes/footer-banner.md)]
