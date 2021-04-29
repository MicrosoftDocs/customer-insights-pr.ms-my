---
title: Aktiviti pelanggan
description: Tentukan aktiviti pelanggan dan lihat aktiviti tersebut dalam garis masa pelanggan.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866418"
---
# <a name="customer-activities"></a>Aktiviti pelanggan

Gabungkan aktiviti pelanggan daripada [pelbagai sumber data](data-sources.md) dalam Dynamics 365 Customer Insights untuk mencipta garis masa yang menyenaraikan aktiviti secara kronologi. Sertakan garis masa dalam aplikasi Dynamics 365 dengan penyelesaian [Kad Pelanggan tambahan](customer-card-add-in.md) atau dalam papan pemuka Power BI.

## <a name="define-an-activity"></a>Takrifkan aktiviti

Sumber data anda boleh termasuk entiti dengan data transaksi dan aktiviti daripada berbilang sumber data. Kenal pasti entiti ini dan pilih aktiviti yang anda mahu lihat pada garis masa pelanggan. Pilih entiti yang mengandungi sasaran aktiviti atau aktiviti anda.

> [!NOTE]
> Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** yang akan dimasukkan dalam garis masa pelanggan dan anda tidak boleh menambah entiti tanpa medan **Tarikh**. Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.

1. Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.

1. Pilih **Tambah aktiviti** untuk memulakan pengalaman berpandu untuk proses persediaan aktiviti.

1. Dalam langkah **Data aktiviti**, tetapkan nilai untuk medan berikut:

   - **Nama aktiviti**: Pilih nama untuk aktiviti anda.
   - **Entiti**: Pilih entiti yang mengandungi data transaksi atau aktiviti.
   - **Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Sediakan data aktiviti dengan nama, entiti dan kekunci utama.":::

1. Pilih **Seterusnya** untuk pergi ke langkah seterusnya.

1. Dalam langkah **Perhubungan**, konfigurasikan butiran untuk menyambungkan data aktiviti anda kepada pelanggan yang berkaitan. Langkah ini menggambarkan sambungan antara entiti.  

   - **Pertama**: Medan asing dalam entiti aktiviti anda yang akan digunakan untuk mewujudkan perhubungan dengan entiti lain.
   - **Kedua**: Entiti pelanggan sumber yang sepadan dengan entiti aktiviti anda yang akan berada dalam perhubungan. Anda hanya boleh dikaitkan dengan entiti pelanggan sumber yang digunakan dalam proses penyatuan data.
   - **Ketiga**: Jika perhubungan antara entiti aktiviti ini dan entiti pelanggan sumber yang dipilih telah wujud, nama perhubungan akan berada dalam mod baca sahaja. Jika tiada perhubungan sedemikian wujud, perhubungan baharu akan dicipta dengan nama yang anda berikan dalam kotak ini.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Takrifkan perhubungan entiti.":::

1. Pilih **Seterusnya** untuk pergi ke langkah seterusnya. 

1. Dalam langkah **Penyatuan aktiviti**, pilih peristiwa aktiviti dan masa mula aktiviti anda. 
   - **Medan diperlukan**
      1. **Aktiviti peristiwa**: Medan untuk peristiwa bagi aktiviti ini
      2. **Cap waktu**: Medan yang mewakili masa mula aktiviti anda.

   - **Medan pilihan**
      1. **Butiran tambahan**: Medan dengan maklumat berkaitan untuk aktiviti ini.
      2. **Ikon**: Ikon yang terbaik mewakili jenis aktiviti ini.
      3. **Alamat web**: Medan yang mengandungi URL dengan maklumat tentang aktiviti ini. Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini. URL ini boleh menjadi mana-mana medan daripada sumber data atau ia boleh dibina sebagai medan baharu menggunakan perubahan Pertanyaan Kuasa. Data URL akan disimpan dalam entiti *Aktiviti yang Disatukan* yang boleh digunakan secara hiliran menggunakan [API](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Tentukan data aktiviti pelanggan dalam entiti Aktiviti yang Disatukan.":::

1. Pilih **Seterusnya** untuk beralih ke langkah yang seterusnya. Anda boleh memilih **Selesai dan semak** untuk menyimpan aktiviti sekarang dengan jenis aktiviti yang ditetapkan kepada **Lain-lain**. 

1. Dalam langkah **Jenis Aktiviti**, pilih jenis aktiviti dan secara pilihan, pilih jika anda mahu memetakan secara semantik sebahagian daripada jenis aktiviti untuk digunakan dalam bahagian lain dalam Customer Insights. Pada masa ini, jenis aktiviti *Langganan* & *SalesOrderLine* boleh dipetakan secara semantik selepas bersetuju untuk memetakan petak. Jika jenis aktiviti tidak berkaitan dengan aktiviti baharu, anda boleh memilih *Lain-lain* atau *Cipta baharu* untuk jenis aktiviti yang tersuai.

1. Pilih **Seterusnya** untuk beralih ke langkah yang seterusnya. 

1. Dalam langkah **Semak**, sahkan pilihan anda. Anda kembali ke mana-mana langkah sebelumnya dan mengemas kini maklumat jika perlu.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Semak medan khusus untuk aktiviti.":::
   
1. Pilih **Simpan aktiviti** untuk menggunakan perubahan anda dan pilih **Selesai** untuk kembali ke **Data** > **Aktiviti**. Di sini, anda melihat aktiviti yang ditetapkan untuk ditunjukkan dalam garis masa. 

1. Pada halaman **Aktiviti**, pilih **Jalankan** untuk memproses aktiviti. 

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.


## <a name="manage-existing-activities"></a>Urus aktiviti sedia ada

Pada **Data** > **Aktiviti**, anda boleh melihat semua aktiviti yang disimpan dan menguruskannya. Setiap aktiviti diwakili oleh baris yang juga termasuk butiran mengenai sumber, entiti dan jenis aktiviti.

Tindakan berikut tersedia apabila anda memilih aktiviti. 

- **Edit**: Buka persediaan aktiviti pada langkah tinjauan. Anda boleh mengubah sebarang atau semua konfigurasi semasa daripada langkah ini. Selepas mengubah konfigurasi, pilih **Simpan aktiviti** dan kemudian pilih **Jalankan** untuk memproses perubahan.

- **Namakan semula**: Buka dialog di tempat untuk memasukkan nama lain untuk aktiviti yang dipilih. Pilih **Simpan** untuk menggunakan perubahan anda.

- **Padam**: Buka dialog untuk mengesahkan pemadaman aktiviti yang dipilih. Anda juga boleh memadamkan lebih daripada satu aktiviti sekaligus dengan memilih aktiviti dan kemudian memilih ikon padam. Pilih **Padam** untuk mengesahkan pemadaman.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
