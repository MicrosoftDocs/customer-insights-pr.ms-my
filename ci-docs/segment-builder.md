---
title: Cipta segmen dengan halaman pembina segmen
description: Cipta bahagian pelanggan untuk mengumpul mereka berasaskan pelbagai atribut.
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
ms.openlocfilehash: c8e9e4976ade36c1c3c4f688a667b329bfde6e3e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643554"
---
# <a name="create-segments"></a>Cipta segmen

Takrifkan penapis kompleks sekitar entiti pelanggan disatukan dan entiti yang berkaitan. Setiap segmen, selepas pemprosesan, mencipta set rekod pelanggan yang boleh anda eksport dan ambil tindakan padanya. Segmen diuruskan pada halaman **Segmen**. Anda boleh [cipta segmen baharu](#create-a-new-segment) menggunakan pembina segmen atau [cipta segmen pantas](#quick-segments) daripada kawasan aplikasi lain.

> [!TIP]
> - Segmen pantas hanya disokong dalam persekitaran untuk **pelanggan individu**.
> - Segmen berdasarkan **pelanggan individu** secara automatik menyertakan maklumat kenalan untuk ahli segmen. Dalam persekitaran untuk segmen **akaun perniagaan**, segmen adalah berdasarkan akaun (syarikat atau subsidiari). Untuk memasukkan maklumat kenalan dalam segmen, gunakan kefungsian **Atribut projek** dalam pembina segmen. Pastikan sumber data kenalan adalah [dipetakan secara semantiknya ke ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping) entiti.

## <a name="segment-builder"></a>Pembina segmen

Imej berikut menunjukkan pelbagai aspek pembina segmen. Imej menunjukkan segmen yang menghasilkan sekumpulan pelanggan. Pelanggan yang memesan barangan dalam tempoh masa tertentu dan mata ganjaran yang dikumpul atau membelanjakan sejumlah wang tertentu.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elemen dalam pembina segmen." lightbox="media/segment-builder-overview.png":::

1. Menyusun segmen anda dengan peraturan dan subperaturan. Setiap peraturan atau subperaturan terdiri daripada syarat. Gabungkan syarat dengan operator logik

1. Pilih [laluan perhubungan](relationships.md) antara entiti yang digunakan pada peraturan. Laluan perhubungan menentukan atribut yang boleh digunakan dalam syarat.

1. Uruskan peraturan dan subperaturan. Tukar kedudukan peraturan atau padamkan.

1. Tambah syarat dan bina peringkat penyarangan yang sesuai menggunakan subperaturan.

1. Gunakan operasi tetapan untuk peraturan yang disambungkan.

1. Gunakan anak tetingkap atribut untuk menambah atribut entiti tersedia atau cipta syarat berdasarkan atribut. Anak tetingkap menunjukkan senarai entiti dan atribut, berdasarkan laluan perhubungan yang dipilih, yang tersedia untuk peraturan yang dipilih.

1. Tambah syarat berdasarkan atribut kepada peraturan sedia ada dan subperaturan atau menambahkannya ke peraturan baharu.

1. Buat asal dan buat semula perubahan semasa membina segmen.

Contoh di atas menunjukkan keupayaan pembahagian. Kami telah menentukan segmen untuk pelanggan yang membeli sekurang-kurangnya barangan bernilai $500 dalam talian *dan* berminat dalam pembangunan perisian.

## <a name="create-a-new-segment"></a>Cipta bahagian baharu

Terdapat berbilang cara untuk mencipta segmen baharu. Bahagian ini menerangkan cara membina segmen anda sendiri dari awal. Anda juga boleh mencipta *segmen pantas* berdasarkan pada entiti sedia ada atau menggunakan model pembelajaran mesin untuk mendapatkan *segmen yang dicadangkan*. Untuk mendapatkan maklumat lanjut, pergi ke [Gambaran keseluruhan segmen](segments.md).

Semasa mencipta segmen, anda boleh menyimpan draf. Dalam peringkat draf, segmen disimpan sebagai segmen tidak aktif. Apabila anda melengkapkan konfigurasi segmen, jalankan ia untuk mengaktifkan segmen. Anda juga boleh **Aktifkan** segmen dari halaman **Semua segmen**.

1. Pergi ke halaman **Bahagian**.

1. Pilih **Baharu** > **Bina sendiri**.

1. Pada halaman pembina segmen, anda takrifkan atau karang peraturan. Peraturan terdiri daripada satu atau lebih keadaan yang mentakrifkan set pelanggan.

1. Dalam seksyen **Rule1**, pilih atribut entiti yang anda ingin tapis pelanggan. Terdapat dua cara untuk memilih mencari:
   - Semak senarai entiti dan atribut yang tersedia dalam anak tetingkap **Tambahkan pada Peraturan** dan pilih ikon **+** bersebelahan dengan atribut untuk ditambahkan. Pilih sama ada anda ingin menambahkan atribut pada peraturan sedia ada atau menggunakannya untuk mencipta peraturan baharu.
   - Taipkan nama atribut dalam bahagian peraturan untuk melihat cadangan sepadan.

1. Pilih operator untuk menentukan nilai yang sepadan dengan syarat. Atribut boleh mempunyai salah satu daripada empat jenis data sebagai nilai: berangka, rentetan, tarikh atau Boolean. Bergantung pada jenis data atribut, operator yang berbeza tersedia untuk menentukan syarat. Untuk segmen dengan akaun perniagaan, dua operator khas tersedia untuk memasukkan hierarki yang berpotensi antara akaun yang diinjes. Gunakan operator *anak kepada* dan *induk kepada* untuk memasukkan akaun yang berkaitan.

1. Pilih **Tambah syarat** untuk menambahkan lebih banyak syarat pada peraturan. Untuk mencipta peraturan di bawah peraturan semasa, pilih **Tambah subperaturan**.

1. Jika peraturan menggunakan entiti lain daripada entiti *Pelanggan*, anda perlu menetapkan laluan perhubungan. Laluan perhubungan ini diperlukan untuk memberitahu sistem yang perhubungan anda mahu untuk mengakses entiti pelanggan disatukan. Pilih **Tetapkan laluan perhubungan** untuk memetakan entiti yang dipilih pada entiti pelanggan disatukan. Jika hanya terdapat satu kemungkinan laluan perhubungan, sistem akan memilihnya secara automatik. Laluan perhubungan yang berbeza boleh menghasilkan keputusan yang berbeza. Setiap peraturan boleh mempunyai laluan perhubungannya sendiri.

   :::image type="content" source="media/relationship-path.png" alt-text="Kemungkinan laluan perhubungan apabila mencipta peraturan berdasarkan entiti yang dipetakan pada entiti pelanggan disatukan.":::

   Contohnya, entiti *eCommerce_eCommercePurchases* dalam syot layar mempunyai empat pilihan untuk dipetakan pada entiti *Pelanggan* profil disatukan:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Pelanggan
   - eCommerce_eCommercePurchases > Pelanggan
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Pelanggan
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Pelanggan Apabila memilih pilihan terakhir, kita boleh sertakan atribut daripada semua entiti yang disenaraikan dalam syarat peraturan. Kami mungkin akan mendapat hasil yang lebih sedikit kerana rekod pelanggan yang sepadan perlu menjadi sebahagian daripada semua entiti. Dalam contoh ini, mereka perlu membeli barang melalui e-dagang(*eCommerce_eCommercePurchases*), di tempat jualan(*POS_posPurchases*) dan mengambil bahagian dalam program kesetiaan kami (*loyaltyScheme_loyCustomers*). Apabila memilih pilihan kedua, kami hanya boleh memilih atribut daripada entiti *eCommerce_eCommercePurchases* dan *Pelanggan*. Ini mungkin mengakibatkan lebih banyak profil pelanggan.

1. Jika terdapat berbilang syarat dalam peraturan, anda boleh memilih operator logik yang menghubungkannya.  
   - **DAN** operator: Semua syarat mesti dipenuhi untuk memasukkan rekod dalam segmen. Pilihan ini adalah paling berguna apabila anda menakrif syarat dalam entiti yang berbeza.
   - **ATAU** operator: Salah satu syarat mesti dipenuhi untuk memasukkan rekod dalam segmen. Pilihan ini paling berguna apabila anda menakrif berbilang syarat untuk entiti yang sama.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Peraturan dengan dua DAN syarat.":::

   Apabila menggunakan ATAU operator, semua syarat mestilah berdasarkan entiti yang dimasukkan dalam laluan perhubungan.

   - Anda boleh mencipta berbilang peraturan untuk mencipta set rekod pelanggan yang berbeza. Anda boleh menggabungkan kumpulan untuk memasukkan pelanggan yang diperlukan bagi kes perniagaan anda. Untuk mencipta peraturan baharu, pilih **Tambah peraturan**. Khususnya, jika anda tidak boleh memasukkan dan entiti dalam peraturan kerana laluan perhubungan yang ditetapkan, anda perlu mencipta peraturan baharu untuk memilih borang atribut.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Tambahkan peraturan baharu pada segmen dan pilih operator set.":::

   - Pilih salah satu operator set: **Kesatuan**, **Bersilang** atau **Kecuali**.

      - **Kesatuan** menyatukan dua kumpulan.
      - **Bersilang** dua kumpulan bertindih. Hanya data yang *lazim* kepada kedua-dua kumpulan kekal dalam kumpulan yang disatukan.
      - **Kecuali** menggabungkan dua kumpulan. Hanya data dalam Kumpulan A yang *tidak lazim* dengan data dalam kumpulan B disimpan.

1. Secara lalai, segmen menjana entiti output yang mengandungi semua atribut profil pelanggan yang sepadan dengan penapis yang ditentukan. Jika segmen berdasarkan entiti lain daripada entiti *Pelanggan*, anda boleh menambahkan lebih banyak atribut daripada entiti tersebut kepada entiti output. Pilih **Atribut projek** untuk memilih atribut yang akan ditambah pada entiti output.

   > [!IMPORTANT]
   > Untuk segmen berdasarkan akaun perniagaan, butiran satu atau lebih kenalan bagi setiap akaun daripada entiti *ContactProfile* perlu dimasukkan dalam segmen untuk membenarkan segmen diaktifkan atau dieksport ke destinasi yang memerlukan maklumat kenalan. Untuk mendapatkan maklumat lanjut tentang entiti *ContactProfile*, lihat [Pemetaan semantik](semantic-mappings.md).
   > Output sampel untuk segmen berdasarkan akaun perniagaan dengan atribut diunjurkan kenalan boleh kelihatan seperti ini:
   >
   > |ID  |Nama akaun  |Hasil  |Nama orang hubungan  | Peranan kenalan|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [Pengurus Pemerolehan,CEO]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Contoh atribut unjuran yang dipilih dalam anak tetingkap untuk ditambahkan pada entiti output.":::
  
   Sebagai contoh: Segmen adalah berdasarkan entiti yang mengandungi data pembelian yang berkaitan dengan entiti *Pelanggan*. Segmen tersebut mencari semua pelanggan dari Sepanyol yang membeli barangan pada tahun semasa. Anda boleh memilih untuk menambahkan atribut seperti harga barangan, atau tarikh pembelian pada semua rekod pelanggan yang sepadan dalam entiti output. Maklumat ini mungkin berguna untuk menganalisis korelasi bermusim dengan jumlah perbelanjaan.

   > [!NOTE]
   > - **Atribut projek** hanya berfungsi untuk entiti yang mempunyai perhubungan satu dengan banyak dengan entiti pelanggan. Contohnya, seorang pelanggan boleh mempunyai berbilang langganan.
   > - Jika atribut yang anda mahu projek lebih daripada satu hop daripada entiti *Pelanggan*, seperti yang ditakrifkan oleh perhubungan, atribut tersebut sepatutnya digunakan dalam setiap peraturan bagi pertanyaan segmen yang anda sedang bangunkan.
   > - Jika atribut yang anda mahu projek hanya lebih daripada satu hop daripada entiti *Pelanggan*, atribut tersebut tidak perlu wujud dalam setiap peraturan bagi pertanyaan segmen yang anda sedang bangunkan.
   > - **Atribut yang diunjurkan** difaktorkan apabila menggunakan operator set.

1. Pilih **Edit butiran** di sebelah segmen Tidak Bertajuk. Berikan nama untuk segmen anda dan kemas kini **Nama entiti output** yang dicadangkan untuk segmen tersebut. Secara pilihan, tambah perihalan dan [tag](work-with-tags-columns.md#manage-tags) pada segmen.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Kotak dialog Edit butiran butiran.":::

1. Pilih **Jalankan** untuk menyimpan segmen, aktifkan dan mulakan pemprosesan segmen anda berdasarkan semua peraturan dan syarat. Jika tidak, ia akan disimpan sebagai segmen tidak aktif.

1. Pilih **Kembali ke segmen** untuk kembali ke halaman **Segmen**.

1. Secara lalai, segmen dicipta sebagai segmen dinamik. Ia bermaksud bahawa segmen itu disegar semula semasa sistem penyegaran semula. Untuk [menghentikan segar semula automatik](segments.md#manage-existing-segments), pilih segmen, pilih pilihan **Buat statik**. Segmen statik hanya boleh [disegar semula secara manual](segments.md#refresh-segments) pada bila-bila masa.

> [!TIP]
> - Pembina segmen tidak akan mencadangkan nilai sah daripada entiti apabila menetapkan operator untuk syarat. Anda boleh pergi ke **Data** > **Entiti** dan memuat turun data entiti untuk melihat nilai yang tersedia.
> - Syarat berdasarkan tarikh yang membolehkan anda bertukar antara julat tarikh tetap dengan tarikh terapung.
> - Jika anda mempunyai berbilang peraturan untuk segmen anda, peraturan yang anda edit mempunyai baris biru menegak di sebelahnya.
> - Anda boleh memindahkan peraturan dan syarat ke tempat lain dalam definisi segmen. Pilih [...] bersebelahan dengan peraturan atau syarat, dan pilih cara dan tempat untuk memindahkannya.
> - Kawalan **Buat asal** dan **Buat Semula** dalam bar perintah membenarkan anda menggulung balik perubahan.

## <a name="quick-segments"></a>Segmen pantas

Segmen pantas membolehkan anda membina segmen ringkas dengan operator tunggal dengan pantas untuk wawasan yang lebih pantas.

1. Pada halaman **Segmen**, pilih **Baharu** > **Cipta daripada**.
   - Pilih pilihan **Profil** untuk membina segmen yang berasaskan pada entiti *pelanggan disatukan*.
   - Pilih pilihan **Ukuran** untuk membina segmen sekitar ukuran yang anda cipta sebelum ini.
   - Pilih pilihan **Kecerdasan** untuk membina segmen di sekitar salah satu entiti output yang dijana anda menggunakan sama ada keupayaan **Ramalan** atau **Model Tersuai**.

2. Dalam kotak dialog **Segmen pantas baharu**, pilih atribut daripada **Medan** juntai bawah.

3. Sistem akan menyediakan lebih banyak cerapan yang membantu anda mencipta segmen pelanggan yang lebih baik.
   - Untuk medan kategori, kami akan menunjukkan 10 kiraan pelanggan teratas. Pilih **Nilai** dan pilih **Semak Semula**.
   - Untuk atribut numerik, sistem akan menunjukkan apakah nilai atribut yang jatuh dalam setiap persentil pelanggan. Pilih **Operator** dan **Nilai**, kemudian pilih **Semak Semula**.

4. Sistem akan memberikan anda **saiz bahagian yang dianggarkan**. Anda boleh memilih sama ada untuk menjana bahagian yang anda takrif, atau kunjungi semula terlebih dahulu untuk mendapatkan saiz bahagian yang berbeza.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nama dan anggaran untuk segmen pantas.":::

5. **Berikan nama** entiti Nama **dan** Output untuk segmen anda. Secara pilihan, tambah [tag](work-with-tags-columns.md#manage-tags).

6. Pilih **Simpan** untuk mencipta bahagian.

7. Selepas bahagian selesai diproses, anda boleh melihatnya seperti bahagian lain yang anda cipta.

## <a name="next-steps"></a>Langkah seterusnya

[Eksport segmen](export-destinations.md) dan terokai [penyepaduan Kad Pelanggan](customer-card-add-in.md) untuk menggunakan segmen dalam aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
