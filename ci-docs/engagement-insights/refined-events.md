---
title: Cipta dan ubah suai peristiwa diperhalus
description: Cipta dan ubah suai peristiwa diperhalus.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034785"
---
# <a name="create-and-modify-refined-events"></a>Cipta dan ubah suai peristiwa diperhalus

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Peristiwa ialah data yang mewakili tingkah laku pengguna seperti aktiviti pada tapak web.

- Peristiwa *asas* merekod apabila pengguna melihat halaman (pandangan peristiwa) atau berinteraksi dengan kandungan (peristiwa tindakan).
- Peristiwa *diperhalus* adalah pandangan maya bagi peristiwa asas. Anda mentakrifkan peristiwa diperhalus dengan mengalih keluar dan menambah sifat atau dengan menapis peristiwa berdasarkan pada nilai sifat.

Gunakan peristiwa diperhalus untuk mengurangkan skop peristiwa asas bagi [eksport](export-events.md) atau untuk mengalih keluar sifat yang tidak diperlukan bagi pendedahan.

## <a name="create-refined-events"></a>Cipta peristiwa yang diperhalus

Terdapat tiga cara untuk mencipta peristiwa diperhalus daripada peristiwa asas. 

1. Pergi ke **Data**> **Peristiwa** dan pilih salah satu daripada pilihan berikut:
    - Pilih **Peristiwa baharu** dan kemudian pilih **Cipta peristiwa diperhalus**.
    - Pilih peristiwa asas untuk membuka pandangan terperinci dan pilih **Cipta peristiwa diperhalus** daripada menu atas.
    - Pilih **Lagi [...]** untuk membuka menu pintasan bagi peristiwa asas. Kemudian pilih **Cipta peristiwa diperhalus**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Pilihan untuk mencipta peristiwa diperhalus.":::

1. Dalam dialog **Cipta peristiwa diperhalus**, masukkan maklumat berikut:

- Pilih peristiwa daripada juntai bawah **Peristiwa asas** jika anda mencipta peristiwa baharu.
- Masukkan nama dalam kotak **Nama paparan peristiwa diperhalus**.
- Secara pilihan, kemas kini **Nama actual** yang dicadangkan tanpa menggunakan ruang.

3. Pilih **Cipta** untuk menggunakan tetapan anda.

1. Dalam pandangan terperinci bagi peristiwa diperhalus anda, pilih **Tambah dan alih keluar sifat** untuk membuka anak tetingkap **Edit sifat**. 

1. Gunakan kotak semak untuk memilih sifat yang anda mahu tunjukkan dan yang anda mahu sembunyikan. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Edit sifat untuk peristiwa diperhalus.":::

1. Pilih **Sahkan** untuk menggunakan pilihan anda.

1. Pilih **Simpan** untuk menyimpan konfigurasi.

## <a name="edit-refined-events"></a>Edit peristiwa diperhalus

Anda boleh mengubah nama dan sifat peristiwa diperhalus.

### <a name="edit-event-name"></a>Edit nama peristiwa

1. Pergi ke **Data** > **Peristiwa**. 
1. Pilih **Lagi [...]** untuk peristiwa dan pilih **Edit nama**.
1. Kemas kini nama peristiwa dan pilih **Namakan semula**.

### <a name="edit-selected-properties"></a>Edit sifat yang dipilih

1. Pergi ke **Data** > **Peristiwa** dan pilih peristiwa diperhalus untuk membuka pandangan terperinci.
1. Pilih **Tambah dan alih keluar sifat**. 
1. Edit pemilihan kotak semak.
1. Pilih **Sahkan** dan kemudian **Simpan** untuk menggunakan perubahan.

Untuk maklumat tentang peristiwa mengeksport, lihat [Eksport peristiwa](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
