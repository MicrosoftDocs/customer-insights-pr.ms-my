---
title: Gabung entiti dalam penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
ms.date: 01/28/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 978a7c9bc440398fa39e9fa1d366d74e5c7aaea0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643854"
---
# <a name="merge-entities"></a>Gabungkan entiti

Fasa gabung ialah fasa terakhir dalam proses penyatuan data. Tujuannya ialah untuk menyesuaikan data berkonflik. Contoh data berkonflik termasuk nama pelanggan yang ditemui dalam dua set data anda tetapi menunjukkan sedikit berbeza dalam setiap ("Grant Marshall" berbanding "Grant Marshal") atau nombor telefon yang berbeza dalam format (617-803-091X berbanding 617803091X). Menggabungkan titik data berkonflik itu dilakukan secara atribut dengan atribut.

:::image type="content" source="media/merge-fields-page.png" alt-text="Halaman gabung dalam proses penyatuan data menunjukkan jadual dengan medan digabungkan yang mentakrifkan profil pelanggan disatukan.":::

Selepas menyelesaikan [fasa padan](match-entities.md), anda boleh memulakan fasa gabung dengan memilih jubin **Gabung** pada halaman **Satukan**.

## <a name="review-system-recommendations"></a>Semak semula pengesyoran sistem

Pada **Data** > **Satukan** > **Gabung**, anda memilih dan mengecualikan atribut untuk bergabung dalam entiti profil pelanggan disatukan anda. Profil pelanggan disatukan adalah hasil daripada proses data penyatuan. Sesetengah atribut digabungkan oleh sistem secara automatik.

Untuk melihat atribut yang disertakan dalam salah satu atribut yang digabungkan secara automatik, pilih atribut yang digabungkan dalam tab **Medan pelanggan** jadual. Atribut yang digubah bagi atribut yang digabungkan dipaparkan dalam dua baris baharu di bawah atribut yang digabungkan.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Asingkan, namakan semula, kecualikan, dan edit medan yang digabungkan

Anda boleh mengubah cara sistem memproses atribut yang digabungkan untuk menjana profil pelanggan disatukan. Pilih **Tunjukkan lagi** dan pilih perkara yang anda mahu ubah.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Pilihan dalam menu Tunjukkan lagi juntai bawah untuk menguruskan atribut yang digabungkan.":::

Untuk maklumat lanjut, lihat bahagian berikut.

## <a name="separate-merged-fields"></a>Pisahkan medan yang digabungkan

Untuk memisahkan medan yang digabungkan, cari atribut dalam jadual. Medan yang dipisahkan ditunjukkan sebagai titik data individu pada profil pelanggan disatukan. 

1. Pilih medan yang digabungkan.
  
1. Pilih **Tunjukkan lagi** dan pilih **Medan berasingan**.
 
1. Sahkan pengasingan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="rename-merged-fields"></a>Namakan semula medan yang digabungkan

Tukar nama paparan bagi atribut yang digabungkan. Anda tidak boleh mengubah nama entiti output.

1. Pilih medan yang digabungkan.
  
1. Pilih **Tunjukkan lagi** dan pilih **Namakan Semula**.

1. Sahkan nama paparan yang ditukar. 

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="exclude-merged-fields"></a>Kecualikan medan yang digabungkan

Kecualikan atribut daripada profil pelanggan disatukan. Jika medan digunakan dalam proses lain, contohnya dalam segmen, alih keluarkannya daripada proses ini sebelum mengecualikannya daripada profil pelanggan. 

1. Pilih medan yang digabungkan.
  
1. Pilih **Tunjukkan lagi** dan pilih **Kecualikan**.

1. Sahkan pengecualian.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

Pada halaman **Gabung**, pilih **Medan yang dikecualikan** untuk melihat senarai semua medan yang dikecualikan. Anak tetingkap ini membenarkan anda menambah semula medan yang dikecualikan.

## <a name="edit-a-merged-field"></a>Edit medan yang digabungkan

1.  Pilih medan yang digabungkan.

1.  Pilih **Tunjukkan lagi** dan pilih **Edit**.

1.  Tentukan cara untuk menyatukan atau menggabungkan medan daripada satu daripada tiga pilihan:
    - **Kepentingan**: Mengenal pasti nilai pemenang berdasarkan kedudukan kepentingan yang ditentukan untuk medan yang terlibat. Ia merupakan pilihan gabungan lalai. Pilih **Alih ke atas/bawah** untuk menetapkan kedudukan kepentingan.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Pilihan kepentingan dalam dialog medan gabungan."::: 
    - **Terkini**: Mengenal pasti nilai pemenang berdasarkan paling keterkinian. Memerlukan tarikh atau medan angka untuk setiap entiti yang mengambil bahagian dalam skop medan gabungan untuk menentukan keterkinian.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Pilihan keterkinian dalam dialog medan gabungan.":::
    - **Kurang terkini**: Mengenal pasti nilai pemenang berdasarkan kurang keterkinian. Memerlukan tarikh atau medan angka untuk setiap entiti yang mengambil bahagian dalam skop medan gabungan untuk menentukan keterkinian.

1.  Anda boleh menambah lebih banyak medan untuk mengambil bahagian dalam proses gabungan.

1.  Anda boleh menamakan semula medan yang digabungkan.

1. Pilih **Selesai** untuk menggunakan perubahan anda.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="combine-fields-manually"></a>Gabungkan medan secara manual

Tentukan atribut yang digabungkan secara manual.

1. **Pada halaman Gabungkan**, pilih **Gabungkan**.

1. Pilih opsyen **Medan**.

1. Tentukan dasar pemenang gabungan dalam **Satukan medan mengikut** menu juntai bawah.

1. Pilih medan untuk ditambah. Pilih **Tambah medan** untuk menggabungkan lebih medan.

1. Berikan **Nama** dan **Nama medan output**.

1. Pilih **Selesai** untuk menggunakan perubahan tersebut.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="combine-a-group-of-fields"></a>Gabungkan sekumpulan medan

Rawat sekumpulan medan sebagai satu unit. Contohnya, apabila jika rekod kami mengandungi medan Alamat1, Alamat2, Bandar, Negeri dan Zip. Kami mungkin tidak mahu bergabung dalam rekod yang berbeza Alamat2, memikirkan ia akan menjadikan data kami lebih lengkap

1. **Pada halaman Gabungkan**, pilih **Gabungkan**.

1. Pilih opsyen **Kumpulan medan**.

1. Tentukan dasar pemenang gabungan dalam **kumpulan Rank mengikut** dropdown.

1. Pilih **Tambah** dan pilih jika anda ingin menambah lebih banyak medan atau kumpulan tambahan pada medan.

1. **Berikan Nama** dan **nama** Output untuk setiap medan gabungan.

1. **Sediakan Nama** untuk kumpulan medan. 

1. Pilih **Selesai** untuk menggunakan perubahan tersebut.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="change-the-order-of-fields"></a>Ubah pesanan pilihan

Sesetengah entiti mengandungi lebih banyak butiran daripada yang lain. Jika entiti termasuk data terkini tentang medan, anda boleh mengutamakannya daripada entiti lain apabila menggabungkan nilai.

1. Pilih medan yang digabungkan.
  
1. Pilih **Tunjukkan lagi** dan pilih **Edit**.

1. Dalam anak tetingkap **Gabungkan medan**, pilih **Alih ke atas/ke bawah** untuk menetapkan pesanan atau seret dan lepaskannya dalam kedudukan yang dikehendaki.

1. Sahkan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="configure-customer-id-generation"></a>Konfigurasikan penjanaan ID Pelanggan 

Selepas mengkonfigurasikan medan penggabungan, anda boleh menentukan cara menjana nilai CustomerId, pengecam profil pelanggan yang unik. Langkah gabungan dalam proses penyatuan data akan menjana pengecam profil pelanggan yang unik. Pengecam ialah CustomerId dalam entiti *Pelanggan* yang terhasil daripada proses penyatuan data. 

CustomerId dalam entiti Pelanggan ialah berdasarkan cincang nilai pertama daripada kunci utama pemenang bukan nol. Kekunci ini berasal daripada entiti yang digunakan dalam fasa padanan dan gabungan, dan dipengaruhi oleh urutan padanan.Jadi CustomerID yang dijana boleh berubah apabila nilai kekunci utama berubah dalam entiti utama urutan padanan. Jadi, nilai kunci utama mungkin tidak semestinya mewakili pelanggan yang sama.

Mengkonfigurasi ID pelanggan yang stabil mendayakan anda mengelakkan tingkah laku itu.

**Konfigurasikan ID pelanggan unik**

1. Pergi ke **Satukan** > **Gabung**.

1. Pilih tab **Kekunci**. 

1. Tuding pada baris **CustomerId** dan pilih pilihan **Konfigurasi**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kawalan untuk menyesuaikan penjanaan ID.":::

1. Pilih hingga lima medan yang akan terdiri daripada ID pelanggan unik dan lebih stabil. Rekod yang tidak sepadan dengan konfigurasi anda menggunakan ID yang dikonfigurasikan sistem.  

1. Pilih **Selesai** dan jalankan proses gabungan untuk menggunakan perubahan anda.

## <a name="group-profiles-into-households-or-clusters"></a>Profil kumpulan ke dalam isi rumah atau kluster

Sebagai sebahagian daripada proses konfigurasi penjanaan profil pelanggan, anda boleh mentakrifkan peraturan kepada profil berkaitan kumpulan ke dalam kluster. Pada masa ini terdapat dua jenis kluster yang tersedia – kluster isi rumah dan tersuai. Sistem secara automatik memilih isi rumah dengan peraturan yang dipratentukan jika entiti *Pelanggan* mengandungi medan semantik *Person.LastName* dan *Location.Address*. Anda juga boleh mencipta Kluster dengan peraturan dan syarat anda sendiri, sama dengan [peraturan padanan](match-entities.md#define-rules-for-match-pairs).

**Takrifkan isi rumah atau kluster**

1. Pergi ke **Satukan** > **Gabung**.

1. Pada tab **Gabung**, pilih **Lanjutan** > **Cipta kluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kawalan untuk mencipta kluster baharu.":::

1. Pilih antara **Isi rumah** atau kluster **Tersuai**. Jika medan semantik *Person.LastName* dan *Location.Address* wujud dalam entiti *Pelanggan*, isi rumah dipilih secara automatik.

1. Berikan nama untuk kluster dan pilih **Selesai**.

1. Pilih tab **Kluster** untuk mencari kluster yang anda cipta.

1. Tentukan peraturan dan syarat untuk mentakrifkan gugusan anda.

1. Pilih **Jalankan** untuk menjalankan proses gabungan dan mencipta kluster.

Selepas menjalankan proses penggabungan, pengecam kluster akan ditambah sebagai medan baharu kepada entiti *Pelanggan*.

## <a name="run-your-merge"></a>Jalankan gabungan anda

Sama ada anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, anda sentiasa boleh menjalankan gabungan anda. Pilih **Jalankan** pada halaman **Gabung** untuk memulakan proses.

> [!div class="mx-imgBorder"]
> ![Simpan dan Jalankan gabungan data.](media/configure-data-merge-save-run.png "Simpan dan Jalankan Gabungan Data")

Pilih **Jalankan Gabungan sahaja** jika anda hanya mahu melihat output yang ditunjukkan dalam entiti pelanggan disatukan. Proses hiliran akan disegar semula seperti yang [ditakrifkan dalam jadual segar semula](system.md#schedule-tab).

Pilih **Jalankan proses Gabungan dan hiliran** untuk menyegar semula sistem dengan perubahan anda. Semua proses termasuk pengayaan, segmen dan ukuran akan berjalan semula secara automatik. Selepas semua proses hiliran dilengkapkan, profil pelanggan menunjukkan sebarang perubahan yang anda lakukan.

Untuk membuat lebih banyak perubahan dan menjalankan semula langkah, anda boleh membatalkan penggabungan yang sedang dilaksanakan. Pilih teks **Menyegarkan semula ...** dan pilih **Batal kerja** di bahagian tepi tetingkap yang muncul.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Laluan gerudi bawah untuk mendapatkan butiran proses daripada pautan status tugas.":::

## <a name="next-step"></a>Langkah Seterusnya

Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-hub.md) atau [perhubungan](relationships.md) untuk mendapatkan wawasan lanjut tentang pelanggan anda.

Jika anda telah mengkonfigurasikan aktiviti, pengayaan atau segmen, ia akan diproses secara automatik untuk menggunakan data pelanggan terkini.

[!INCLUDE [footer-include](includes/footer-banner.md)]
