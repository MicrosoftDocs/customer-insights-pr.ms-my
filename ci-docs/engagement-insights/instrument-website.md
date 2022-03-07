---
title: Tambah kod pada tapak web anda
description: Cara menambahkan cebisan kod untuk merekodkan peristiwa pada tapak web anda.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035105"
---
# <a name="install-the-code-snippet-on-a-website"></a>Pasang cebisan kod pada tapak web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Artikel ini menerangkan cara pentadbir memasang cebisan kod pada tapak web. Anda akan mula melihat peristiwa dalam ruang kerja anda sejurus selepas menambahkan skrip pada tapak web anda. Untuk mendapatkan maklumat lanjut, lihat [Urus ruang kerja dan persekitaran](manage-environments-workspaces.md). Untuk menangkap peristiwa dalam aplikasi mudah alih, lihat [Gambaran keseluruhan sumber pembangun](developer-resources.md).


### <a name="prerequisites"></a>Prasyarat

* Anda mesti mempunyai keizinan pentadbir untuk ruang kerja untuk menyimpan data.
* Tapak web atau projek anda mesti dihoskan dalam talian untuk menghantar data aktiviti. Data yang dihantar daripada fail tempatan tidak akan diterima oleh pelayan.


## <a name="add-code-to-your-website"></a>Tambah kod pada tapak web anda
1.  Pergi ke **Pentadbir** > **Ruang Kerja**  dan kemudian pilih **Panduan pemasangan**.
1. Pilih **Salin kod** untuk menyalin cebisan kod. Secara lalai, kunci pengingesan untuk ruang kerja anda dibenamkan dalam cebisan kod.
:::image type="content" source="media/copy-code.png" alt-text="Syot layar halaman cebisan kod.":::
3. Tambah cebisan kod yang disalin pada tapak web anda, berhampiran <head> tag dan sebelum sebarang skrip atau tag CSS lain.
4.  Terbitkan tapak web anda yang dikemas kini dan tunggu beberapa minit untuk merekodkan trafik web masuk.
5.  Untuk melihat data anda, pilih ruang kerja anda daripada penukar ruang kerja dalam anak tetingkap navigasi. Kemudian, pilih salah satu daripada laporan dalam bahagian **Temui**.

## <a name="configuration-options"></a>Pilihan konfigurasi

Anda boleh mengubah pilihan konfigurasi yang berikut dalam cebisan kod:

- **ingestionKey**: Kunci pengingesan yang digunakan untuk menghantar peristiwa ke ruang kerja anda. Anda boleh menukar kunci penginjesan untuk menghantar peristiwa ke ruang kerja yang lain. Kunci pengingesan adalah unik untuk setiap ruang kerja. 
- **autoCapture**: Menentukan sama ada pandangan halaman dan interaksi dengan tapak web direkodkan. Ia mempunyai dua pilihan:
    - **pandangan**: Ditetapkan kepada *benar* untuk merekodkan pandangan laman. Pandangan halaman direkodkan sebagai *Lihat* [peristiwa](glossary.md#event), jenis [peristiwa asas](glossary.md#base-event).
    - **klik**: Ditetapkan kepada *benar* untuk merekodkan interaksi pelawat pada tapak web. Interaksi direkodkan sebagai *Tindakan* [peristiwa](glossary.md#event), jenis [peristiwa asas](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
