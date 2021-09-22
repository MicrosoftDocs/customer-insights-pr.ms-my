---
title: Jalankan sampel SDK web
description: Ketahui cara memperibadikan dan menjalankan sampel SDK web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036614"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Jalankan sampel SDK web untuk keupayaan cerapan penglibatan Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Keupayaan cerapan penglibatan pustaka SDK web ialah pustaka JavaScript dengan kod sampel yang boleh anda gunakan pada tapak web anda.

## <a name="prerequisites"></a>Prasyarat

- Pasang [Kod Visual Studio](https://code.visualstudio.com/).
- [Pasang sambungan Pelayan Langsung](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) dalam Kod Visual Studio dan membiasakan diri dengan cara untuk menjalankan Pelayan Langsung.
- Anda mesti mempunyai [kunci pengingesan](instrument-website.md).

## <a name="run-sample"></a>Jalankan sampel

1. [Muat turun sampel SDK web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Nyahzip fail dimampatkan `ei_websdk_sample.zip`.

1. Buka folder nyahzip dalam Kod Visual Studio.

1. Dalam fail `ei_websdk_sample.html`, gantikan rentetan "INGESTION_KEY" dengan kunci pengingesan anda daripada portal keupayaan cerapan penglibatan dan rentetan "NAMA" dengan nama global yang anda mahu SDK untuk diunsurkan. Pastikan anda menggantikan semua kejadian.

1. Buka fail `ei_websdk_sample.html` menggunakan Pelayan Langsung dalam Kod Visual Studio dengan memilih **Langsungkan** daripada bar status.

1. Apabila membuka halaman, peristiwa pandangan hendaklah dihantar secara automatik. Mengklik pada sebarang butang pada halaman akan menghantar peristiwa tindakan. Butang **Jejak Peristiwa** juga akan menghantar peristiwa tersuai. Memilih butang **Pergi ke Bing** akan menghantar peristiwa tindakan sebelum menavigasi ke tapak web Bing.

1. Lihat peristiwa yang mengalir apabila anda menavigasi ke ruang kerja anda. Ruang kerja ini dikaitkan dengan kunci pengingesan yang dimasukkan dalam langkah 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]