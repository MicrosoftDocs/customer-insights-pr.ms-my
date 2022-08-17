---
title: Menyatukan medan pelanggan untuk penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: a6f29c4985ee274207d122fb1bd76d97b98613b6
ms.sourcegitcommit: 10dcfc32eaf8ec0903be96136dca7bb4e250276a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/01/2022
ms.locfileid: "9213593"
---
# <a name="unify-customer-fields-for-data-unification"></a>Menyatukan medan pelanggan untuk penyatuan data

Dalam langkah proses penyatuan ini, pilih dan kecualikan atribut untuk digabungkan dalam entiti profil bersatu anda. Sebagai contoh, jika tiga entiti mempunyai data e-mel, anda mungkin mahu menyimpan ketiga-tiga medan e-mel yang berasingan atau menggabungkannya ke dalam medan e-mel tunggal untuk profil bersatu. Sesetengah atribut digabungkan secara automatik oleh sistem. Anda boleh mencipta ID pelanggan yang stabil dan unik dan profil berkaitan kumpulan ke dalam kelompok.

:::image type="content" source="media/m3_unify.png" alt-text="Halaman gabung dalam proses penyatuan data menunjukkan jadual dengan medan digabungkan yang mentakrifkan profil pelanggan disatukan.":::

## <a name="review-and-update-the-customer-fields"></a>Semak dan kemas kini medan pelanggan

1. Semak semula senarai medan yang akan disatukan **di bawah tab Medan** pelanggan jadual. Buat sebarang perubahan jika berkenaan.

   1. Untuk mana-mana medan gabungan, anda boleh:
      - [Sunting](#edit-a-merged-field)
      - [Namakan semula](#rename-fields)
      - [Berasingan](#separate-merged-fields)
      - [Kecualikan](#exclude-fields)
      - [Bergerak ke atas atau ke bawah](#change-the-order-of-fields)

   1. Untuk mana-mana medan tunggal, anda boleh:
      - [Gabungkan medan](#combine-fields-manually)
      - [Gabungkan sekumpulan medan](#combine-a-group-of-fields)
      - [Namakan semula](#rename-fields)
      - [Kecualikan](#exclude-fields)
      - [Bergerak ke atas atau ke bawah](#change-the-order-of-fields)

1. Secara pilihan, [menjana konfigurasi ID pelanggan](#configure-customer-id-generation).

1. Secara pilihan, [profil kumpulan ke dalam isi rumah atau kelompok](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Langkah seterusnya: Semak penyatuan](review-unification.md)

### <a name="edit-a-merged-field"></a>Edit medan yang digabungkan

1. Pilih medan yang digabungkan dan pilih **Edit**. Anak tetingkap Gabungkan medan dipaparkan.

1. Tentukan cara untuk menyatukan atau menggabungkan medan daripada satu daripada tiga pilihan:
    - **Kepentingan**: Mengenal pasti nilai pemenang berdasarkan kedudukan kepentingan yang ditentukan untuk medan yang terlibat. Ia merupakan pilihan gabungan lalai. Pilih **Alih ke atas/bawah** untuk menetapkan kedudukan kepentingan.

      > [!NOTE]
      > Wawasan Pelanggan menggunakan nilai bukan batal pertama. Sebagai contoh, entiti yang diberikan A, B, dan C disenaraikan dalam urutan itu, jika A.Name dan B.Name adalah batal, maka nilai dari C.Name digunakan.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Pilihan kepentingan dalam dialog medan gabungan.":::

    - **Terkini**: Mengenal pasti nilai pemenang berdasarkan paling keterkinian. Memerlukan tarikh atau medan angka untuk setiap entiti yang mengambil bahagian dalam skop medan gabungan untuk menentukan keterkinian.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Pilihan keterkinian dalam dialog medan gabungan.":::

    - **Kurang terkini**: Mengenal pasti nilai pemenang berdasarkan kurang keterkinian. Memerlukan tarikh atau medan angka untuk setiap entiti yang mengambil bahagian dalam skop medan gabungan untuk menentukan keterkinian.

1. Anda boleh menambah lebih banyak medan untuk mengambil bahagian dalam proses gabungan.

1. Anda boleh menamakan semula medan yang digabungkan.

1. Pilih **Selesai** untuk menggunakan perubahan anda.

### <a name="rename-fields"></a>Namakan semula medan

Tukar nama paparan medan yang digabungkan atau berasingan. Anda tidak boleh mengubah nama entiti output.

1. Pilih medan dan pilih **Namakan semula**.

1. Masukkan nama paparan baru.

1. Pilih **Selesai**.

### <a name="separate-merged-fields"></a>Pisahkan medan yang digabungkan

Untuk memisahkan medan yang digabungkan, cari atribut dalam jadual. Medan yang dipisahkan ditunjukkan sebagai titik data individu pada profil pelanggan disatukan.

1. Pilih medan yang digabungkan dan pilih Medan **berasingan**.

1. Sahkan pengasingan.

### <a name="exclude-fields"></a>Kecualikan medan

Kecualikan medan yang digabungkan atau berasingan daripada profil pelanggan bersatu. Jika medan digunakan dalam proses lain, contohnya dalam segmen, alih keluarkannya daripada proses ini sebelum mengecualikannya daripada profil pelanggan.

1. Pilih medan dan pilih **Kecualikan**.

1. Sahkan pengecualian.

Untuk melihat senarai semua medan yang dikecualikan, pilih Medan **dikecualikan**. Sekiranya perlu, anda boleh membaca medan yang dikecualikan.

### <a name="change-the-order-of-fields"></a>Ubah pesanan pilihan

Sesetengah entiti mengandungi lebih banyak butiran daripada yang lain. Jika entiti termasuk data terkini tentang medan, anda boleh mengutamakannya daripada entiti lain apabila menggabungkan nilai.

1. Pilih medan.
  
1. Pilih **Alih ke atas/bawah** untuk menetapkan tertib atau seret dan lepaskannya dalam kedudukan yang dikehendaki.

### <a name="combine-fields-manually"></a>Gabungkan medan secara manual

Gabungkan medan berasingan untuk mencipta atribut yang digabungkan.

1. Pilih **Gabungkan** > **Medan**. Anak tetingkap Gabungkan medan dipaparkan.

1. Tentukan dasar pemenang gabungan dalam **Satukan medan mengikut** menu juntai bawah.

1. Pilih **Tambah medan** untuk menggabungkan lebih banyak medan.

1. Berikan **Nama** dan **Nama medan output**.

1. Pilih **Selesai** untuk menggunakan perubahan tersebut.

### <a name="combine-a-group-of-fields"></a>Gabungkan sekumpulan medan

Rawat sekumpulan medan sebagai satu unit. Sebagai contoh, jika rekod kami mengandungi medan Alamat1, Alamat2, Bandar, Negeri dan Zip, kami tidak mahu bergabung dalam Alamat rekod yang berbeza2, memikirkan ia akan menjadikan data kami lebih lengkap.

1. Pilih **Gabungkan** > **Kumpulan medan**.

1. Tentukan dasar pemenang cantum dalam **kumpulan Kedudukan mengikut** juntai bawah.

1. Pilih **Tambah** dan pilih jika anda ingin menambah lebih banyak medan atau kumpulan pada medan.

1. **Sediakan Nama** dan **nama** Output untuk setiap medan gabungan.

1. **Sediakan Nama** untuk kumpulan medan.

1. Pilih **Selesai** untuk menggunakan perubahan tersebut.

## <a name="configure-customer-id-generation"></a>Konfigurasikan penjanaan ID pelanggan

Tentukan cara menjana nilai ID pelanggan, pengecam profil pelanggan yang unik. Langkah menyatukan medan dalam proses penyatuan data menjana pengecam profil pelanggan yang unik. Pengenalpasti ialah *CustomerId* dalam *entiti Pelanggan* yang terhasil daripada proses penyatuan data.

CustomerId *·* adalah berdasarkan cincangan nilai pertama kekunci utama pemenang bukan batal. Kekunci ini berasal dari entiti yang digunakan dalam penyatuan data dan dipengaruhi oleh urutan padanan.Jadi ID pelanggan yang dijana boleh berubah apabila nilai utama berubah dalam entiti utama pesanan padanan. Nilai kunci utama mungkin tidak selalu mewakili pelanggan yang sama.

Mengkonfigurasi ID pelanggan yang stabil mendayakan anda mengelakkan tingkah laku itu.

1. Pilih tab **Kekunci**.

1. Tuding pada **baris CustomerId** dan pilih **Konfigurasi**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kawalan untuk menyesuaikan penjanaan ID.":::

1. Pilih hingga lima medan yang akan terdiri daripada ID pelanggan unik dan lebih stabil. Rekod yang tidak sepadan dengan konfigurasi anda menggunakan ID yang dikonfigurasikan sistem.  

1. Pilih **Selesai**.

## <a name="group-profiles-into-households-or-clusters"></a>Profil kumpulan ke dalam isi rumah atau kluster

Anda boleh mentakrifkan peraturan untuk mengumpulkan profil berkaitan ke dalam kelompok. Pada masa ini terdapat dua jenis kluster yang tersedia – kluster isi rumah dan tersuai. Sistem secara automatik memilih isi rumah dengan peraturan yang dipratentukan jika entiti *Pelanggan* mengandungi medan semantik *Person.LastName* dan *Location.Address*. Anda juga boleh mencipta Kluster dengan peraturan dan syarat anda sendiri, sama dengan [peraturan padanan](match-entities.md#define-rules-for-match-pairs).

1. Pilih **Kluster** > **Cipta Lanjutan**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kawalan untuk mencipta kluster baharu.":::

1. Pilih antara **Isi rumah** atau kluster **Tersuai**. Jika medan semantik *Person.LastName* dan *Location.Address* wujud dalam entiti *Pelanggan*, isi rumah dipilih secara automatik.

1. Berikan nama untuk kluster dan pilih **Selesai**.

1. Pilih tab **Kluster** untuk mencari kluster yang anda cipta.

1. Tentukan peraturan dan syarat untuk mentakrifkan gugusan anda.

1. Pilih **Selesai**. Kelompok ini dicipta apabila proses penyatuan selesai. Pengenalpasti kluster ditambah sebagai medan baru kepada *entiti Pelanggan*.

> [!div class="nextstepaction"]
> [Langkah seterusnya: Semak penyatuan](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
