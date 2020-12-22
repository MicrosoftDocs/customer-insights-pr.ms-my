---
title: Aktiviti pelanggan
description: Tentukan aktiviti pelanggan dan lihat aktiviti tersebut dalam garis masa pelanggan.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667240"
---
# <a name="customer-activities"></a>Aktiviti pelanggan

Gabungkan aktiviti pelanggan daripada [pelbagai sumber data](data-sources.md) dalam Dynamics 365 Customer Insights untuk mencipta garis masa pelanggan yang menyenaraikan aktiviti dalam susunan kronologi. Anda boleh memasukkan garis masa dalam aplikasi penglibatan pelanggan dalam Dynamics 365 menerusi [tambahan Kad Pelanggan](customer-card-add-in.md), atau dalam papan pemuka Power BI.

## <a name="define-an-activity"></a>Takrifkan aktiviti

Sumber data anda termasuk entiti dengan data transaksi dan aktiviti daripada sumber data berbilang. Kenal pasti entiti ini dan pilih aktiviti yang anda mahu lihat pada garis masa pelanggan. Pilih entiti yang mengandungi sasaran aktiviti atau aktiviti anda.

1. Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.

1. Pilih **Tambah aktiviti**.

   > [!NOTE]
   > Entiti mesti mempunyai sekurang-kurangnya satu atribut jenis **Tarikh** yang akan dimasukkan dalam garis masa pelanggan dan anda tidak boleh menambah entiti tanpa medan **Tarikh**. Kawalan **Tambah aktiviti** dinyahdayakan jika tiada entiti sedemikian ditemui.

1. Dalam anak tetingkap **Tambah aktiviti**, tetapkan nilai untuk medan berikut:

   - **Entiti**: Pilih entiti yang mengandungi data transaksi atau aktiviti.
   - **Perkara utama**: Pilih medan yang mengenal pasti rekod secara unik. Ia tidak seharusnya mengandungi sebarang nilai duplikasi, nilai kosong atau kehilangan nilai.
   - **Cap masa**: Pilih medan yang mewakili masa mula aktiviti anda.
   - **Peristiwa**: Pilih medan yang merupakan peristiwa untuk aktiviti tersebut.
   - **Alamat web**: Pilih medan yang mewakili URL yang menyediakan maklumat tambahan tentang aktiviti ini. Contohnya, sistem transaksi yang memberi sumber untuk aktiviti ini. URL ini boleh menjadi mana-mana medan daripada sumber data atau ia boleh dibina sebagai medan baharu menggunakan perubahan Pertanyaan Kuasa. Data URL akan disimpan dalam entiti Aktiviti Disatukan, yang menjadi hiliran yang digunakan menggunakan API.
   - **Butiran**: Secara pilihan, pilih medan yang ditambah untuk butiran tambahan.
   - **Ikon**: Secara pilihan, pilih ikon yang mewakili aktiviti ini.
   - **Jenis Aktiviti**: Takrifkan rujukan jenis aktiviti untuk Model Data Biasa yang menghuraikan sebaiknya takrifan semantik aktiviti.

1. Dalam bahagian **Persediaan perhubungan**, butiran dikonfigurasi untuk menyambungkan data aktiviti anda kepada pelanggan yang berkaitan.

   > [!div class="mx-imgBorder"]
   > ![Takrifkan perhubungan entiti](media/activities-entities-define.png "Takrifkan perhubungan entiti")

    - **Medan entiti aktiviti**: Pilih medan dalam entiti aktiviti anda yang akan digunakan untuk mewujudkan perhubungan dengan entiti lain.
    - **Entiti pelanggan** : Pilih entiti pelanggan sumber berkaitan dengan entiti aktiviti anda akan berada dalam perhubungan. Anda hanya boleh mengaitkan dengan entiti pelanggan sumber yang digunakan dalam proses data penyatuan.
    - **Medan entiti pelanggan**: Medan ini menunjukkan kunci utama bagi entiti pelanggan sumber seperti yang dipilih dalam proses peta. Medan kunci utama dalam entiti pelanggan sumber ini digunakan untuk mewujudkan perhubungan dengan entiti aktiviti.
    - **Nama**: Jika perhubungan antara entiti aktiviti ini dan entiti pelanggan sumber yang terpilih telah wujud, nama perhubungan akan berada dalam mod baca sahaja. Jika tiada hubungan sedemikian wujud, perhubungan baharu akan dicipta dengan nama yang disediakan di sini.

1. Pilih **Simpan** untuk menggunakan perubahan anda.

1. Pada halaman **Aktiviti**, pilih **Jalankan**.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="edit-an-activity"></a>Edit aktiviti

1. Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.

2. Pilih entiti aktiviti yang anda mahu edit dan pilih **Edit**. Atau, anda boleh hover pada baris entiti dan pilih ikon **Edit**.

3. Klik pada ikon **Edit**.

4. Dalam anak tetingkap **Edit aktiviti**, kemas kini nilai dan pilih **Simpan**.

5. Pada halaman **Aktiviti**, pilih **Jalankan**.

## <a name="delete-an-activity"></a>Padam aktiviti

1. Dalam wawasan khalayak, pergi ke **Data** > **Aktiviti**.

2. Pilih entiti aktiviti yang anda mahu alih keluar dan pilih **Padam**. Atau, anda boleh hover pada baris entiti dan pilih ikon **Padam**. Selain itu, anda boleh memilih entiti aktiviti berbilang untuk dipadam serentak.
   > [!div class="mx-imgBorder"]
   > ![Edit atau padam perhubungan entiti](media/activities-entities-edit-delete.png "Edit atau padam perhubungan entiti.").

3. Pilih pada ikon **Padam**.

4. Sahkan pemadaman anda.
