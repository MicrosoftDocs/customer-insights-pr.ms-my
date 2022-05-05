---
title: Mulakan Dengan Dynamics 365 Customer Insights
description: Gambaran keseluruhan Wawasan Pelanggan membantu sumber untuk bermula dengan cepat.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6d23552687530fddf42418b924571dddc0209e69
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643225"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Mulakan Dengan Dynamics 365 Customer Insights

Wawasan Pelanggan dapat membantu anda membina pemahaman yang lebih mendalam mengenai pelanggan anda. Sambungkan data dari pelbagai sumber transaksi, tingkah laku dan pemerhatian untuk mencipta pandangan pelanggan 360 darjah. Gunakan wawasan ini untuk memacu pengalaman dan proses yang berpusatkan pelanggan. Menyatukan dan memahami data pelanggan dan memanfaatkannya untuk tindakan dan wawasan pintar.

## <a name="step-1-create-an-environment"></a>Langkah 1: Cipta persekitaran

Untuk memulakan, anda perlu mencipta persekitaran untuk bekerja terlebih dahulu. Jika organisasi anda sudah membeli lesen, lihat [Cipta persekitaran](create-environment.md). Untuk memulakan percubaan untuk Wawasan Pelanggan, lihat [Menyediakan persekitaran percubaan](trial-signup.md). 

## <a name="step-2-explore-customer-insights"></a>Langkah 2: Terokai Wawasan Pelanggan

Kali pertama anda log masuk ke Wawasan Pelanggan, anda boleh mengkonfigurasi tetapan dan meneroka produk.

1. [log masuk ke Wawasan](https://home.ci.ai.dynamics.com) Pelanggan menggunakan akaun pengguna Microsoft Azure Active Directory (AAD) anda.

1. [Tukar persekitaran](manage-environments.md#switch-environments) untuk melihat data demo dan [meneroka Wawasan Pelanggan](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Langkah 3: Inges, satukan dan sediakan perhubungan untuk data anda

Profil disatukan ialah asas untuk mendapatkan cerapan dan mengambil tindakan terhadap data. Bawa masuk data daripada pelbagai sumber dan jalankan proses penyatuan data untuk menggabungkan profil disatukan. Tentukan perhubungan antara entiti yang diinges dengan menggunakan ciri pengayaan untuk menambahkan maklumat pada profil. 

1. Inges data dengan mencipta sumber data daripada pelbagai pilihan. Pilih antara [Power Query penyambung](connect-power-query.md), [folder](connect-common-data-model.md) Model Data Biasa, atau [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

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

1. Semak pilihan penyepaduan, contohnya kepada aplikasi Dynamics 365 yang lain dengan [tambahan](customer-card-add-in.md) Kad Pelanggan.  


[!INCLUDE [footer-include](includes/footer-banner.md)]