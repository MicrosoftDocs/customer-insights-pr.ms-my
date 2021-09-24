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
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483691"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Had perkhidmatan dalam keupayaan Customer Insights

Artikel ini menerangkan had terbina dalam pada perkhidmatan Customer Insights yang direka untuk memastikan kebolehpercayaan dan kestabilan perkhidmatan. Sebarang permintaan perubahan boleh dibuat melalui [Forum idea](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Cerapan khalayak

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Had perkhidmatan dalam keupayaan cerapan khalayak Dynamics 365 Customer Insights

| Kawasan  | Had  | Nota |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmen dan ukuran | 100 segmen atau langkah. | Jumlah gabungan [segmen](audience-insights/segments.md) dan [langkah](audience-insights/measures.md) aktif tidak boleh melebihi 100.  |
| Hubungan | 20 tahap kedalaman pada perhubungan dalam laluan entiti. | Apabila mencipta [segmen](audience-insights/segments.md) atau [ukuran](audience-insights/measures.md) menggunakan antara muka pembina, laluan entiti boleh mempunyai sehingga 20 lompatan perhubungan antara entiti permulaan dengan entiti sasaran.  |


## <a name="engagement-insights"></a>Cerapan penglibatan

### <a name="workspace-and-event-quotas"></a>Kuota ruang kerja dan peristiwa

Cerapan penglibatan adalah aplikasi berskala tinggi yang boleh menyokong jutaan peristiwa setiap saat. Semasa pratonton awam, peristiwa mempunyai ambang volum. Terdapat juga had kepada bilangan ruang kerja dalam organisasi.

### <a name="engagement-insights-limits"></a>Had cerapan penglibatan

- Volum peristiwa maksimum bagi setiap ruang kerja = 100 peristiwa setiap saat

- Bilangan maksimum ruang kerja setiap organisasi = 100

Apabila peristiwa melebihi ambang, ia boleh menyebabkan kehilangan data dalam laporan berdasarkan pada peristiwa itu. Anda boleh [menghubungi sokongan](https://go.microsoft.com/fwlink/?linkid=2145734) untuk meminta peningkatan volum sebelum anda melebihi had. Kami akan bekerja dengan anda untuk menentukan keperluan anda bagi peningkatan volum dan menyokong permintaan anda.


[!INCLUDE[footer-include](includes/footer-banner.md)]