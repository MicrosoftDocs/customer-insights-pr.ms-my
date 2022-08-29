---
title: Menyatukan medan pelanggan untuk penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
recommendations: false
ms.date: 07/27/2022
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
ms.openlocfilehash: 7ebd6ab8fa6ae141f33295a5d7723e96c8dc70ca
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304024"
---
# <a name="unify-customer-fields"></a>Menyatukan bidang pelanggan

Dalam langkah proses penyatuan ini, pilih dan kecualikan atribut untuk bergabung dalam entiti profil bersatu anda. Contohnya, jika tiga entiti mempunyai data e-mel, anda mungkin mahu menyimpan ketiga-tiga medan e-mel yang berasingan atau menggabungkannya ke dalam medan e-mel tunggal untuk profil bersatu. Sesetengah atribut secara automatik digabungkan oleh sistem. Anda boleh mencipta ID pelanggan yang stabil dan unik. Bagi pelanggan individu, anda boleh mengumpulkan profil yang berkaitan ke dalam kluster.

:::image type="content" source="media/m3_unify.png" alt-text="Halaman Menyatukan medan pelanggan dalam proses penyatuan data menunjukkan jadual dengan medan tercantum yang mentakrifkan profil pelanggan bersatu.":::

## <a name="review-and-update-the-customer-fields"></a>Menyemak dan mengemas kini medan pelanggan

1. Semak senarai medan yang akan disatukan di bawah tab **medan** Pelanggan jadual. Buat sebarang perubahan jika berkenaan.

   1. Untuk sebarang medan gabungan, anda boleh:
      - [Sunting](#edit-a-merged-field)
      - [Namakan semula](#rename-fields)
      - [Berasingan](#separate-merged-fields)
      - [Kecualikan](#exclude-fields)
      - [Bergerak ke atas atau ke bawah](#change-the-order-of-fields)

   1. Untuk sebarang medan tunggal, anda boleh:
      - [Gabungkan medan](#combine-fields-manually)
      - [Menggabungkan sekumpulan medan](#combine-a-group-of-fields)
      - [Namakan semula](#rename-fields)
      - [Kecualikan](#exclude-fields)
      - [Bergerak ke atas atau ke bawah](#change-the-order-of-fields)

1. Secara pilihan, [jana konfigurasi](#configure-customer-id-generation) ID pelanggan.

1. Secara pilihan untuk B-to-C, [profil kumpulan ke dalam isi rumah atau kluster](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Langkah seterusnya: Semak penyatuan](review-unification.md)

### <a name="edit-a-merged-field"></a>Edit medan yang digabungkan

1. Pilih medan tercantum dan pilih **Edit**. Anak tetingkap medan Gabung dipaparkan.

1. Tentukan cara untuk menyatukan atau menggabungkan medan daripada satu daripada tiga pilihan:
    - **Kepentingan**: Mengenal pasti nilai pemenang berdasarkan kedudukan kepentingan yang ditentukan untuk medan yang terlibat. Ia merupakan pilihan gabungan lalai. Pilih **Alih ke atas/bawah** untuk menetapkan kedudukan kepentingan.

      > [!NOTE]
      > Wawasan Pelanggan menggunakan nilai bukan nol pertama. Sebagai contoh, memandangkan entiti A, B dan C disenaraikan dalam susunan itu, jika A.Name dan B.Name adalah batal, maka nilai dari C.Name digunakan.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Pilihan kepentingan dalam dialog medan gabungan.":::

    - **Terkini**: Mengenal pasti nilai pemenang berdasarkan paling keterkinian. Memerlukan tarikh atau medan angka untuk setiap entiti yang mengambil bahagian dalam skop medan gabungan untuk menentukan keterkinian.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Pilihan keterkinian dalam dialog medan gabungan.":::

    - **Kurang terkini**: Mengenal pasti nilai pemenang berdasarkan kurang keterkinian. Memerlukan tarikh atau medan angka untuk setiap entiti yang mengambil bahagian dalam skop medan gabungan untuk menentukan keterkinian.

1. Anda boleh menambah lebih banyak medan untuk mengambil bahagian dalam proses gabungan.

1. Anda boleh menamakan semula medan yang digabungkan.

1. Pilih **Selesai** untuk menggunakan perubahan anda.

### <a name="rename-fields"></a>Menamakan semula medan

Mengubah nama paparan medan yang dicantumkan atau berasingan. Anda tidak boleh mengubah nama entiti output.

1. Pilih medan dan pilih **Namakan Semula**.

1. Masukkan nama paparan baharu.

1. Pilih **Selesai**.

### <a name="separate-merged-fields"></a>Pisahkan medan yang digabungkan

Untuk memisahkan medan yang digabungkan, cari atribut dalam jadual. Medan yang dipisahkan ditunjukkan sebagai titik data individu pada profil pelanggan disatukan.

1. Pilih medan tercantum dan pilih **Asingkan medan**.

1. Sahkan pengasingan.

### <a name="exclude-fields"></a>Mengecualikan medan

Kecualikan medan yang digabungkan atau berasingan daripada profil pelanggan bersatu. Jika medan digunakan dalam proses lain, contohnya dalam segmen, alih keluarkannya daripada proses ini sebelum mengecualikannya daripada profil pelanggan.

1. Pilih medan dan pilih **Kecualikan**.

1. Sahkan pengecualian.

Untuk melihat senarai semua medan yang dikecualikan, pilih **Medan dikecualikan**. Sekiranya perlu, anda boleh membaca medan yang dikecualikan.

### <a name="change-the-order-of-fields"></a>Ubah pesanan pilihan

Sesetengah entiti mengandungi lebih banyak butiran daripada yang lain. Jika entiti termasuk data terkini tentang medan, anda boleh mengutamakannya daripada entiti lain apabila menggabungkan nilai.

1. Pilih medan.
  
1. Pilih **Alih ke atas/bawah** untuk menetapkan tertib atau seret dan lepaskannya dalam kedudukan yang dikehendaki.

### <a name="combine-fields-manually"></a>Menggabungkan medan secara manual

Gabungkan medan berasingan untuk mencipta atribut gabungan.

1. Pilih **Gabungkan** > **Medan**. Anak tetingkap medan Gabung dipaparkan.

1. Tentukan dasar pemenang gabungan dalam **Satukan medan mengikut** menu juntai bawah.

1. Pilih **Tambah medan** untuk menggabungkan lebih banyak medan.

1. Berikan **Nama** dan **Nama medan output**.

1. Pilih **Selesai** untuk menggunakan perubahan tersebut.

### <a name="combine-a-group-of-fields"></a>Menggabungkan sekumpulan medan

Rawat sekumpulan medan sebagai satu unit. Contohnya, jika rekod kami mengandungi medan Alamat1, Alamat2, Bandar, Negeri dan Zip, kami tidak mahu bergabung dalam Rekod2 yang berbeza, memikirkan ia akan menjadikan data kami lebih lengkap.

1. Pilih **Gabungkan** > **Kumpulan medan**.

1. Tentukan dasar cantum pemenang **dalam kumpulan Kedudukan mengikut** juntai bawah.

1. Pilih **Tambah** dan pilih jika anda ingin menambah lebih banyak medan atau kumpulan pada medan.

1. **Berikan Nama** dan **nama** Output untuk setiap medan gabungan.

1. **Sediakan Nama** untuk kumpulan medan.

1. Pilih **Selesai** untuk menggunakan perubahan tersebut.

## <a name="configure-customer-id-generation"></a>Konfigurasikan penjanaan ID pelanggan

Tentukan cara menjana nilai ID pelanggan, pengecam profil pelanggan yang unik. Langkah menyatukan medan dalam proses penyatuan data menjana pengecam profil pelanggan yang unik. Pengecam ialah *ClientId* dalam *entiti Pelanggan* yang terhasil daripada proses penyatuan data.

CustomerId *·* adalah berdasarkan hash nilai pertama kunci utama pemenang bukan nol. Kekunci ini berasal dari entiti yang digunakan dalam penyatuan data dan dipengaruhi oleh susunan padanan.Jadi ID pelanggan yang dijana boleh berubah apabila nilai utama berubah dalam entiti utama pesanan padanan. Nilai utama utama mungkin tidak selalu mewakili pelanggan yang sama.

Mengkonfigurasi ID pelanggan yang stabil mendayakan anda mengelakkan tingkah laku itu.

1. Pilih tab **Kekunci**.

1. Letakkan penuding pada **baris CustomerId** dan pilih **Konfigurasi**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Kawalan untuk menyesuaikan penjanaan ID.":::

1. Pilih hingga lima medan yang akan terdiri daripada ID pelanggan unik dan lebih stabil. Rekod yang tidak sepadan dengan konfigurasi anda menggunakan ID yang dikonfigurasikan sistem.  

1. Pilih **Selesai**.

## <a name="group-profiles-into-households-or-clusters"></a>Profil kumpulan ke dalam isi rumah atau kluster

Bagi pelanggan individu, anda boleh menentukan peraturan untuk mengumpulkan profil berkaitan ke dalam kluster. Pada masa ini terdapat dua jenis kluster yang tersedia – kluster isi rumah dan tersuai. Sistem secara automatik memilih isi rumah dengan peraturan yang dipratentukan jika entiti *Pelanggan* mengandungi medan semantik *Person.LastName* dan *Location.Address*. Anda juga boleh mencipta Kluster dengan peraturan dan syarat anda sendiri, sama dengan [peraturan padanan](match-entities.md#define-rules-for-match-pairs).

1. Pilih **Advanced** > **Create cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Kawalan untuk mencipta kluster baharu.":::

1. Pilih antara **Isi rumah** atau kluster **Tersuai**. Jika medan semantik *Person.LastName* dan *Location.Address* wujud dalam entiti *Pelanggan*, isi rumah dipilih secara automatik.

1. Berikan nama untuk kluster dan pilih **Selesai**.

1. Pilih tab **Kluster** untuk mencari kluster yang anda cipta.

1. Tentukan peraturan dan syarat untuk mentakrifkan gugusan anda.

1. Pilih **Selesai**. Kluster ini diwujudkan apabila proses penyatuan selesai. Pengecam kelompok ditambahkan sebagai medan baru kepada *entiti Pelanggan*.

> [!div class="nextstepaction"]
> [Langkah seterusnya: Semak penyatuan](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
