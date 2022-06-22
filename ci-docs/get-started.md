---
title: Mulakan Dengan Dynamics 365 Customer Insights
description: Gambaran keseluruhan Wawasan Pelanggan membantu sumber untuk bermula dengan cepat.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011990"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Mulakan Dengan Dynamics 365 Customer Insights

Wawasan Pelanggan dapat membantu anda membina pemahaman yang lebih mendalam mengenai pelanggan anda. Sambungkan data dari pelbagai sumber transaksi, tingkah laku dan pemerhatian untuk mencipta pandangan pelanggan 360 darjah. Gunakan wawasan ini untuk memacu pengalaman dan proses yang berpusatkan pelanggan. Menyatukan dan memahami data pelanggan dan memanfaatkannya untuk tindakan dan wawasan pintar.

## <a name="step-1-create-an-environment"></a>Langkah 1: Cipta persekitaran

Pertama, wujudkan persekitaran untuk bekerja. Jika organisasi anda sudah membeli lesen, lihat [Cipta persekitaran](create-environment.md). Untuk memulakan percubaan untuk Wawasan Pelanggan, lihat [Menyediakan persekitaran percubaan](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Langkah 2: Terokai Wawasan Pelanggan

Kali pertama anda log masuk ke Wawasan Pelanggan, konfigurasikan tetapan dan meneroka produk.

1. [log masuk ke Wawasan](https://home.ci.ai.dynamics.com) Pelanggan menggunakan akaun pengguna Microsoft Azure Active Directory (AAD) anda.

1. Tukar persekitaran untuk melihat data demo dan [meneroka Wawasan Pelanggan](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Langkah 3: Inges, satukan dan sediakan perhubungan untuk data anda

Profil disatukan ialah asas untuk mendapatkan cerapan dan mengambil tindakan terhadap data. Bawa masuk data daripada pelbagai sumber dan jalankan proses penyatuan data untuk menggabungkan profil disatukan. Tentukan hubungan antara entiti yang ditelan dan gunakan ciri pengayaan untuk menambah maklumat ke profil.

1. Inges data dengan mencipta sumber data daripada pelbagai pilihan. Pilih antara [Azure Data Lake Storage, termasuk Model](connect-common-data-model.md) Data Biasa, [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md), atau [Power Query penyambung](connect-power-query.md).

1. [Jalankan proses](data-unification.md) penyatuan data dengan mengenal pasti [medan](map-entities.md) sumber, mengalih keluar [pendua](remove-duplicates.md), [keadaan](match-entities.md) yang sepadan dan [medan](merge-entities.md) penyatuan.

1. Biasakan diri dengan [entiti yang sistem cipta](entities.md) dan cipta [perhubungan antara entiti yang diinges](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Langkah 4: Tingkatkan profil disatukan dengan ramalan, aktiviti dan langkah-langkah

Dengan profil bersatu disediakan, tingkatkan data anda dan tingkatkan lagi maklumat yang mereka berikan.

1. Pilih daripada pustaka pembekal pengayaan yang berkembang untuk [memperkaya data pelanggan anda](enrichment-hub.md).

1. Gunakan [model di luar kotak](predictions-overview.md) untuk meramal kemungkinan pulangan atau hasil yang dijangkakan.

1. [Konfigurasikan aktiviti](activities.md) berdasarkan data yang diinges dan visualisasikan interaksi dengan pelanggan anda dalam garis masa kronologi.

1. [Bina langkah-langkah](measures.md) untuk mengukur matlamat perniagaan dan KPI anda.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Langkah 5: Cipta segmen dan aktifkan data melalui pelbagai pilihan eksport

Sekarang data anda lengkap dan mengandungi pelbagai maklumat mengenai pelanggan anda, cari cara untuk mengambil tindakan ke atas data tersebut.

1. [Cipta segmen](segments.md), subset asas pelanggan anda untuk memastikan tindakan anda relevan untuk pelanggan yang disasarkan.

1. Layari katalog berkembang bagi [pilihan eksport](export-destinations.md) tempat anda boleh menggunakan data pelanggan. Contohnya, anda boleh menggunakan data untuk mengurus promosi dan jangkauan dengan pemasaran digital.

1. Semak pilihan penyepaduan, contohnya kepada aplikasi Dynamics 365 yang lain dengan [tambahan](customer-card-add-in.md) Kad Pelanggan.  


[!INCLUDE [footer-include](includes/footer-banner.md)]
