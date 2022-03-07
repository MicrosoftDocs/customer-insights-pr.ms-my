---
title: Cipta dan ubah suai peristiwa
description: Cara untuk mencipta dan ubah suai peristiwa.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228214"
---
# <a name="create-and-modify-events"></a>Cipta dan ubah suai peristiwa

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Peristiwa ialah data yang mewakili tingkah laku pengguna seperti aktiviti pada tapak web.

- Peristiwa *asas* merekod apabila pengguna melihat halaman (pandangan peristiwa) atau berinteraksi dengan kandungan (peristiwa tindakan).
- Peristiwa *diperhalus* adalah pandangan maya bagi peristiwa asas. Anda mentakrifkan peristiwa diperhalus dengan mengalih keluar dan menambah sifat atau dengan menapis peristiwa berdasarkan pada nilai sifat.

## <a name="prerequisites"></a>Prasyarat

Untuk melihat peristiwa, data tapak web anda perlu disambungkan terlebih dahulu kepada cerapan penglibatan dengan cebisan kod. Untuk mendapatkan maklumat lanjut, lihat [Pasang SDK web pada tapak web](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Sambungkan data anda terlebih dahulu.":::

## <a name="create-refined-events"></a>Cipta peristiwa diperhalus

Gunakan peristiwa diperhalus untuk mengurangkan skop peristiwa asas bagi [eksport](export-events.md) atau untuk mengalih keluar sifat yang tidak diperlukan bagi pendedahan.

> [!NOTE]
> Sebaik sahaja anda menambahkan SDK web ke tapak web anda, anda boleh melihat peristiwa asas anda dan mencipta peristiwa yang diperhalus. 

Untuk melihat peristiwa asas anda:

1. Pergi ke **Data** dalam anak tetingkap navigasi kiri.

1. Pilih **Peristiwa** untuk melihat senarai semua peristiwa dalam ruang kerja.

    :::image type="content" source="media/data-events.png" alt-text="Lihat peristiwa.":::

Untuk mencipta acara yang diperhalus daripada peristiwa asas: 

1. Pergi ke **Data** > **Peristiwa** dan pilih **+ Peristiwa baharu** di bahagian atas skrin.

1. Dalam dialog **Peristiwa baharu**, pilih **Cipta peristiwa diperhalus** dan kemudian pilih **Seterusnya**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Wizard peristiwa baharu.":::
     
1. Dalam dialog **Peristiwa baharu**, masukkan maklumat berikut:

   - Pilih peristiwa daripada juntai bawah **Peristiwa asas**.
   - Masukkan nama dalam kotak **Nama paparan peristiwa diperhalus**.
   - Secara pilihan, kemas kini **Nama actual** yang dicadangkan tanpa menggunakan ruang.

1. Pilih **Cipta** untuk menggunakan tetapan anda.

Acara yang diperhalus kini muncul dalam senarai **Peristiwa** anda.

### <a name="edit-event-name"></a>Edit nama peristiwa

Anda boleh mengubah nama dan sifat asas atau peristiwa yang diperhalus.

1. Pergi ke **Data** > **Peristiwa**. 

1. Pilih **Lagi [...]** untuk peristiwa dan pilih **Edit nama**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Pilihan untuk mencipta peristiwa diperhalus.":::

3. Kemas kini nama peristiwa dan pilih **Namakan semula**.

### <a name="view-the-details-of-a-refined-event"></a>Lihat butiran peristiwa yang telah diperhalus:

1. Dalam senarai **Peristiwa**, pilih asas anda atau acara yang diperhalus. 

1. Pilih **Tambah dan alih keluar sifat** di bahagian atas skrin untuk membuka anak tetingkap **Edit sifat**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Tambah dan alih keluar sifat.":::

1. Gunakan kotak semak untuk memilih sifat yang anda mahu tunjukkan dan yang anda mahu sembunyikan. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Edit sifat untuk peristiwa diperhalus.":::

1. Pilih **Sahkan** untuk menggunakan pilihan anda dan kemudian pilih **Simpan**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Edit sifat yang dipilih untuk peristiwa yang telah diperhalus

1. Pergi ke **Data** > **Peristiwa** dan pilih peristiwa diperhalus untuk membuka pandangan terperinci.
1. Pilih **Tambah dan alih keluar sifat**. 
1. Edit pemilihan kotak semak.
1. Pilih **Sahkan** dan kemudian **Simpan** untuk menggunakan perubahan.

Untuk maklumat tentang peristiwa mengeksport, lihat [Eksport peristiwa](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
