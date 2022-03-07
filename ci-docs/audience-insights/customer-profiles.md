---
title: Lihat profil pelanggan
description: Dapatkan pandangan gabungan data pelanggan disatukan anda.
ms.date: 09/30/2021
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
ms.openlocfilehash: 3a17716508a14020c56640c7d68f300a9d721af4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354892"
---
# <a name="customer-profiles"></a>Profil pelanggan

Halaman **Pelanggan** menunjukkan pandangan gabungan profil pelanggan anda yang disatukan. Profil pelanggan tersedia sebaik sahaja anda [mencipta entiti Pelanggan disatukan](data-unification.md). Halaman membenarkan anda mencari pelanggan dan mentakrifkan indeks untuk carian tersebut.

Pelanggan boleh menjadi individu atau organisasi. Setiap profil pelanggan diwakili oleh jubin. Gunakan kawalan penghalamanan untuk mendapatkan lebih banyak rekod. Kad memaparkan medan daripada entiti *Pelanggan* seperti yang ditakrifkan dalam **Indeks carian & penapis**. Pilih jubin untuk melihat data untuk pelanggan yang dipilih dalam halaman khusus yang dipanggil [Halaman butiran pelanggan](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Halaman pelanggan menunjukkan jubin hasil](media/customers-page-result-tiles-B2C.png "Halaman pelanggan menunjukkan jubin hasil")

> [!NOTE]
> Jika anda tidak dapat melihat jubin apabila anda memilih **Pelanggan** dalam navigasi, pentadbir anda perlu [mentakrifkan sekurang-kurangnya satu atribut yang boleh dicari](search-filter-index.md) dalam **Indeks carian & penapis**.

## <a name="search-for-customers"></a>Carian untuk pelanggan

Carian untuk pelanggan dengan memasukkan nama atau beberapa atribut yang lain dalam kotak carian. Carian hanya berfungsi dalam entiti _Pelanggan_ yang dicipta semasa proses data penyatuan.

Sebagai pentadbir, anda boleh konfigurasikan atribut boleh dicari menggunakan halaman **Indeks Carian & Tapis**. Untuk mendapatkan maklumat lanjut, pergi ke [Urus indeks carian & penapis](search-filter-index.md).

## <a name="filter-customers"></a>Tapis pelanggan

Anda boleh menapis pelanggan mengikut medan entiti _Pelanggan_. Sama seperti carian, pada mulanya pentadbir anda perlu menakrif medan sebagai boleh ditapis menggunakan halaman **Indeks Carian & Tapis**.

1. Pilih **Tunjuk penapis** pada halaman **Pelanggan**.

1. Tandakan kotak di sebelah atribut bagi menapis pelanggan mengikut kemahuan anda.

1. Alih keluar penapis anda dengan memilih **Kosongkan penapis** pada halaman **Pelanggan**.

## <a name="customer-details-page"></a>Halaman butiran pelanggan

Pilih sebarang jubin pelanggan untuk membuka **halaman butiran pelanggan**. Pandangan ini mengandungi maklumat disatukan untuk pelanggan terpilih. Butiran pelanggan termasuk kandungan berikut:

**Jubin profil pelanggan** : Jubin ini menunjukkan nilai berbeza daripada entiti _Pelanggan_ disatukan. Jika medan tidak mempunyai nilai untuk profil pelanggan yang dipilih, ia tidak akan dipaparkan. Jubin disusun ke dalam bahagian:  
  - Bahagian pertama menunjukkan set medan ditetapkan semula diikuti oleh semua medan yang merupakan sebahagian daripada indeks carian & penapis. Semua medan berkaitan alamat digabungkan ke dalam satu baris tunggal jika profil mengandungi medan tersebut. 
  - **Kenalan untuk pelanggan ini** : Dalam persekitaran untuk akaun perniagaan, anda akan melihat semua kenalan yang berkaitan untuk pelanggan ini sebagai bahagian kedua. Setiap kenalan ditunjukkan dengan medan mereka. Medan kosong disembunyikan.
  - **Medan tambahan** : Menunjukkan medan selebihnya bagi pelanggan yang dipilih kecuali ID. 
  - **ID** : Senaraikan semua ID di bawah nama entiti sepadan mereka. Medan dikenal pasti sebagai ID oleh semantik mereka yang mengkategorikan mereka sedemikian.

**Garis masa aktiviti** : Menunjukkan data jika anda telah mengkonfigurasi aktiviti. Pandangan garis masa mengandungi aktiviti yang diisih secara kronologi pelanggan yang dipilih, bermula dengan aktiviti paling terkini. Untuk mendapatkan maklumat lanjut, pergi ke [Aktiviti pelanggan](activities.md).

**Cerapan**:  
  - **Ukuran** : Menunjukkan jika anda mengkonfigurasikan satu atau lebih ukuran ukuran atribut pelanggan. Ia termasuk KPI yang dikira pada pelanggan anda pada peringkat pelanggan individu. Untuk mendapatkan maklumat lanjut, pergi ke [Takrifkan dan uruskan ukuran](measures.md).

  - **Minat yang berpotensi, jenama berpotensi** : Menunjukkan jika anda mengkonfigurasi jenama atau pengayaan afiniti yang diminati. Ia mewakili minat berpotensi dan afiniti untuk jenama yang berdasarkan kepada pelanggan lain yang profil serupa dengan profil pelanggan yang dipilih. Untuk mendapatkan maklumat lanjut, pergi ke [Perkayakan profil pelanggan dengan jenama dan afiniti minat](enrichment-microsoft.md).

Untuk kembali ke halaman carian pelanggan, pilih **Kembali kepada Pelanggan**.

## <a name="next-steps"></a>Langkah seterusnya

[Tambah lebih banyak sumber data](data-sources.md), [perkayakan profil disatukan](enrichment-hub.md) atau [cipta segmen](segments.md) untuk berfungsi dengan profil pelanggan disatukan dalam aplikasi lain.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
