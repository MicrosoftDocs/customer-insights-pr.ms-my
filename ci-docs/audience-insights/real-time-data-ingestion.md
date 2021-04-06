---
title: Pengingesan data masa nyata dan pengehadan
description: Maklumat umum mengenai keupayaan masa nyata dalam wawasan khalayak.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598580"
---
# <a name="real-time-data-ingestion-preview"></a>Pengingesan data masa nyata (pratonton)

Kefungsian hampir dengan masa nyata membolehkan anda melihat, dalam sekelip mata, interaksi terkini yang pelanggan anda telah lakukan dengan produk atau perkhidmatan anda.

[Menyegarkan semula yang dijadualkan](system.md#schedule-tab) termasuk bilangan rekod yang besar dan beberapa operasi kompleks. Pertama, data ditarik daripada sumber data. Seterusnya, data disatukan dan kemudian diperkaya dengan maklumat tambahan. Setiap jalanan proses ini boleh mengambil masa berminit-minit hingga berjam-jam.

Kefungsian masa nyata menyediakan data dengan serta-merta untuk penggunaan, sehingga segar semula dijadualkan seterusnya menarik data ini daripada sumber data.

Kemas kini masa nyata mempunyai masa tamat tempoh dan selepas masa ini, ia tidak lagi menulis ganti nilai daripada sumber data:

- Kemas kini profil akan disimpan selama 4 jam
- Aktiviti akan disimpan selama 30 hari

Nilai ini ialah parameter panggilan API yang boleh anda ubah. Ia bertujuan untuk memastikan data sumber anda mengekalkan sumber kepercayaan anda. Jika anda mahu kemas kini masa nyata dimasukkan lebih lama, anda perlu menambahnya ke sumber data supaya ia akan ditarik semasa segar semula yang dijadualkan seterusnya.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Kemas kini masa nyata medan profil pelanggan yang disatukan

Profil yang dikemas kini akan ditunjukkan dalam pandangan kad pelanggan atau sebarang visualisasi lain dalam tempoh masa beberapa saat.

Oleh kerana operasi masa nyata berlaku selepas penyatuan data telah berlaku, ia hanya digunakan pada profil pelanggan yang disatukan. Oleh sebab itu, perubahan profil masa nyata tidak akan mengemas kini langkah, keahlian bahagian atau pengayaan.

### <a name="limitations"></a>Had-had

- Profil pelanggan boleh dikemas kini tetapi tidak dicipta atau dipadamkan.
- Mengeksport kemas kini masa nyata kepada sistem luaran, seperti Power BI, tidak boleh dilakukan pada masa ini.

## <a name="real-time-creation-of-activities"></a>Penciptaan aktiviti masa nyata

API masa nyata membolehkan anda menerbitkan aktiviti baharu daripada sistem sumber anda (rekod sumber individu) kepada profil pelanggan disatukan. Aktiviti baharu akan tersedia sebagai aktiviti yang disatukan dalam garis masa profil pelanggan yang disatukan dalam sekelip mata. Anda boleh melihat garis masa dalam pandangan kad pelanggan atau sebarang integrasi garis masa lain yang anda konfigurasikan.

> [!NOTE]
>
> - Aktiviti adalah tidak berubah. Ia tidak berubah setelah dicipta.
> - Pada masa ini, bahagian dan langkah tidak akan dikemas kini berdasarkan aktiviti baharu.
> - Aktiviti yang ditambahkan hanya melalui API masa nyata bukan sebahagian daripada eksport dan tidak akan ditunjukkan dalam Power BI.

Terdapat dua cara untuk sambung ke API masa nyata:

- [secara tidak langsung](#connect-via-the-dynamics-365-customer-insights-connector), menggunakan [penyambung Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [secara langsung](#connect-directly-to-the-real-time-api), dengan kod

Kedua-dua cara berkongsi prasyarat yang berikut:

- Persekitaran Customer Insights
- Profil pelanggan yang disatukan
- Aktiviti dikonfigurasikan dan berjalan
- Keizinan Penyumbang atau Pentadbir untuk mengesahkan akaun anda

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Sambungkan melalui penyambung Dynamics 365 Customer Insights

API masa nyata boleh menginges data daripada sambungan Power Platform yang khusus, [penyambung Dynamics 365 Customer Insights](/connectors/customerinsights/), tanpa perlu menulis dan mengatur letak sebarang kod.    
Penyambung boleh melakukan tindakan masa nyata yang sama seperti API. Anda memerlukan lesen yang sah untuk penyambung premium. Untuk maklumat lanjut, lihat [Soalan Lazim pelesenan Power Apps dan Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps dan/atau Power Automate](/connectors/)
- Azure [Aplikasi Logik](/azure/connectors/apis-list)

Untuk butiran tentang mencipta aliran, lihat [dokumentasi Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Sambungkan secara langsung kepada API masa nyata

Anda boleh menggunakan keupayaan masa nyata dengan membina talian paip anda sendiri dan menyambung secara langsung ke API masa nyata.    
Anda boleh menyiarkan aktiviti dalam format sistem sumber anda atau dalam format UnifiedActivity. Dapatkan format dengan membuat panggilan API kepada /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Butiran API ini, termasuk parameter dan respons, boleh didapati dalam seksyen **EntityData** pada [Rujukan Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Untuk mendapatkan maklumat lanjut, lihat [Kerja dengan Customer Insights API](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Memahami pengguna masa nyata anda dengan telemetri

Dapatkan gambaran keseluruhan jumlah permintaan kepada API masa nyata dan maklumat mengenai isu yang mungkin dihadapi oleh sistem. Anda boleh [mengakses telemetri masa nyata](system.md#api-usage-tab). 


[!INCLUDE[footer-include](../includes/footer-banner.md)]