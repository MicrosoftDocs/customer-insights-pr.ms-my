---
title: Lihat profil pelanggan
description: Melihat data pelanggan anda yang disatukan termasuk menggunakan carian dan penapis
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303794"
---
# <a name="view-customer-profiles"></a>Lihat profil pelanggan

Profil pelanggan tersedia sebaik sahaja anda [membuat entiti Pelanggan *bersatu*](data-unification.md). Paparan gabungan profil pelanggan bersatu anda dipaparkan pada **halaman Pelanggan**. Pelanggan boleh menjadi individu atau organisasi.

Pergi ke halaman **Pelanggan** untuk melihat pelanggan anda dan profil mereka. Setiap profil pelanggan diwakili oleh jubin. Gunakan kawalan penghalamanan untuk mendapatkan lebih banyak rekod. Kad memaparkan medan daripada entiti *Pelanggan* seperti yang ditakrifkan dalam **Indeks carian & penapis**. Susunan medan dalam setiap kad dipilih oleh sistem.

> [!NOTE]
> Jika anda tidak dapat melihat jubin apabila anda memilih **Pelanggan**, pentadbir anda perlu [menentukan sekurang-kurangnya satu atribut](search-filter-index.md) yang boleh dicari dalam **indeks** Carian &tapis.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Halaman pelanggan menunjukkan jubin hasil.":::

Pilih mana-mana tindakan berikut:
- [Lihat butiran pelanggan](#view-customer-details)
- [Urus indeks](search-filter-index.md) carian & tapis (pentadbir sahaja)
- [Tapis pelanggan](#filter-customers)
- **Kembangkan kad** atau **Runtuhkan kad** untuk mengembangkan atau meruntuhkan maklumat yang dipaparkan pada jubin pelanggan
- **Mengisih mengikut** atribut tertentu
- [Carian untuk pelanggan](#search-for-customers)

  > [!NOTE]
  > Untuk menggunakan carian dan penapis, pentadbir mesti mengkonfigurasi atribut yang boleh dicari dan menentukan medan boleh ditapis menggunakan indeks carian &penapis.

## <a name="search-for-customers"></a>Carian untuk pelanggan

Cari pelanggan dengan memasukkan nama atau beberapa atribut lain dalam **Pelanggan** carian. Atribut yang boleh dicari ditakrifkan oleh pentadbir dan datang dari entiti Pelanggan *bersatu*.

> [!NOTE]
> **Rentetan** ialah satu-satunya jenis data yang disertakan dalam carian. Gunakannya dalam **medan Cari pelanggan** pada halaman Pelanggan untuk mencari pelanggan.

## <a name="filter-customers"></a>Tapis pelanggan

Tapis pelanggan mengikut *bidang entiti Pelanggan*. Medan boleh ditapis ditakrifkan oleh pentadbir.

1. Pada halaman **Pelanggan**, pilih **Tunjukkan penapis**. Anak tetingkap Penapis dipaparkan.

1. Tandakan kotak di sebelah atribut bagi menapis pelanggan mengikut kemahuan anda.

1. Alih keluar semua penapis dengan memilih Kosongkan **penapis** atau kosongkan kotak semak di sebelah atribut yang dipilih.

1. Pilih **Sembunyikan penapis** untuk menutup anak tetingkap penapis.

1. Untuk menyimpan hasil penapis sebagai [segmen, pilih](segments.md) Simpan penapis sebagai **segmen**.
   1. Masukkan nama untuk segmen.
   1. Pilih **Simpan** untuk menyimpan segmen.
   1. Pilih sama ada untuk menjalankan segmen sekarang dengan **memilih Aktifkan** atau jalankan **kemudian**.

## <a name="view-customer-details"></a>Lihat butiran pelanggan

Pada halaman **Pelanggan**, pilih jubin pelanggan untuk melihat butiran bagi pelanggan terpilih.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Halaman butiran pelanggan.":::

Butiran pelanggan termasuk:

**Jubin** profil pelanggan menunjukkan nilai yang berbeza dari entiti Pelanggan *bersatu*. Jika medan tidak mempunyai nilai untuk profil pelanggan yang dipilih, medan tersebut tidak akan dipaparkan kecuali medan alamat. Jubin disusun ke dalam bahagian:

- Bahagian pertama menunjukkan set medan ditetapkan semula diikuti oleh semua medan yang merupakan sebahagian daripada indeks carian & penapis. Semua medan berkaitan alamat digabungkan menjadi satu baris, yang menunjukkan walaupun profil tidak mengandungi maklumat alamat.
- **Kenalan untuk paparan pelanggan** ini dalam persekitaran untuk akaun perniagaan (B-to-B). Setiap kenalan ditunjukkan dengan medan mereka. Medan kosong disembunyikan.
- **Medan** tambahan menunjukkan medan selebihnya pelanggan terpilih, kecuali ID.
- **ID menyenaraikan** semua ID di bawah nama entiti yang sepadan. Bidang dikenal pasti sebagai ID oleh semantik mereka.

**Garis masa aktiviti** menunjukkan data jika anda telah mengkonfigurasikan [aktiviti](activities.md). Pandangan garis masa mengandungi aktiviti yang diisih secara kronologi pelanggan yang dipilih, bermula dengan aktiviti paling terkini.

**Cerapan**:

- **Ukuran** menunjukkan jika anda telah mengkonfigurasikan [langkah](measures.md) atribut pelanggan. Ia termasuk KPI yang dikira pada pelanggan anda pada peringkat pelanggan individu.

- **Minat yang berpotensi, jenama** berpotensi menunjukkan jika anda mengkonfigurasi [pengayaan](enrichment-microsoft.md) pertalian jenama atau minat. Ia mewakili minat berpotensi dan afiniti untuk jenama yang berdasarkan kepada pelanggan lain yang profil serupa dengan profil pelanggan yang dipilih.

Untuk kembali ke **halaman Pelanggan**, pilih **Kembali kepada Pelanggan**.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[Tambah lebih banyak sumber data](data-sources.md), [perkayakan profil disatukan](enrichment-hub.md) atau [cipta segmen](segments.md) untuk berfungsi dengan profil pelanggan disatukan dalam aplikasi lain.

[!INCLUDE [footer-include](includes/footer-banner.md)]
