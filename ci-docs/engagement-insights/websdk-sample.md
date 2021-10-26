---
title: Jalankan sampel SDK web
description: Ketahui cara memperibadikan dan menjalankan sampel SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606246"
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
