---
title: Tugas dikongsi untuk senario ramalan
description: Ketahui cara mengurus, menyelesaikan masalah dan memperhalus ramalan.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 8c5d8b0395452c8da1631f09cffeddfc811e6d29
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230803"
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

### <a name="view-the-input-data-usability-report"></a>Lihat laporan kebolehgunaan data input

Selepas model luar kotak telah melengkapkan langkah latihan, lihat laporan:
- Pilih elips di sebelah nama model dan pilih **Laporan kebolehgunaan data input**.
- Pilih status model pilih **Lihat laporan kebolehgunaan data input** dalam anak tetingkap sisi.
- Memilih salah satu model dalam senarai dan pilih **Laporan kebolehgunaan data input** dalam bar perintah.
- Buka halaman hasil model dan pilih **Laporan kebolehgunaan data input** dalam bar perintah.

### <a name="information-in-the-input-data-usability-report"></a>Maklumat dalam laporan kebolehgunaan data input

Lajur berikut dalam laporan mengandungi maklumat yang berguna untuk meningkatkan data untuk model.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kebolehgunaan data input yang menunjukkan jadual dengan ralat, amaran dan pengesyoran.":::

- **Nama:** Nama perihalan ralat, amaran atau cadangan.
- **Langkah:** Fasa model, kereta api atau skor, maklumat merujuk kepada.
- **Keadaan:** Keterukan maklumat (ralat, amaran, cadangan).
- **Nama lajur:** Lajur dalam entiti yang perlu diubah suai untuk meningkatkan prestasi model.
- **Nama entiti:** Nama entiti yang perlu diubah suai untuk meningkatkan prestasi model.
- **Butiran:** Butiran tentang ralat, amaran atau pengesyoran.

## <a name="refresh-a-prediction"></a>Segar semula ramalan

Ramalan akan menyegar semula secara automatik pada [jadual yang sama data anda menyegar semula](system.md#schedule-tab) seperti yang dikonfigurasikan dalam tetapan. Anda boleh juga menyegarkannya semula secara manual.

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu segar semula.

1. Pilih **Segar Semula**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Padamkan ramalan

Memadamkan ramalan juga mengalih keluar entiti outputnya.

1. Pergi ke **Kecerdasan** > **Ramalan** dan pilih tab **Ramalan saya**.

1. Pilih elipsis menegak di sebelah ramalan yang anda mahu padamkan.

1. Pilih **Padam**.
