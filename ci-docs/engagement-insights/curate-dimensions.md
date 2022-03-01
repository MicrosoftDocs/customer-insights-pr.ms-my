---
title: Gunakan dimensi demografi untuk data tingkah laku pemisahan (dimensi dikumpul)
description: Gunakan dimensi dikumpul profil disatukan untuk mendayakan sifat profil pelanggan cerapan khalayak.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461114"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Gunakan dimensi demografi untuk data tingkah laku pemisahan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dengan menggunakan dimensi demografi profil disatukan, pengguna cerapan penglibatan boleh mengakses sifat profil cerapan khalayak. Anda kemudian boleh menggunakan sifat ini dalam analisis interaktif data tingkah laku, termasuk data yang ditangkap oleh cerapan penglibatan pada tapak web atau aplikasi mudah alih anda.

>[!NOTE]
> Cerapan penglibatan termasuk dimensi di luar kotak untuk sifat peristiwa. Maklumat lanjut: [Lihat dan cipta dimensi](dimensions.md)

## <a name="prerequisite"></a>Prasyarat

- Persekitaran cerapan penglibatan yang mana anda mempunyai data profil pelanggan yang dipautkan kepada persekitaran cerapan khalayak yang mana profil pelanggan yang dicipta. Maklumat lanjut: [Cipta pautan antara cerapan khalayak dan cerapan penglibatan](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Selepas anda mencipta pautan antara cerapan khalayak dan persekitaran cerapan penglibatan, anda mungkin hanya mahu data khusus kepada sifat profil pelanggan, yang mungkin berguna sebagai dimensi dalam cerapan penglibatan. Untuk mendapatkan maklumat lanjut, pergi ke [Dayakan cerapan khalayak segmen dan atribut profil disatukan](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>Cipta laporan tersuai baharu

1. Pada tetingkap kiri, pilih **Tersuai** > **Laporan baharu** dan kemudian pilih metrik yang anda mahu. (Untuk contoh ini, kami memilih **Pandangan halaman mengikut Jam**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Pilih metrik.":::

2. Dalam editor Visualisasi, pilih **Dimensi** dan kemudian pilih **Demografi** dalam menu juntai bawah **Jenis Dimensi**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Pilih demografi.":::

3. Pilih dimensi **Isyarat.Pelanggan.*xxx***. (Contoh ini menunjukkan Isyarat.Pelanggan.Negara.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Pilih dimensi.":::
  
## <a name="limitations"></a>Batasan

Pada masa ini anda boleh menggunakan dimensi demografi untuk data tingkah laku pemisahan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
