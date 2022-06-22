---
title: Had perkhidmatan dalam Wawasan Pelanggan
description: Fahami had dan sekatan dalam perkhidmatan Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940679"
---
# <a name="service-limits-in-customer-insights"></a>Had perkhidmatan dalam Wawasan Pelanggan

Artikel ini menerangkan had terbina dalam pada perkhidmatan Customer Insights yang direka untuk memastikan kebolehpercayaan dan kestabilan perkhidmatan. Sebarang permintaan perubahan boleh dibuat melalui [Forum idea](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Kawasan  | Had  | Nota |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, ukuran dan ramalan | 300  | Jumlah segmen [,](segments.md) ukuran [dan](measures.md) ramalan [yang](predictions.md) digabungkan tidak boleh melebihi 300.  |
| Perhubungan | 20 tahap kedalaman pada perhubungan dalam laluan entiti. | Apabila mencipta [segmen](segments.md) atau [ukuran](measures.md) menggunakan antara muka pembina, laluan entiti boleh mempunyai sehingga 20 lompatan perhubungan antara entiti permulaan dengan entiti sasaran.  |

## <a name="fair-scheduling-of-jobs"></a>Penjadualan pekerjaan yang adil

Customer Insights adalah perkhidmatan SaaS yang menggunakan sumber Azure yang dikongsi. Pelanggan cenderung mempunyai beban kerja intensiti berubah-ubah dan pada jadual yang berbeza. Untuk memastikan akses yang adil kepada sumber asas, kami memastikan proses sistem dilaksanakan dengan teratur. Contoh proses sistem adalah pekerjaan yang berkaitan dengan penyatuan data, kemas kini segmen, atau pengiraan ukuran. Penjadualan yang adil melindungi anda daripada beratur untuk mendapatkan sumber jika terdapat lonjakan pekerjaan yang diminta. Pada masa yang sama, Wawasan Pelanggan tidak menjamin semua pekerjaan yang anda beratur diproses secara selari.

[!INCLUDE [footer-include](includes/footer-banner.md)]
