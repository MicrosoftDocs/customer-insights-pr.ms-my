---
title: Tambah kod pada tapak web anda
description: Cara menambahkan cebisan kod untuk menangkap peristiwa Dynamics 365 Customer Insights pada tapak web anda.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558904"
---
# <a name="install-the-web-sdk-on-a-website"></a>Pasang web SDK pada tapak web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Artikel ini menerangkan bagaimana pentadbir memasang kit alat pembangunan perisian web (SDK) pada tapak web. Anda akan mula melihat peristiwa dalam ruang kerja anda sejurus selepas memainkan peranan tapak web anda. Untuk mendapatkan maklumat lanjut, lihat [Urus ruang kerja dan persekitaran](manage-environments-workspaces.md). Untuk menangkap peristiwa dalam aplikasi mudah alih, lihat [Gambaran keseluruhan sumber pembangun](developer-resources.md).


### <a name="prerequisites"></a>Prasyarat

* Anda mesti mempunyai keizinan pentadbir untuk ruang kerja untuk menyimpan data.
* Tapak web atau projek anda mesti dihoskan dalam talian untuk menghantar data aktiviti. Data yang dihantar daripada fail tempatan tidak akan diterima oleh pelayan.


## <a name="add-web-sdk-to-your-website"></a>Tambah SDK web ke tapak web anda

Pergi ke **Pentadbir** > **Ruang Kerja**  dan kemudian pilih **Panduan pemasangan**. Terdapat dua pilihan untuk memasang SDK web. Yang pertama adalah untuk menggunakan pautan muat turun dan yang kedua adalah untuk memasang pakej pengurus pakej nod (NPM).

### <a name="option-1-using-the-download-link"></a>Pilihan 1: Menggunakan pautan muat turun

1. Pilih **Salin kod** untuk menyalin cebisan kod. Secara lalai, kunci pengingesan untuk ruang kerja anda dibenamkan dalam cebisan kod.
  :::image type="content" source="media/copy-code.png" alt-text="Syot layar halaman cebisan kod.":::

1. Tambah kod yang disalin ke tapak web anda, berhampiran <head> tag dan sebelum sebarang skrip atau tag CSS lain.
1. Terbitkan tapak web anda yang dikemas kini dan tunggu beberapa minit untuk merekodkan trafik web masuk.
1. Untuk melihat data anda, pilih ruang kerja anda daripada penukar ruang kerja dalam anak tetingkap navigasi. Kemudian, pilih salah satu daripada laporan dalam bahagian **Temui**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Pilihan 2: Menggunakan pakej NPM (disyorkan untuk Aplikasi web berasaskan JavaScript)

1. Pergi ke [tapak web NPM](https://www.npmjs.com/package/engagementinsights-web) kami dan ikut arahan untuk memasang dan sediakan NPM SDK web.
1. Terbitkan tapak web anda yang dikemas kini dan tunggu beberapa minit untuk merekodkan trafik web masuk.
1. Untuk melihat data anda, pilih ruang kerja anda daripada penukar ruang kerja dalam anak tetingkap navigasi. Kemudian, pilih salah satu daripada laporan dalam bahagian **Temui**.

## <a name="configuration-options"></a>Pilihan konfigurasi

Anda boleh mengubah pilihan konfigurasi yang berikut dalam cebisan kod:

- **ingestionKey**: Kunci pengingesan yang digunakan untuk menghantar peristiwa ke ruang kerja anda. Anda boleh menukar kunci penginjesan untuk menghantar peristiwa ke ruang kerja yang lain. Kunci pengingesan adalah unik untuk setiap ruang kerja.
- **autoCapture**: Menentukan sama ada pandangan halaman dan interaksi dengan tapak web direkodkan. Ia mempunyai dua pilihan:
    - **pandangan**: Ditetapkan kepada *benar* untuk merekodkan pandangan laman. Pandangan halaman direkodkan sebagai *Lihat* [peristiwa](glossary.md#event), jenis [peristiwa asas](glossary.md#base-event).
    - **klik**: Ditetapkan kepada *benar* untuk merekodkan interaksi pelawat pada tapak web. Interaksi direkodkan sebagai *Tindakan* [peristiwa](glossary.md#event), jenis [peristiwa asas](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
