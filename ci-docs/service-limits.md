---
title: Had perkhidmatan dalam Dynamics 365 Customer Insights
description: Fahami had dan sekatan.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791992"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Had perkhidmatan dalam keupayaan Customer Insights

Artikel ini menerangkan had terbina dalam pada perkhidmatan Customer Insights yang direka untuk memastikan kebolehpercayaan dan kestabilan perkhidmatan. Sebarang permintaan perubahan boleh dibuat melalui [Forum idea](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Cerapan khalayak

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Had perkhidmatan dalam keupayaan wawasan khalayak Dynamics 365 Customer Insights

| Kawasan  | Had  | Nota |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen, langkah dan ramalan | 300  | Jumlah bilangan [segmen](audience-insights/segments.md), [ukuran, dan ramalan digabungkan tidak boleh melebihi](audience-insights/measures.md)[...](audience-insights/predictions.md) 300.  |
| Hubungan | 20 tahap kedalaman pada perhubungan dalam laluan entiti. | Apabila mencipta [segmen](audience-insights/segments.md) atau [ukuran](audience-insights/measures.md) menggunakan antara muka pembina, laluan entiti boleh mempunyai sehingga 20 lompatan perhubungan antara entiti permulaan dengan entiti sasaran.  |


## <a name="engagement-insights"></a>Cerapan penglibatan

### <a name="workspace-and-event-quotas"></a>Kuota ruang kerja dan peristiwa

Cerapan penglibatan adalah aplikasi berskala tinggi yang boleh menyokong jutaan peristiwa setiap saat. Semasa pratonton awam, peristiwa mempunyai ambang volum. Terdapat juga had kepada bilangan ruang kerja dalam organisasi.

### <a name="engagement-insights-limits"></a>Had cerapan penglibatan

- Volum peristiwa maksimum bagi setiap ruang kerja = 100 peristiwa setiap saat

- Bilangan maksimum ruang kerja setiap organisasi = 100

Apabila peristiwa melebihi ambang, ia boleh menyebabkan kehilangan data dalam laporan berdasarkan pada peristiwa itu. Anda boleh [menghubungi sokongan](https://go.microsoft.com/fwlink/?linkid=2145734) untuk meminta peningkatan volum sebelum anda melebihi had. Kami akan bekerja dengan anda untuk menentukan keperluan anda bagi peningkatan volum dan menyokong permintaan anda.


[!INCLUDE[footer-include](includes/footer-banner.md)]
