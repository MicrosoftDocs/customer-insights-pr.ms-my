---
title: Had perkhidmatan dalam Dynamics 365 Customer Insights
description: Fahami had dan sekatan.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641773"
---
# <a name="service-limits-in-customer-insights"></a>Had perkhidmatan dalam Wawasan Pelanggan

Artikel ini menerangkan had terbina dalam pada perkhidmatan Customer Insights yang direka untuk memastikan kebolehpercayaan dan kestabilan perkhidmatan. Sebarang permintaan perubahan boleh dibuat melalui [Forum idea](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Kawasan  | Had  | Nota |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, ukuran dan ramalan | 300  | Jumlah segmen [,](segments.md) ukuran [dan](measures.md) ramalan [yang](predictions.md) digabungkan tidak boleh melebihi 300.  |
| Perhubungan | 20 tahap kedalaman pada perhubungan dalam laluan entiti. | Apabila mencipta [segmen](segments.md) atau [ukuran](measures.md) menggunakan antara muka pembina, laluan entiti boleh mempunyai sehingga 20 lompatan perhubungan antara entiti permulaan dengan entiti sasaran.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
