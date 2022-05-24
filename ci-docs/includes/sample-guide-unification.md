---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755555"
---
Selepas menelan data, mulakan proses penyatuan data untuk membuat profil pelanggan yang bersatu. Untuk mendapatkan maklumat lanjut, lihat [Penyatuan data](../data-unification.md).

### <a name="select-source-fields"></a>Pilih medan sumber

1. Selepas menginges data, petakan kenalan daripada data e-Dagang dan Kesetiaan kepada jenis data umum. Pergi ke **Data** > **Unify**.

1. Pilih entiti yang mewakili profil pelanggan – **eCommerceContacts** dan **loyCustomers**.

   ![menyatukan sumber data e-Dagang dan kesetiaan.](../media/unify-ecommerce-loyalty.png)

1. Pilih **ContactId** sebagai kunci utama untuk **eCommerceContacts** dan **LoyaltyID** sebagai kunci utama untuk **loyCustomers**.

1. Pilih **Seterusnya**. Langkau rekod pendua dan pilih **Berikut**.

### <a name="match-conditions"></a>Keadaan padanan

1. Pilih **eCommerceContacts: eCommerce** sebagai entiti utama dan sertakan semua rekod.

1. Pilih **loyCustomers: LoyaltyScheme** dan sertakan semua rekod.

1. Tambah peraturan:
   - Pilih **FullName** untuk kedua-dua eCommerceContacts dan loyCustomers.
   - Pilih **Jenis (Telefon, Nama, Alamat, ...)** untuk **Menormalkan**.
   - Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.
   - Masukkan **FullName, E-mel** untuk nama.

1. Tambah syarat kedua untuk alamat e-mel:
   - Pilih **E-mel** untuk kedua-dua eCommerceContacts dan loyCustomers.
   - Biarkan Menormalkan kosong.
   - Tetapkan **Tahap Kepersisan** : **Asas** dan **Nilai** : **Tinggi**.

   ![Menyatukan peraturan padanan untuk nama dan e-mel.](../media/unify-match-rule.png)

1. Pilih **Selesai**.

1. Pilih **Seterusnya**.

### <a name="unify-fields"></a>Menyatukan medan

1. Namakan semula **ContactId** untuk **entiti loyCustomers** kepada **ContactIdLOYALTY** untuk membezakannya daripada ID lain yang ditelan.

1. Pilih **Seterusnya** untuk menyemak dan kemudian pilih **Cipta profil** pelanggan.
