---
title: Pilih medan sumber untuk penyatuan data
description: Langkah pertama dalam proses penyatuan ialah memilih entiti, atribut, kunci utama, dan jenis semantik untuk memetakan data ke profil pelanggan bersatu.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304576"
---
# <a name="select-source-fields-for-data-unification"></a>Pilih medan sumber untuk penyatuan data

Langkah pertama dalam penyatuan ialah memilih entiti dan medan dalam set data anda yang anda ingin bersatu. Pilih entiti yang mengandungi butiran berkaitan pelanggan seperti nama, alamat, nombor telefon dan e-mel. Anda boleh memilih satu atau lebih entiti.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Pilih entiti dan medan

1. Pergi ke **Data** > **Penyatuan**.

   Untuk pelanggan individu (B-to-C), **halaman pendaratan Penyatuan** dipaparkan menunjukkan **Bermula** pada langkah pertama, **medan Sumber**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Petikan skrin halaman pendaratan penyatuan untuk pengalaman larian pertama untuk pelanggan individu.":::

   Untuk akaun perniagaan (B-to-B), **halaman pendaratan Penyatuan** memaparkan **Penyatuan akaun** yang menunjukkan **Bermula** pada langkah pertama, **medan** Sumber. Langkah **Penyatuan kenalan (pratonton)** adalah pilihan dan sementara menunggu penyatuan akaun.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Petikan skrin halaman pendaratan penyatuan untuk pengalaman larian pertama untuk akaun perniagaan.":::

1. Pilih **Mulakan**.

1. Pada halaman **Medan sumber**, pilih **Pilih entiti dan medan**. Anak **tetingkap Pilih entiti dan medan** dipaparkan.

1. Pilih sekurang-kurangnya satu entiti.

1. Bagi setiap entiti terpilih, kenal pasti medan yang ingin anda gunakan untuk memadankan rekod pelanggan dan medan untuk disertakan dalam profil bersatu. Medan ini dipanggil *Atribut*. Anda boleh memilih atribut yang diperlukan secara individu daripada entiti atau memasukkan semua atribut daripada entiti dengan memilih kotak semak pada peringkat entiti. Anda boleh mencari pada kata kunci merentasi semua atribut dan entiti untuk memilih atribut yang diperlukan yang anda mahu petakan.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Tangkapan skrin entiti dan atribut terpilih.":::

   Dalam contoh ini, kami menambah **entiti eCommerceContacts** dan **loyCustomer**. Dengan memilih entiti ini, anda boleh memperoleh wawasan yang pelanggan perniagaan online ialah ahli program kesetiaan.

1. Pilih **Gunakan** untuk mengesahkan pilihan anda. Entiti dan atribut yang dipilih dipaparkan.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pilih kekunci utama dan jenis semantik untuk atribut

   :::image type="content" source="media/m3_select_primary.png" alt-text="Petikan skrin entiti terpilih dengan kunci primer belum dipilih." lightbox="media/m3_select_primary.png":::

Bagi setiap entiti, lakukan langkah-langkah berikut.

1. Pilih **kekunci** Utama. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut rentetan, integer dan jenis data GUID disokong sebagai kekunci primer.

1. Untuk menggunakan model AI untuk ramalan semantik pintar yang menjimatkan masa dan meningkatkan ketepatan, pastikan **Pemetaan** pintar dihidupkan. Pemetaan pintar menyediakan cadangan semantik berasaskan AI dalam **medan Jenis**.

1. Untuk setiap atribut, pilih Jenis **semantik** yang paling tepat menerangkan atribut tersebut, seperti nama, bandar atau alamat e-mel.

   > [!NOTE]
   > Dalam B-to-C, satu medan harus memetakan kepada jenis *semantik Person.FullName* untuk mengisi nama pelanggan dalam kad pelanggan. Dalam B-to-B, nama akaun harus dipetakan ke *Organization.Name*. Jika tidak, kad pelanggan akan muncul tanpa nama.

   1. Untuk mengubah jenis atribut yang dikenal pasti oleh sistem, pilih pilihan lain. Jika jenis tidak wujud, cipta jenis semantik tersuai dengan **memilih medan Jenis** untuk atribut dan masukkan nama jenis semantik tersuai anda.

   1. Untuk menambah atribut yang mengandungi URL pada imej atau logo profil yang tersedia secara umum, pilih entiti dan medan yang mengandungi URL. Dalam medan **Jenis**, masukkan yang berikut:
      - Untuk seseorang: ImejProfil.Seseorang
      - Untuk organisasi: ImejLogo.Organisasi

1. Semak atribut di mana jenis semantik dikenal pasti secara automatik. Atribut ini disenaraikan di bawah Semak medan **dipetakan**. Hanya atribut dengan jenis yang sama boleh digabungkan dalam **langkah menyatukan medan** pelanggan. Jenis semantik digunakan untuk mencadangkan pandangan secara automatik. Pastikan jenis yang anda pilih konsisten merentas semua entiti yang dipilih.

1. Untuk atribut yang tidak dipetakan secara automatik kepada jenis semantik, pilih medan jenis semantik, masukkan nama jenis atribut tersuai anda atau biarkan ia dibongkar. Atribut ini disenaraikan di bawah **Takrifkan data dalam medan** yang belum dipetakan.

1. Selepas melengkapkan langkah untuk setiap entiti, pilih **Simpan medan** sumber.

1. Pilih **Seterusnya**.

> [!div class="nextstepaction"]
> [Langkah seterusnya: Alih keluar pendua](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
