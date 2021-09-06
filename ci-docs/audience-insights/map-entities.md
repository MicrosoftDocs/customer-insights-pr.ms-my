---
title: Petakan entiti untuk penyatuan data
description: Petakan data untuk mencipta profil pelanggan disatukan.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 570683876b10cb83d8af14552ca9bea9d80613575005d49a9af37cc16b8e75c9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034417"
---
# <a name="map-entities-and-attributes"></a>Petakan entiti dan atribut

**Peta** ialah peringkat pertama dalam proses data penyatuan Insights khalayak. Pemetaan terdiri daripada tiga fasa:

- *Pemilihan entiti*: Kenal pasti entiti boleh gabung yang membawa kepada set data dengan maklumat yang lebih lengkap tentang pelanggan.
- *Pemilihan atribut*: Bagi setiap entiti, kenal pasti lajur yang anda mahu gabung dan selaraskan dalam peringkat *padan* dan *gabung*. Lajur ini dipanggil *Atribut*.
- *Kekunci utama dan pilihan jenis semantik*: Untuk setiap entiti, kenal pasti atribut yang anda mahu takrifkan sebagai kekunci utama untuk entiti tersebut dan untuk setiap atribut, kenal pasti jenis semantik yang terbaik menggambarkan atribut tersebut.

Untuk maklumat lanjut tentang aliran penyatuan data umum , lihat [Satukan](data-unification.md).

## <a name="select-the-first-entities"></a>Pilih entiti pertama

1. Dalam Insights khalayak, pergi ke **Data** > **Unify** > **Padan**.

2. Mulakan fasa pemetaan dengan memilih **Pilih entiti**.

3. Pilih entiti dan atribut yang anda mahu gunakan dalam fasa *padanan* dan *gabungan*. Anda boleh memilih atribut yang diperlukan secara individu daripada entiti atau memasukkan semua atribut daripada entiti dengan memilih kotak semak **Memasukkan semua medan** pada peringkat entiti. Kami mengesyorkan pemilihan sekurang-kurangnya dua entiti untuk mendapat manfaat daripada proses penyatuan data.

   > [!div class="mx-imgBorder"]
   > ![Tambah contoh entiti.](media/data-manager-configure-map-add-entities-example.png "Tambah contoh entiti")

   Dalam contoh ini, kami menambahkan entiti **eCommerceContacts** dan **loyCustomers**. Dengan memilih entiti ini, anda boleh memperoleh wawasan yang pelanggan perniagaan online ialah ahli program kesetiaan.
   
   Anda boleh mencari pada kata kunci merentasi semua atribut dan entiti untuk memilih atribut yang diperlukan yang anda mahu petakan.
   
     > [!div class="mx-imgBorder"]
   > ![Contoh medan carian.](media/data-manager-configure-map-search-fields-example.png "Contoh medan carian")

4. Pilih **Gunakan** untuk mengesahkan pilihan anda.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Pilih kekunci utama dan jenis semantik untuk atribut

Selepas memilih entiti anda, halaman **Peta** menyenaraikan entiti yang dipilih untuk ulasan anda. Takrifkan kekunci utama untuk entiti dan kenal pasti jenis semantik untuk atribut dalam entiti.

- **Kekunci utama**: Pilih satu atribut sebagai kekunci utama untuk setiap entiti anda. Untuk atribut menjadi kekunci utama yang sah, ia tidak boleh mengandungi nilai pendua, nilai yang hilang atau nilai tak sah. Atribut jenis data rentetan, integer dan GUID disokong sebagai kekunci utama dan akan dipaparkan dalam medan untuk anda pilih.

- **Jenis atribut semantik**: Kategori atribut anda, seperti alamat e-mel atau nama. Untuk menggunakan model AI untuk ramalan pintar semantik, jimatkan masa dan tingkatkan ketepatan, tetapkan **Pemetaan pintar** kepada **HIDUPKAN**. Pemetaan pintar menyerlahkan pengesyoran semantik berasaskan AI dalam medan **Jenis**. Jika anda menetapkan ia kepada **MATIKAN**, anda akan melihat pengesyoran pemetaan biasa kami. Anda boleh memilih sebarang jenis semantik daripada senarai pilihan tersedia dan mengatasi pilihan yang disyorkan.

> [!div class="mx-imgBorder"]
> ![Jenis atribut dan ramalan semantik.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Jenis atribut dan ramalan semantik")

Menambah jenis semantik entiti tersuai juga boleh dilakukan. Pilih jenis medan untuk atribut itu dan taip nama jenis semantik tersuai anda. Cara ini, anda juga boleh mengubah jenis atribut yang dikenal pasti oleh sistem.

Semua atribut yang jenis semantik dikenal pasti secara automatik dikumpulkan dalam bahagian **Ulasan medan yang dipetakan**. Mengulas atribut ini dan jenis semantik kerana ia akan digunakan untuk menggabungkan entiti anda dalam langkah gabungan data penyatuan.

Atribut yang tidak dipetakan secara automatik kepada jenis semantik dikumpulkan dalam bahagian **Takrifkan data dalam bahagian medan tidak dipetakan**. Pilih medan jenis semantik untuk atribut yang tidak dipetakan atau masukkan nama jenis atribut tersuai anda.

> [!div class="mx-imgBorder"]
> ![Kekunci utama dan jenis atribut.](media/data-manager-configure-map-add-attributes.png "Kekunci utama dan jenis atribut")

> [!NOTE]
> Satu medan perlu dipetakan kepada jenis semantik Person.FullName untuk mengisi nama pelanggan dalam kad pelanggan. Jika tidak, kad pelanggan akan muncul tanpa nama. 

## <a name="add-and-remove-attributes-and-entities"></a>Tambah dan alih keluar atribut dan entiti

1. Pada **Satukan** > **Peta**, pilih **Edit medan**.

2. Dalam anak tetingkap **Edit medan**, tambah atau alih keluar atribut dan entiti. Gunakan carian atau tatal untuk mencari dan memilih atribut dan entiti yang anda berminat. Anda tidak boleh mengalih keluar atribut atau entiti jika ia telah dipadankan.

   > [!div class="mx-imgBorder"]
   > ![Tambah atau alih keluar atribut.](media/configure-data-map-edit.png "Tambah atau alih keluar atribut")

3. Pilih **Guna**.

## <a name="add-images-to-profiles"></a>Tambah imej pada profil

Jika entiti mengandungi URL untuk imej atau logo profil yang tersedia secara umum, anda boleh menambahnya ke profil pelanggan disatukan.

Pilih entiti dan cari medan yang mengandungi URL ke imej profil. Dalam medan input **Jenis**, masukkan secara manual nilai berikut: 
- Untuk seseorang: ImejProfil.Seseorang
- Untuk organisasi: ImejLogo.Organisasi

Teruskan dengan langkah penyatuan dan pastikan atribut yang mengandungi URL imej juga ditambah dalam langkah [Gabungan](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Tetapkan atribut untuk organisasi

Untuk organisasi (Pratonton), jenis atribut hendaklah dipetakan kepada "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Kekunci utama dan atribut jenis B2B](media/configure-data-map-edit-b2b.png "Kekunci utama dan atribut jenis B2B")

## <a name="next-step"></a>Langkah seterusnya

Sebagai sebahagian daripada proses penyatuan data, pergi ke halaman **Padan** . Lawat [**Padan**](match-entities.md) untuk mengetahui tentang peringkat ini.

> [!TIP]
> Semak video berikut: [Bermula: Cipta Profile Pelanggan Disatukan](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]