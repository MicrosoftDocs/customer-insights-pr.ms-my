---
title: Tugas dikongsi untuk senario ramalan
description: Ketahui cara mengurus, menyelesaikan masalah dan memperhalus ramalan.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095734"
---
# <a name="manage-predictions"></a>Urus ramalan

Artikel ini membincangkan beberapa tugas yang paling banyak senario ramalan berkongsi.

## <a name="troubleshoot-a-failed-prediction"></a>Selesaikan ramalan yang gagal

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak bersebelahan dengan ramalan yang anda mahu lihat log ralatnya.

1. Pilih **Log**.

1. Semak semula semua ralat. Terdapat beberapa jenis ralat yang boleh berlaku dan ia menghuraikan keadaan yang menyebabkan ralat tersebut. Contohnya, ralat bahawa data tidak mencukupi untuk meramal secara tepat pada lazimnya diselesaikan dengan memuatkan data tambahan ke dalam Customer Insights.

## <a name="input-data-usability-report"></a>Laporan kebolehgunaan data input

Laporan kebolehgunaan data input menyediakan pandangan ralat disatukan dan amaran bahawa ramalan luar kotak anda mungkin menjana. Ia juga memberi pengesyoran cara meningkatkan prestasi model.

Laporan tersedia selepas model selesai proses latihan. Ia dicipta untuk setiap model secara berasingan, tanpa mengira jika ia berjaya sepenuhnya atau tidak.

> [!NOTE]
> Pada masa ini, ciri ini hanya berfungsi untuk model Pulangan Transaksi.

### <a name="view-the-input-data-usability-report"></a>Lihat laporan kebolehgunaan data input

Selepas model luar kotak telah melengkapkan langkah latihan, lihat laporan:
- Pilih elips di sebelah nama model dan pilih **Laporan kebolehgunaan data input**.
- Pilih status model pilih **Lihat laporan kebolehgunaan data input** dalam anak tetingkap sisi.
- Memilih salah satu model dalam senarai dan pilih **Laporan kebolehgunaan data input** dalam bar perintah.
- Buka halaman hasil model dan pilih **Laporan kebolehgunaan data input** dalam bar perintah.

### <a name="information-in-the-input-data-usability-report"></a>Maklumat dalam laporan kebolehgunaan data input

Lajur berikut dalam laporan mengandungi maklumat yang berguna untuk meningkatkan data untuk model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kebolehgunaan data input yang menunjukkan jadual dengan ralat, amaran dan pengesyoran.":::

- Nama: Nama deskriptif ralat, amaran atau pengesyoran.
- Langkah: Fasa model, latihan atau skor yang dirujuk maklumat.
- Keadaan: Keterukan maklumat (ralat, amaran, pengesyoran).
- Nama lajur: Lajur dalam entiti yang perlu diubah suai untuk meningkatkan prestasi model.
- Nama entiti: Nama entiti yang perlu diubah suai untuk meningkatkan prestasi model.
- Butiran: Butiran tentang ralat, amaran atau pengesyoran.

## <a name="refresh-a-prediction"></a>Segar semula ramalan

Ramalan akan menyegar semula secara automatik pada [jadual yang sama data anda menyegar semula](system.md#schedule-tab) seperti yang dikonfigurasikan dalam tetapan. Anda boleh juga menyegarkannya semula secara manual.

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu segar semula.

1. Pilih **Segar Semula**.

## <a name="delete-a-prediction"></a>Padamkan ramalan

Memadamkan ramalan juga mengalih keluar entiti outputnya.

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu padamkan.

1. Pilih **Padam**.
