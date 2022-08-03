---
title: Buat segmen kompleks dengan pembina segmen
description: Gunakan pembina segmen untuk mencipta segmen pelanggan yang kompleks dengan mengumpulkannya berdasarkan pelbagai atribut.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170646"
---
# <a name="create-complex-segments-with-segment-builder"></a>Buat segmen kompleks dengan pembina segmen

Takrifkan penapis kompleks sekitar entiti pelanggan disatukan dan entiti yang berkaitan. Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya.

> [!TIP]
> Segmen berdasarkan **pelanggan individu** secara automatik menyertakan maklumat kenalan untuk ahli segmen. Dalam persekitaran untuk segmen **akaun perniagaan**, segmen adalah berdasarkan akaun (syarikat atau subsidiari). Untuk memasukkan maklumat kenalan dalam segmen, gunakan kefungsian **Atribut projek** dalam pembina segmen. Pastikan sumber data kenalan adalah [dipetakan secara semantiknya ke ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) entiti.

## <a name="segment-builder"></a>Pembina segmen

Imej berikut menunjukkan pelbagai aspek pembina segmen. Imej menunjukkan segmen yang menghasilkan sekumpulan pelanggan. Pelanggan yang memesan barangan dalam tempoh masa tertentu dan mata ganjaran yang dikumpul atau membelanjakan sejumlah wang tertentu.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemen dalam pembina segmen." lightbox="media/segment-builder-overview.png":::

1. Menyusun segmen anda dengan peraturan dan subperaturan. Setiap peraturan atau subperaturan terdiri daripada syarat. Gabungkan syarat dengan pengendali logik.

1. Pilih [laluan perhubungan](relationships.md) antara entiti yang digunakan pada peraturan. Laluan perhubungan menentukan atribut yang boleh digunakan dalam syarat.

1. Uruskan peraturan dan subperaturan. Tukar kedudukan peraturan atau padamkan.

1. Tambah syarat dan bina peringkat penyarangan yang sesuai menggunakan subperaturan.

1. Gunakan operasi tetapan untuk peraturan yang disambungkan.

1. Gunakan anak tetingkap atribut untuk menambah atribut entiti tersedia atau cipta syarat berdasarkan atribut. Anak tetingkap menunjukkan senarai entiti dan atribut, berdasarkan laluan perhubungan yang dipilih, yang tersedia untuk peraturan yang dipilih.

1. Tambah syarat berdasarkan atribut kepada peraturan sedia ada dan subperaturan atau menambahkannya ke peraturan baharu.

1. Buat asal dan buat semula perubahan semasa membina segmen.

Contoh di atas menunjukkan keupayaan pembahagian. Kami telah menentukan segmen untuk pelanggan yang membeli sekurang-kurangnya barangan bernilai $500 dalam talian *dan* berminat dalam pembangunan perisian.

## <a name="create-a-new-segment-with-segment-builder"></a>Buat segmen baru dengan pembina segmen

1. Pergi ke **Segmen**.

1. Pilih **Baharu** > **Bina sendiri**. Pada halaman pembina segmen, anda takrifkan atau karang peraturan. Peraturan terdiri daripada satu atau lebih keadaan yang mentakrifkan set pelanggan.

1. Pilih **Edit butiran** di sebelah segmen Tidak Bertajuk. Berikan nama untuk segmen anda dan kemas kini **Nama entiti output** yang dicadangkan untuk segmen tersebut. Secara pilihan, tambah perihalan dan [tag](work-with-tags-columns.md#manage-tags) pada segmen.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Kotak dialog Edit butiran butiran.":::

1. Dalam seksyen **Rule1**, pilih atribut entiti yang anda ingin tapis pelanggan. Terdapat dua cara untuk memilih mencari:
   - Semak senarai entiti dan atribut yang tersedia dalam anak tetingkap **Tambahkan pada Peraturan** dan pilih ikon **+** bersebelahan dengan atribut untuk ditambahkan. Pilih sama ada anda ingin menambahkan atribut pada peraturan sedia ada atau menggunakannya untuk mencipta peraturan baharu.
   - Taipkan nama atribut dalam bahagian peraturan untuk melihat cadangan sepadan.

1. Pilih operator untuk menentukan nilai yang sepadan dengan syarat. Atribut boleh mempunyai salah satu daripada empat jenis data sebagai nilai: berangka, rentetan, tarikh atau Boolean. Bergantung pada jenis data atribut, operator yang berbeza tersedia untuk menentukan syarat. Untuk segmen dengan akaun perniagaan, dua operator khas tersedia untuk memasukkan hierarki yang berpotensi antara akaun yang diinjes. Gunakan operator *anak kepada* dan *induk kepada* untuk memasukkan akaun yang berkaitan.

1. Pilih **Tambah syarat** untuk menambahkan lebih banyak syarat pada peraturan. Untuk mencipta peraturan di bawah peraturan semasa, pilih **Tambah subperaturan**.

1. Jika peraturan menggunakan entiti lain daripada *entiti Pelanggan*, pilih **Tetapkan laluan** perhubungan untuk memetakan entiti yang dipilih kepada entiti pelanggan yang disatukan. Jika hanya terdapat satu laluan perhubungan yang mungkin, sistem memilihnya secara automatik. Laluan [hubungan yang berbeza](relationships.md#relationship-paths) boleh menghasilkan hasil yang berbeza. Setiap peraturan boleh mempunyai laluan perhubungannya sendiri.

   :::image type="content" source="media/relationship-path.png" alt-text="Kemungkinan laluan perhubungan apabila mencipta peraturan berdasarkan entiti yang dipetakan pada entiti pelanggan disatukan.":::

1. Jika anda mempunyai berbilang syarat dalam peraturan, pilih operator logik yang menghubungkannya.  
   - **DAN** operator: Semua syarat mesti dipenuhi untuk memasukkan rekod dalam segmen. Gunakan opsyen ini apabila anda mentakrifkan keadaan merentas entiti yang berbeza.
   - **ATAU** operator: Salah satu syarat mesti dipenuhi untuk memasukkan rekod dalam segmen. Gunakan opsyen ini apabila anda mentakrifkan berbilang syarat untuk entiti yang sama.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Peraturan dengan dua DAN syarat.":::

   Apabila menggunakan ATAU operator, semua syarat mestilah berdasarkan entiti yang dimasukkan dalam laluan perhubungan.

1. Untuk mencipta set rekod pelanggan yang berbeza, buat berbilang peraturan. Untuk memasukkan pelanggan yang diperlukan untuk kes perniagaan anda, gabungkan kumpulan. Secara khusus, jika anda tidak dapat memasukkan entiti dalam peraturan kerana laluan perhubungan yang ditentukan, cipta peraturan baru untuk memilih atribut daripadanya.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Tambahkan peraturan baharu pada segmen dan pilih operator set.":::

   1. Pilih **Tambah peraturan**.
   1. Pilih salah satu operator set: **Kesatuan**, **Bersilang** atau **Kecuali**.

      - **Kesatuan** menyatukan dua kumpulan.
      - **Bersilang** dua kumpulan bertindih. Hanya data yang *lazim* kepada kedua-dua kumpulan kekal dalam kumpulan yang disatukan.
      - **Kecuali** menggabungkan dua kumpulan. Hanya data dalam Kumpulan A yang *tidak lazim* dengan data dalam kumpulan B disimpan.

1. Secara lalai, entiti output secara automatik akan mengandungi semua atribut profil pelanggan yang sepadan dengan penapis yang ditentukan. Jika segmen adalah berdasarkan entiti lain daripada *entiti Pelanggan*, pilih **atribut** Projek untuk menambah lebih banyak atribut daripada entiti ini pada entiti output.

   > [!IMPORTANT]
   > Untuk segmen berdasarkan akaun perniagaan, butiran satu atau lebih kenalan setiap akaun daripada *entiti ContactProfile* mesti disertakan dalam segmen untuk membolehkan segmen tersebut diaktifkan atau dieksport ke destinasi yang memerlukan maklumat hubungan. Untuk mendapatkan maklumat lanjut tentang entiti *ContactProfile*, lihat [Pemetaan semantik](semantic-mappings.md).
   > Output sampel untuk segmen berdasarkan akaun perniagaan dengan atribut diunjurkan kenalan boleh kelihatan seperti ini:
   >
   > |ID  |Nama akaun  |Hasil  |Nama orang hubungan  | Peranan kenalan|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [Pengurus Pemerolehan,CEO]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Contoh atribut unjuran yang dipilih dalam anak tetingkap untuk ditambahkan pada entiti output.":::
  
   Sebagai contoh: Segmen adalah berdasarkan entiti yang mengandungi data pembelian yang berkaitan dengan entiti *Pelanggan*. Segmen tersebut mencari semua pelanggan dari Sepanyol yang membeli barangan pada tahun semasa. Anda boleh memilih untuk menambah atribut seperti harga barangan, atau tarikh pembelian kepada semua rekod pelanggan yang sepadan dalam entiti output. Maklumat ini mungkin berguna untuk menganalisis korelasi bermusim dengan jumlah perbelanjaan.

   > [!NOTE]
   > - **Atribut projek** hanya berfungsi untuk entiti yang mempunyai perhubungan satu dengan banyak dengan entiti pelanggan. Contohnya, seorang pelanggan boleh mempunyai berbilang langganan.
   > - Jika atribut yang anda mahu projek lebih daripada satu hop daripada entiti *Pelanggan*, seperti yang ditakrifkan oleh perhubungan, atribut tersebut sepatutnya digunakan dalam setiap peraturan bagi pertanyaan segmen yang anda sedang bangunkan.
   > - Jika atribut yang anda mahu projek hanya lebih daripada satu hop daripada entiti *Pelanggan*, atribut tersebut tidak perlu wujud dalam setiap peraturan bagi pertanyaan segmen yang anda sedang bangunkan.
   > - **Atribut yang diunjurkan** difaktorkan apabila menggunakan operator set.

1. Pilih **Jalankan** untuk mencipta segmen. Pilih **Simpan** jika anda mahu mengekalkan konfigurasi semasa dan jalankan segmen kemudian. Halaman **Segmen** dipaparkan.

### <a name="segment-builder-tips"></a>Petua pembina segmen

Apabila mencipta segmen menggunakan pembina segmen, perlu diingat petua berikut:

- Pembina segmen tidak akan mencadangkan nilai sah daripada entiti apabila menetapkan operator untuk syarat. Anda boleh pergi ke **Data** > **Entiti** dan memuat turun data entiti untuk melihat nilai yang tersedia.
- Syarat berdasarkan tarikh membolehkan anda bertukar antara tarikh tetap dan julat tarikh terapung.
- Jika anda mempunyai berbilang peraturan untuk segmen anda, peraturan yang anda edit mempunyai baris biru menegak di sebelahnya.
- Anda boleh memindahkan peraturan dan syarat ke tempat lain dalam definisi segmen. Pilih elipsis menegak (&vellip;) di sebelah peraturan atau syarat dan pilih bagaimana dan di mana untuk memindahkannya.
- Kawalan **Buat asal** dan **Buat Semula** dalam bar perintah membenarkan anda menggulung balik perubahan.
- Selepas mencipta segmen, sesetengah segmen membolehkan [anda menjejaki penggunaan segmen](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Langkah-langkah berikutnya

[Eksport segmen](export-destinations.md) dan terokai [penyepaduan Kad Pelanggan](customer-card-add-in.md) untuk menggunakan segmen dalam aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
