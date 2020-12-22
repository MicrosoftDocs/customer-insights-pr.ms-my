---
title: Lihat profil pelanggan
description: Dapatkan pandangan gabungan data pelanggan disatukan anda.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653901"
---
# <a name="customer-profiles"></a>Profil pelanggan

Halaman **Pelanggan** menunjukkan pandangan gabungan pelanggan anda, berdasarkan data profil yang dikumpulkan daripada [semua sumber data](data-sources.md). Profil pelanggan tersedia sebaik sahaja anda [mencipta entiti Pelanggan disatukan](data-unification.md). Pastikan anda melengkapkan proses penyatuan data untuk mendapatkan lebih banyak pandangan tentang pelanggan anda. Halaman itu juga membenarkan anda membuat carian untuk pelanggan.

Pelanggan boleh individu atau organisasi (pratonton). Setiap profil pelanggan atau organisasi diwakili oleh jubin. Pilih jubin untuk melihat maklumat tambahan tentang pelanggan atau organisasi tertentu. Gunakan kawalan penomboran halaman pada bahagian bawah halaman untuk melihat rekod tambahan.

> [!div class="mx-imgBorder"] 
> ![Profil pelanggan B2C](media/profiles-customers.png "Profil pelanggan B2C")

Organisasi (Pratonton)
> [!div class="mx-imgBorder"] 
> ![Profil pelanggan B2B](media/profile-customers-b2b.png "Profil pelanggan B2B")

> [!NOTE]
> Jika anda tidak dapat melihat jubin apabila anda memilih **Pelanggan** dalam navigasi, pentadbir anda perlu untuk [mentakrifkan sekurang-kurangnya satu atribut yang boleh dicari](search-filter-index.md) pada **Indeks carian & penapis**.

## <a name="search-for-customers"></a>Carian untuk pelanggan

Carian untuk pelanggan dengan memasukkan nama atau beberapa atribut yang lain dalam kotak carian. Carian hanya berfungsi dalam entiti Profil Pelanggan yang dicipta semasa proses penyatuan data.

Sebagai pentadbir, anda boleh konfigurasikan atribut boleh dicari menggunakan halaman **Indeks Carian & Tapis**. Untuk maklumat lanjut, lihat [Mengurus indeks carian & tapis](search-filter-index.md).

## <a name="filter-customers"></a>Tapis pelanggan

Anda boleh menapis pelanggan dengan medan entiti Profil Pelanggan. Sama seperti carian, pada mulanya pentadbir anda perlu menakrif medan sebagai boleh ditapis menggunakan halaman **Indeks Carian & Tapis**.

1. Pilih **Tapis** pada halaman **Pelanggan**.

2. Tandakan kotak di sebelah atribut bagi menapis pelanggan mengikut kemahuan anda.

   > [!div class="mx-imgBorder"] 
   > ![Profil pelanggan](media/profiles-customers3.png "Profil pelanggan")

3. Alih keluar penapis anda dengan memilih **Kosongkan penapis** pada halaman **Pelanggan**.

##  <a name="customer-details-page"></a>Halaman butiran pelanggan

Pilih sebarang jubin pelanggan untuk membuka **halaman butiran pelanggan**. Pandangan ini mengandungi maklumat disatukan untuk pelanggan terpilih.

Butiran pelanggan termasuk:

-   **Jubin profil pelanggan:** Jubin ini menunjukkan nilai berbeza daripada entiti profil pelanggan disatukan. Butiran ini boleh termasuk alamat e-mel, nama, bandar dan sebagainya. 

-   **Kemungkinan minat, bakal jenama:** Menunjukkan jika anda mengkonfigurasi pengayaan pihak pertama. Ia mewakili kepentingan yang berkemungkinan dan afiniti untuk jenama pelanggan dengan profil yang serupa dengan pelanggan ini mungkin miliki. Untuk maklumat lanjut, lihat [Perkayakan profil pelanggan. dengan afiniti jenama dan kepentingan](enrichment-microsoft-graph.md).

-   **Langkah:** Menunjukkan jika anda mengkonfigurasi satu atau lebih langkah daripada jenis khusus: langkah atribut pelanggan. Ia termasuk KPI yang dikira pada pelanggan anda pada peringkat pelanggan individu. Untuk maklumat lanjut, lihat [Langkah mentakrif dan mengurus](measures.md).

-   **Garis masa aktiviti:** Menunjukkan jika anda telah mengkonfigurasi aktiviti. Pandangan garis masa mengandungi aktiviti yang disusun secara kronologi pada pelanggan ini, bermula dengan aktiviti paling terkini. Untuk maklumat lanjut, lihat [Aktiviti pelanggan](activities.md).

Pilih **kembali ke Pelanggan** untuk kembali ke halaman carian pelanggan.

## <a name="next-steps"></a>Langkah seterusnya

[Tambah lebih banyak sumber data](data-sources.md) atau [cipta segmen pelanggan](segments.md).
