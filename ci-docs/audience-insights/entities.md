---
title: Entiti dan set data
description: Lihat data pada halaman Entiti.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049405"
---
# <a name="entities-in-audience-insights"></a>Entiti dalam wawasan khalayak

Selepas [mengkonfigurasi sumber data anda](data-sources.md), pergi ke halaman **Entiti** untuk menilai kualiti data yang dimasukkan. Entiti dianggap sebagai set data. Berbilang keupayaan Dynamics 365 Customer Insights dibina sekitar entiti ini. Mengkajinya semula dengan teliti boleh membantu anda mengesahkan output keupayaan tersebut.

Halaman **Entiti** menyenaraikan entiti dan termasuk beberapa lajur:

- **Nama**: Nama entiti data anda. Jika anda nampak simbol amaran di sebelah nama entiti, ia bermaksud data untuk entiti tersebut tidak berjaya dimuatkan.
- **Sumber**: Jenis sumber data yang memasukkan entiti
- **Dicipta oleh**: Nama orang yang mencipta entiti
- **Dicipta**: Tarikh dan masa penciptaan entiti
- **Dikemas kini oleh**: Nama orang yang mengemas kini entiti
- **Kemas kini terakhir**: Tarikh dan masa kemas kini yang terakhir bagi entiti
- **Segar semula terakhir**: Tarikh dan masa data terakhir segar semula

## <a name="exploring-a-specific-entitys-data"></a>Menerokai data entiti khusus

Pilih entiti untuk menerokai medan dan rekod yang berbeza termasuk dalam entiti tersebut.

> [!div class="mx-imgBorder"]
> ![Pilih entiti](media/data-manager-entities-data.png "Pilih entiti")

- Tab **Data** menunjukkan butiran penyenaraian jadual tentang rekod individu entiti.

> [!div class="mx-imgBorder"]
> ![Jadual medan](media/data-manager-entities-fields.PNG "Jadual medan")

- Tab **Atribut** dipilih secara lalai dan menunjukkan jadual untuk menyemak butiran bagi entiti yang dipilih seperti nama medan, jenis data dan jenis. Lajur **Jenis** menunjukkan jenis berkaitan Model Data Lazim, yang mana sama ada dikenal pasti secara automatik oleh sistem atau [dipetakan secara manual](map-entities.md) oleh pengguna. Ini ialah jenis semantik yang mungkin berbeza daripada jenis data atribut—contohnya, medan *e-mel* di bawah mempunyai jenis data *Teks* tetapi jenis Model Data Lazim (semantik) berkemungkinan *E-mel* atau *AlamatE-mel*.

> [!NOTE]
> Kedua-dua jadual menunjukkan hanya sampel data entiti anda. Untuk melihat set data lengkap, pergi ke halaman **Sumber data**, pilih entiti, pilih **Edit** dan lihat data entiti ini dengan editor Power Query seperti yang diterangkan dalam [Sumber data](data-sources.md).

Untuk mengetahui lebih lanjut tentang data yang dimasukkan di dalam entiti, lajur **Ringkasan** menyediakan anda dengan beberapa ciri penting data seperti batal, nilai yang hilang, nilai unik, kiraan dan pengagihan, sebagaimana berkaitan dengan data anda.

Pilih ikon carta untuk melihat ringkasan data.

> [!div class="mx-imgBorder"]
> ![Simbol ringkasan](media/data-manager-entities-summary.png "Jadual ringkasan data")

### <a name="next-step"></a>Langkah seterusnya

Lihat topik [Menyatukan](data-unification.md) untuk mengetahui cara untuk *memetakan*, *padan* dan *menggabungkan* data yang dimasukkan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
