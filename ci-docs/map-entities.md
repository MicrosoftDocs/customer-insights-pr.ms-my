---
title: Pilih medan sumber untuk penyatuan data
description: Langkah pertama dalam proses penyatuan ialah memilih entiti, atribut, kekunci utama dan jenis semantik untuk memetakan data ke profil pelanggan bersatu.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139793"
---
# <a name="select-source-fields-for-data-unification"></a>Pilih medan sumber untuk penyatuan data

Langkah pertama dalam penyatuan ialah memilih entiti dan medan dalam set data anda yang anda ingin gabungkan. Pilih entiti yang mengandungi butiran berkaitan pelanggan seperti nama, alamat, nombor telefon dan e-mel. Anda boleh memilih satu atau lebih entiti.

## <a name="select-entities-and-fields"></a>Pilih entiti dan medan

1. Pergi ke **Data** > **Unify**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Petikan skrin halaman pendaratan menyatukan untuk pengalaman larian pertama dengan Mari bermula diserlahkan.":::

1. Pilih **Mulakan**.

1. **Pada halaman Medan** sumber, pilih **Pilih entiti dan medan**. Anak **tetingkap Pilih entiti dan medan** dipaparkan.

1. Pilih sekurang-kurangnya satu entiti.

1. Untuk setiap entiti yang dipilih, kenal pasti medan yang anda ingin gunakan untuk memadankan rekod pelanggan dan medan untuk disertakan dalam profil bersatu. Medan ini dipanggil *Atribut*. Anda boleh memilih atribut yang diperlukan secara individu daripada entiti atau menyertakan semua atribut daripada entiti dengan memilih kotak semak pada tahap entiti. Anda boleh mencari pada kata kunci merentasi semua atribut dan entiti untuk memilih atribut yang diperlukan yang anda mahu petakan.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Petikan skrin entiti dan atribut terpilih.":::

   Dalam contoh ini, kami menambah **entiti Kenalan** dan **Kesetiaan Pelanggan**. Dengan memilih entiti ini, anda boleh memperoleh wawasan yang pelanggan perniagaan online ialah ahli program kesetiaan.

1. Pilih **Gunakan** untuk mengesahkan pilihan anda. Paparan entiti dan atribut yang dipilih.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pilih kekunci utama dan jenis semantik untuk atribut

   :::image type="content" source="media/m3_select_primary.png" alt-text="Petikan skrin entiti terpilih dengan kekunci utama tidak dipilih." lightbox="media/m3_select_primary.png":::

Untuk setiap entiti, lakukan langkah-langkah berikut.

1. Pilih kekunci **Utama**. Kunci utama ialah atribut yang unik kepada entiti. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut jenis data rentetan, integer dan GUID disokong sebagai kekunci utama.

1. Untuk menggunakan model AI untuk ramalan semantik pintar, menjimatkan masa dan meningkatkan ketepatan, memastikan **Pemetaan** pintar dihidupkan. Pemetaan pintar menyerlahkan pengesyoran semantik berasaskan AI dalam medan **Jenis**. Anda boleh mengatasi pemilihan yang dicadangkan dengan memilih mana-mana jenis semantik dari senarai pilihan yang ada.

1. Untuk setiap atribut, pilih Jenis **semantik** yang paling sesuai untuk menerangkan atribut tersebut, seperti nama, bandar atau alamat e-mel.

   > [!NOTE]
   > Satu medan harus memetakan ke jenis *semantik Person.FullName* untuk mengisi nama pelanggan dalam kad pelanggan. Jika tidak, kad pelanggan akan muncul tanpa nama.

   1. Untuk mengubah jenis atribut yang dikenal pasti oleh sistem, pilih jenis lain. Jika jenis tidak wujud, cipta jenis semantik tersuai dengan **memilih medan Jenis** untuk atribut dan masukkan nama jenis semantik tersuai anda.

   1. Untuk menambah atribut yang mengandungi URL pada imej profil atau logo yang tersedia secara umum, pilih entiti dan medan yang mengandungi URL. Dalam medan **Jenis**, masukkan yang berikut:
      - Untuk seseorang: ImejProfil.Seseorang
      - Untuk organisasi: ImejLogo.Organisasi

   1. Untuk atribut nama akaun, masukkan "Organization.Name" dalam **medan Jenis**.

1. Semak atribut di mana jenis semantik dikenal pasti secara automatik. Atribut ini disenaraikan di bawah **Semak semula medan** yang dipetakan. Hanya atribut dengan jenis yang sama boleh digabungkan dalam **langkah Medan** pelanggan Disatukan. Jenis semantik digunakan untuk mencadangkan cerapan secara automatik. Pastikan jenis yang anda pilih adalah konsisten merentasi semua entiti yang dipilih.

1. Untuk atribut yang tidak dipetakan secara automatik kepada jenis semantik, pilih medan jenis semantik, masukkan nama jenis atribut tersuai anda atau biarkan ia dinyahpetakan. Atribut ini disenaraikan di bawah **Takrifkan data dalam medan** yang tidak dipetakan.

1. Selepas melengkapkan langkah untuk setiap entiti, pilih **Simpan medan** sumber.

1. Pilih **Seterusnya**.

> [!div class="nextstepaction"]
> [Langkah seterusnya: Alih keluar pendua](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
