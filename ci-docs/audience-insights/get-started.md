---
title: Mari Bermula dengan keupayaan cerapan khalayak dalam Dynamics 365 Customer Insights
description: Gambaran keseluruhan cerapan khalayak membantu sumber untuk bermula dengan cepat.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645275"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Mari Bermula dengan keupayaan cerapan khalayak dalam Dynamics 365 Customer Insights

Cerapan khalayak dapat membantu anda membina pemahaman yang lebih mendalam tentang pelanggan anda. Sambungkan data dari pelbagai sumber transaksi, tingkah laku dan pemerhatian untuk mencipta pandangan pelanggan 360 darjah. Gunakan wawasan ini untuk memacu pengalaman dan proses yang berpusatkan pelanggan. Menyatukan dan memahami data pelanggan dan memanfaatkannya untuk tindakan dan wawasan pintar.

## <a name="step-1-create-an-environment"></a>Langkah 1: Cipta persekitaran

Untuk memulakan, anda perlu mencipta persekitaran untuk bekerja terlebih dahulu. Jika organisasi anda sudah membeli lesen, lihat [Cipta persekitaran](create-environment.md). Untuk memulakan percubaan bagi cerapan khalayak, lihat [Sediakan persekitaran percubaan](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Langkah 2: Teroka cerapan khalayak

Kali pertama anda log masuk ke cerapan khalayak, anda boleh mengkonfigurasikan tetapan dan menerokai produk.

1. [Log masuk ke cerapan khalayak](https://home.ci.ai.dynamics.com) menggunakan akaun pengguna Microsoft Azure Active Directory (AAD).

1. [Tukar persekitaran](manage-environments.md#switch-environments) untuk melihat data demo dan [menerokai cerapan khalayak](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Langkah 3: Inges, satukan dan sediakan perhubungan untuk data anda

Profil disatukan ialah asas untuk mendapatkan cerapan dan mengambil tindakan terhadap data. Bawa masuk data daripada pelbagai sumber dan jalankan proses penyatuan data untuk menggabungkan profil disatukan. Tentukan perhubungan antara entiti yang diinges dengan menggunakan ciri pengayaan untuk menambahkan maklumat pada profil. 

1. Inges data dengan mencipta sumber data daripada pelbagai pilihan. Pilih antara [penyambung Power Query](connect-power-query.md), [folder Common Data Model](connect-common-data-model.md) atau [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. Jalankan [proses penyatuan data](data-unification.md) dengan melalui fasa [peta](map-entities.md), [padanan](match-entities.md), dan [gabungan](merge-entities.md).

1. Biasakan diri dengan [entiti yang sistem cipta](entities.md) dan cipta [perhubungan antara entiti yang diinges](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Langkah 4: Tingkatkan profil disatukan dengan ramalan, aktiviti dan langkah-langkah

Dengan persediaan profil disatukan, anda boleh meningkatkan data anda dan meningkatkan lagi maklumat yang mereka sediakan.

1. Pilih daripada pustaka pembekal pengayaan yang berkembang untuk [memperkaya data pelanggan anda](enrichment-hub.md).

1. Gunakan [model di luar kotak](predictions-overview.md) untuk meramal kemungkinan pulangan atau hasil yang dijangkakan.

1. [Konfigurasikan aktiviti](activities.md) berdasarkan data yang diinges dan visualisasikan interaksi dengan pelanggan anda dalam garis masa kronologi. 

1. [Bina langkah-langkah](measures.md) untuk mengukur matlamat perniagaan dan KPI anda.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Langkah 5: Cipta segmen dan aktifkan data melalui pelbagai pilihan eksport

Sekarang data anda lengkap dan mengandungi pelbagai maklumat tentang pelanggan anda, masa untuk mencari cara bertindak ke atas data tersebut. 

1. [Cipta segmen](segments.md), subset asas pelanggan anda untuk memastikan tindakan anda relevan untuk pelanggan yang disasarkan.

1. Layari katalog berkembang bagi [pilihan eksport](export-destinations.md) tempat anda boleh menggunakan data pelanggan. Contohnya, anda boleh menggunakan data untuk mengurus promosi dan jangkauan dengan pemasaran digital.

1. Semak pilihan integrasi, contohnya dengan [sambungan langsung dengan cerapan penglibatan](../engagement-insights/integrate-audience-insights-engagement-insights.md) atau kepada aplikasi Dynamics 365 lain dengan [tambahan Kad Pelanggan](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
