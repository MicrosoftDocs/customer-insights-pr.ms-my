---
title: Gunakan segmen cerapan khalayak untuk menapis laporan cerapan penglibatan
description: Gunakan segmen cerapan khalayak dalam analisis interaktif data tingkah laku yang ditangkap oleh cerapan penglibatan pada tapak web pelanggan.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230497"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Gunakan segmen cerapan khalayak untuk menapis laporan cerapan penglibatan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dengan cerapan penglibatan, anda boleh menggunakan segmen cerapan khalayak dalam analisis interaktif data tingkah laku yang ditangkap oleh cerapan penglibatan pada tapak web anda.

## <a name="prerequisite"></a>Prasyarat

- Persekitaran cerapan penglibatan yang mana anda mempunyai data segmen cerapan pelanggan yang dipautkan kepada persekitaran cerapan khalayak yang mana segmen dan profil pelanggan dicipta. Maklumat lanjut: [Cipta pautan antara cerapan khalayak dan cerapan penglibatan](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Cipta segmen cerapan khalayak 

> [!IMPORTANT]
> Untuk segmen cerapan khalayak untuk muncul dalam cerapan penglibatan, anda mesti [jalankan proses gabungan dan hiliran](../audience-insights/merge-entities.md) terlebih dahulu. Proses hiliran adalah penting kerana ia menjana jadual unik yang menyediakan segmen cerapan khalayak untuk dikongsi dengan cerapan penglibatan. (Jika sistem segar semula dijadualkan, ia akan secara automatik memasukkan proses hiliran.)

Anda boleh menggunakan segmen cerapan khalayak dalam laporan di luar kotak cerapan penglibatan atau laporan tersuai yang telah anda cipta. Untuk mendapatkan maklumat lanjut, pergi ke [Laporan profil di luar kotak](profile-reports.md) dan [Cipta dan edit laporan tersuai](custom-reports.md).

**Untuk menggunakan segmen cerapan khalayak dalam laporan cerapan penglibatan**

1. Daripada halaman **Ruang kerja** anda pilih **Data** dan kemudian pilih tab **Segmen**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Pilih tab Segmen.":::

   >[!NOTE]
   > Pemilihan segmen cerapan khalayak membawa anda kepada cerapan khalayak, yang mana anda boleh mengetahui cara segmen itu dicipta dari segi peraturan dan logik. Untuk mendapatkan maklumat lanjut tentang segmen cerapan khalayak, pergi ke [Lihat dan cipta segmen](../audience-insights/segments.md).

2. Pilih laporan di luar kotak atau [cipta laporan tersuai](custom-reports.md) dan kemudian pilih **Tambah syarat**. (Untuk contoh ini, kami memilih laporan **Pandangan halaman**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Tambahkan syarat.":::

3. Pilih **Tapis mengikut segmen**, kembangkan senarai **Jenis segmen** dan kemudian pilih **Demografi**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Pilih jenis segmen Demografi.":::

4. Kembangkan senarai **Nama segmen** dan kemudian pilih segmen cerapan khalayak.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Pilih segmen.":::

5. Anda boleh menggunakan satu atau lebih segmen, termasuk tingkah laku (cerapan penglibatan) dan demografi segmen (cerapan khalayak). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Laporan pandangan halaman terhad kepada pelanggan Amerika Syarikat dan segmen Halaman Utama.":::

Dalam imej sebelum ini, **pelanggan Amerika Syarikat** dan segmen **Halaman Utama** telah dipilih, yang mengehadkan laporan **Pandangan halaman** untuk memaparkan hanya dua segmen. 


>[!NOTE]
> Anda boleh menggunakan segmen cerapan khalayak untuk menapis laporan di luar kotak, laporan tersuai dan corong dalam cerapan penglibatan. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]