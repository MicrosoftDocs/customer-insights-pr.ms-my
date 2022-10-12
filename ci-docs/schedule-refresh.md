---
title: Menjadualkan segar semula sistem
description: Jadualkan masa apabila sistem perlu disegar semula
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610339"
---
# <a name="schedule-system-refresh"></a>Menjadualkan segar semula sistem

Menjadualkan segar semula automatik bagi semua sumber data tertelan [anda](data-sources.md). Muat semula automatik membantu memastikan bahawa kemas kini daripada sumber data anda ditunjukkan dalam profil pelanggan anda yang disatukan.

> [!NOTE]
> Power Query sumber data yang diuruskan oleh anda menyegar semula jadual mereka sendiri. Untuk menjadualkan segar semula sumber data ini Power Query, konfigurasikan seting segar semula pada sumber data khusus daripada **halaman Sumber data**. Jajarkan pemasaan dengan jadual segar semula data hulu supaya penyegaran semula tidak semua berlaku sekaligus.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Seting segar semula aliran data.":::

## <a name="set-system-refresh-schedule"></a>Tetapkan jadual segar semula sistem

1. Pergi ke **Sistem** > **Pentadbir** dan pilih tab **Jadual**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Jadualkan tab segar semula daripada halaman Sistem.":::

1. Keadaan lalai untuk segar semula dijadualkan adalah **Tutup**. Untuk mendayakan segar semula berjadual, ubah togel pada bahagian atas skrin ke **Hidup**.

1. Pilih antara segar semula **Mingguan** (lalai) dan **Harian**. Jika anda berhasrat untuk menjadualkan segar semula secara mingguan, pilih satu atau lebih hari untuk menjalankan segar semula.

1. Tetapkan **Zon waktu** anda, kemudian gunakan juntai bawah **Masa** untuk menetapkan masa muat semula anda. Jika anda ingin menjadualkan berbilang segar semula dalam satu hari, pilih **Tambah masa lagi**. Anda boleh menambah sehingga empat segar semula.

1. Pilih **Simpan** untuk menggunakan perubahan anda.

[!INCLUDE [footer-include](includes/footer-banner.md)]
