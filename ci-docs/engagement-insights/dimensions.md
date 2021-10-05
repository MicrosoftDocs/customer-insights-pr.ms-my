---
title: Lihat dan cipta dimensi
description: Cara mencipta, mengedit dan memadam dimensi.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b575c5e84197d76f53a722bac60c5af928c917f9671720ede1de38c4a7478be4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034008"
---
# <a name="view-and-create-dimensions"></a>Lihat dan cipta dimensi

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensi ialah atribut peristiwa yang boleh menerangkan, menapis atau mengumpulkan data. Jika anda menjalankan promosi pemasaran di laman web, anda boleh menggunakan dimensi untuk menyusun pelawat mengikut pengguna baharu dan kembali.  

Cerapan penglibatan termasuk dimensi di luar kotak untuk sifat peristiwa. Contoh termasuk:

- Nama pelayar
- Nama halaman
- Model peranti
- Sistem pengendalian
- Negara

## <a name="view-dimensions"></a>Lihat dimensi

Dimensi adalah berdasarkan sifat peristiwa yang sedia ada. Apabila anda menggunakan kod penjejakan untuk cerapan penglibatan, dimensi sistem dicipta secara automatik.

1. Pergi ke **Data** dalam anak tetingkap navigasi kiri. 
1. Pilih **Dimensi** untuk melihat senarai semua dimensi dalam ruang kerja. 
   > [!NOTE]
   > Dimensi janaan sistem adalah baca sahaja. Anda tidak dapat mengedit dimensi tersebut. Anda hanya boleh mencipta dan mengedit dimensi tersuai.

## <a name="create-a-dimension"></a>Cipta dimensi

Selain daripada dimensi janaan sistem, persekitaran dan pentadbir ruang kerja boleh mencipta dimensi tersuai. Dimensi tersuai adalah berdasarkan sifat lalai peristiwa asas atau ia boleh menggunakan [sifat tersuai peristiwa](advanced-SDK-implementation.md).

1. Pergi ke **Data** > **Dimensi**.
1. Pilih **Tambah dimensi**.

   :::image type="content" source="media/add-dimension.png" alt-text="Tambah dimensi pada peristiwa.":::

1. Dalam anak tetingkap **Cipta dimensi**, pilih sifat untuk menempatkan dimensi. Senarai sifat akan menunjukkan semua sifat dalam ruang kerja yang tidak ditugaskan pada dimensi.
1. Masukkan nama dalam kotak **Nama paparan**. Anda boleh menambahkan perihalan secara pilihan.
1. Pilih **Cipta** untuk menyimpan dimensi. Masa sehingga satu minit mungkin diperlukan sebelum anda boleh menggunakan dimensi dalam [laporan](custom-reports.md) atau [segmen tersuai](segments.md). 

## <a name="edit-a-dimension"></a>Edit dimensi

Anda boleh menukar nama dan perihalan dimensi.

1. Pergi ke **Data** > **Dimensi**.
1. Pilih dimensi yang ingin anda padam.
1. Dalam anak tetingkap **Edit dimensi**, kemas kini dimensi.
1. Pilih **Gunakan** untuk menyimpan perubahan anda.

## <a name="delete-a-dimension"></a>Padam dimensi

Anda hanya boleh memadamkan dimensi yang dicipta oleh pengguna, tetapi anda tidak boleh mengalih keluar dimensi sistem.

Memadamkan dimensi adalah kekal. Laporan dan segmen yang menggunakan dimensi yang dipadam tidak lagi berfungsi. 

1. Pergi ke **Data** > **Dimensi**.
1. Pilih dimensi yang ingin anda padam.
1. Dalam anak tetingkap **Edit dimensi**, pilih **Padam dimensi**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Padamkan dimensi pada peristiwa.":::

1. Masukkan **SAHKAN PADAM** (dengan semua huruf besar) untuk mengesahkan pemadaman. 
1. Pilih **Padam**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]