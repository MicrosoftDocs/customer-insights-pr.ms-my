---
title: Had perkhidmatan dalam Wawasan Pelanggan
description: Memahami had dan sekatan dalam perkhidmatan SaaS Wawasan Pelanggan.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411751"
---
# <a name="service-limits-in-customer-insights"></a>Had perkhidmatan dalam Wawasan Pelanggan

 Wawasan Pelanggan mempunyai had terbina dalam yang direka untuk memastikan kebolehpercayaan dan kestabilan perkhidmatan. Sebarang permintaan perubahan boleh dibuat melalui [Forum idea](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Kawasan  | Had  | Nota |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, ukuran dan ramalan | 300  | Jumlah [segmen](segments.md), [ukuran](measures.md) dan [ramalan](predictions-overview.md) yang digabungkan tidak boleh melebihi 300.  |
| Perhubungan | 20 tahap kedalaman pada perhubungan dalam laluan entiti. | Apabila mencipta [segmen](segments.md) atau [ukuran](measures.md) menggunakan antara muka pembina, laluan entiti boleh mempunyai sehingga 20 lompatan perhubungan antara entiti permulaan dengan entiti sasaran.  |

## <a name="fair-scheduling-of-jobs"></a>Penjadualan pekerjaan yang adil

Wawasan Pelanggan ialah perkhidmatan SaaS yang menggunakan sumber Azure yang dikongsi. Pelanggan cenderung mempunyai beban kerja dengan intensiti berubah-ubah dan pada jadual yang berbeza. Untuk memastikan akses yang adil kepada sumber-sumber asas, kami memastikan proses sistem dilaksanakan dengan teratur. Contoh proses sistem ialah pekerjaan yang berkaitan dengan penyatuan data, kemas kini segmen atau pengiraan ukuran. Penjadualan yang adil melindungi anda daripada beratur untuk mendapatkan sumber jika terdapat lonjakan pekerjaan yang diminta. Pada masa yang sama, Wawasan Pelanggan tidak menjamin semua pekerjaan yang anda beratur diproses secara selari.

[!INCLUDE [footer-include](includes/footer-banner.md)]
