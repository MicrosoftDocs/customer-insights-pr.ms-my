---
title: Gabung entiti dalam penyatuan data
description: Gabung entiti untuk mencipta profil pelanggan disatukan.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085587"
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

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Pilihan dalam menu juntai bawah Tunjukkan lagi untuk mengurus atribut yang digabungkan.":::

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

## <a name="manually-combine-fields"></a>Gabungkan medan secara manual

Tentukan atribut yang digabungkan secara manual. 

1. Pada halaman **Gabung**, pilih **Gabungkan medan**.

1. Berikan **Nama** dan **Nama medan output**.

1. Pilih medan untuk ditambah. Pilih **Tambah medan** untuk menggabungkan lebih medan.

1. Sahkan pengecualian.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan. 

## <a name="change-the-order-of-fields"></a>Ubah pesanan pilihan

Sesetengah entiti mengandungi lebih banyak butiran daripada yang lain. Jika entiti termasuk data terkini tentang medan, anda boleh mengutamakannya daripada entiti lain apabila menggabungkan nilai.

1. Pilih medan yang digabungkan.
  
1. Pilih **Tunjukkan lagi** dan pilih **Edit**.

1. Dalam anak tetingkap **Gabungkan medan**, pilih **Alih ke atas/ke bawah** untuk menetapkan pesanan atau seret dan lepaskannya dalam kedudukan yang dikehendaki.

1. Sahkan perubahan.

1. Pilih **Simpan** dan **Jalankan** untuk memproses perubahan.

## <a name="run-your-merge"></a>Jalankan gabungan anda

Sama ada anda menggabungkan atribut secara manual atau membiarkan sistem menggabungkannya, anda sentiasa boleh menjalankan gabungan anda. Pilih **Jalankan** pada halaman **Gabung** untuk memulakan proses.

> [!div class="mx-imgBorder"]
> ![Simpan dan Jalankan gabungan data](media/configure-data-merge-save-run.png "Simpan dan Jalankan Gabungan Data")

Pilih **Jalankan Gabungan sahaja** jika anda hanya mahu melihat output yang ditunjukkan dalam entiti pelanggan disatukan. Proses hiliran akan disegar semula seperti yang [ditakrifkan dalam jadual segar semula](system.md#schedule-tab).

Pilih **Jalankan proses Gabungan dan hiliran** untuk menyegar semula sistem dengan perubahan anda. Semua proses termasuk pengayaan, segmen dan ukuran akan berjalan semula secara automatik. Selepas semua proses hiliran dilengkapkan, profil pelanggan menunjukkan sebarang perubahan yang anda lakukan.

Untuk membuat lebih banyak perubahan dan menjalankan semula langkah, anda boleh membatalkan penggabungan yang sedang dilaksanakan. Pilih teks **Menyegarkan semula ...** dan pilih **Batal kerja** di bahagian tepi tetingkap yang muncul.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="next-step"></a>Langkah Seterusnya

Konfigurasikan [aktiviti](activities.md), [pengayaan](enrichment-hub.md) atau [perhubungan](relationships.md) untuk mendapatkan wawasan lanjut tentang pelanggan anda.

Jika anda telah mengkonfigurasikan aktiviti, pengayaan atau segmen, ia akan diproses secara automatik untuk menggunakan data pelanggan terkini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
