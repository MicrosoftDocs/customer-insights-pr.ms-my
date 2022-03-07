---
title: Jalankan sampel SDK web
description: Ketahui cara memperibadikan dan menjalankan sampel SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225342"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Jalankan sampel SDK web untuk keupayaan cerapan penglibatan Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Keupayaan cerapan penglibatan pustaka SDK web ialah pustaka JavaScript dengan kod sampel yang boleh anda gunakan pada tapak web anda.

## <a name="prerequisites"></a>Prasyarat

- Pasang [Kod Visual Studio](https://code.visualstudio.com/).
- [Pasang sambungan Pelayan Langsung](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) dalam Kod Visual Studio dan membiasakan diri dengan cara untuk menjalankan Pelayan Langsung.
- Anda mesti mempunyai [ruang kerja cerapan penglibatan](create-workspace.md).

## <a name="run-sample"></a>Jalankan sampel

1. [Muat turun sampel SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Nyahzip fail dimampatkan `ei_websdk_sample.zip`.

1. Buka folder nyahzip dalam Kod Visual Studio.

1. Pergi ke portal cerapan penglibatan untuk ruang kerja anda. Pilih **Pentadbir** > **Ruang kerja** dan kemudian **Panduan pemasangan**. Ikuti pilihan pertama dan pilih **Salin kod** untuk menyalin cebisan kod JavaScript.

1. Dalam fail `ei_websdk_sample.html`, tampal cebisan kod yang anda baru disalin di bawah baris ini:

   - <-- TAMPAL CEBISAN KOD JAVASCRIPT DARIPADA PORTAL CERAPAN PENGLIBATAN DI SINI DI BAWAH BARIS INI -->

1. Buka fail `ei_websdk_sample.html` menggunakan Pelayan Langsung dalam Kod Visual Studio dengan memilih **Langsungkan** daripada bar status.

1. Apabila membuka halaman, peristiwa pandangan hendaklah dihantar secara automatik. Mengklik pada sebarang butang pada halaman akan menghantar peristiwa tindakan. Butang **Jejak Peristiwa** juga akan menghantar peristiwa tersuai. Memilih butang **Pergi ke Bing** akan menghantar peristiwa tindakan sebelum menavigasi ke tapak web Bing.

1. Lihat peristiwa yang mengalir apabila anda menavigasi ke ruang kerja anda. Ruang kerja ini dikaitkan dengan kunci pengingesan yang dimasukkan dalam langkah 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
