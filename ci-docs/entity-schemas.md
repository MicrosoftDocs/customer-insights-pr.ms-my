---
title: Skema entiti Customer Insights dalam Common Data Model
description: Bekerja dengan entiti dalam Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: e155f75ffbc2c1bb228bece1b3e34846df794543
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643369"
---
# <a name="entity-schemas-in-common-data-model"></a>Skim entiti dalam Model Data Lazim



[Model Data Lazim](/common-data-model/) ialah pengisytiharan spesifikasi, dan definisi bagi entiti standard yang mewakili konsep yang digunakan secara lazim dan aktiviti merentasi perniagaan dan aplikasi produktiviti. Model ini dilanjutkan kepada data pemerhatian dan analisis juga. Model Data Lazim menyediakan entiti perniagaan yang ditakrif dengan jelas, bermodul, dan boleh diperluaskan—seperti Akaun, Unit Perniagaan, Kes, Kenalan, Bakal Pelanggan, Peluang, dan Produk—serta interaksi dengan vendor, pekerja, dan pelanggan—seperti aktiviti dan perjanjian peringkat perkhidmatan. Sesiapa sahaja boleh membina dan melanjutkan definisi Model Data Biasa untuk merekodkan idea khusus perniagaan tambahan.

Model data yang dikongsi ini membolehkan aplikasi dan penyepadu data bekerjasama dengan lebih mudah dengan menyediakan definisi data yang disatukan. Model Data Lazim termasuk sistem metadata yang kaya dengan entiti standard, perhubungan, hierarki, sifat, dan banyak lagi. Ia berasal dari aplikasi Dynamics 365 dan bersumber terbuka pada GitHub dengan lebih daripada 260 entiti standard. Sistem besar rakan kongsi dalaman dan luaran menyumbang konsep khusus industri kepada Model Data Lazim.

Berbilang sistem dan platform melaksanakan Model Data Biasa hari ini, termasuk Perkhidmatan aliran data Power BI dan Data Azure. Ia telah disokong dalam Microsoft Dataverse, Dynamics 365, Power Apps, Power BI dan perkhidmatan data Azure yang akan datang, mengakru nilai secara langsung ke arah [Inisiatif Data Terbuka](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Skema entiti Customer Insights

Untuk mewujudkan pandangan 360 darjah pelanggan dan membuat model Customer Insights tersedia dalam Model Data Lazim untuk kebolehpanjangan, kami telah menerbitkan skim entiti berikut:

| Entiti | Perihalan |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Aktiviti yang dilaksanakan oleh pengguna yang mempunyai nilai pemerhatian terhadap perniagaan. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Seseorang atau organisasi yang sama ada melaksanakan atau mempunyai potensi untuk terlibat dalam aktiviti perniagaan. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definisi KPI yang dibahagikan dengan sifar atau lebih banyak dimensi (seperti Pengguna Aktif Bulanan, Jumlah Belanja Mengikut Pelanggan, Purata Kos Pemerolehan Pelanggan) |
|[Bahagian](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Mentakrifkan sekumpulan ahli yang mempunyai sifat umum. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Ahli yang menyertai dalam bahagian diberikan. |

Untuk maklumat lanjut, lihat dokumentasi tentang [Skim entiti Customer Insights dalam Model Data Lazim](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Lihat entiti menggunakan Pengemudi Entiti Model Data Biasa

Anda boleh melihat entiti dalam [Navigasi Entiti Common Data Model](https://microsoft.github.io/CDM/). Pilih entiti daripada bahagian Aplikasi Cerapan untuk mendapatkan senarai entiti Customer Insights dan definisi mereka.
> [!div class="mx-imgBorder"]
> ![Pengemudi Entiti CDM menunjukkan entiti CustomerActivity.](media/CDM-entity-navigator.png "Pengemudi Entiti CDM menunjukkan entiti CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
