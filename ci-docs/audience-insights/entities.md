---
title: Entiti dan set data
description: Lihat data pada halaman Entiti.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 2a207a3dcad4bf192efb6ee1554195f10b19670b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732092"
---
# <a name="entities-in-audience-insights"></a>Entiti dalam wawasan khalayak

Selepas [mengkonfigurasi sumber data anda](data-sources.md), pergi ke halaman [Entiti](data-sources.md) untuk menilai kualiti data yang dimasukkan. Entiti dianggap sebagai set data. Pelbagai keupayaan Dynamics 365 Customer Insights dibina di sekeliling entiti ini. Mengkajinya semula dengan teliti boleh membantu anda mengesahkan output keupayaan tersebut.

Halaman **Entiti** menyenaraikan entiti dan termasuk beberapa lajur:

- **Nama**: Nama entiti data anda. Jika anda nampak simbol amaran di sebelah nama entiti, ia bermaksud data untuk entiti tersebut tidak berjaya dimuatkan.
- **Sumber**: Jenis sumber data yang memasukkan entiti
- **Dicipta oleh**: Nama orang yang mencipta entiti
- **Dicipta**: Tarikh dan masa penciptaan entiti
- **Kemaskini** : Nama orang yang mengemas kini entiti
- **Status** : Butiran mengenai kemas kini terakhir entiti

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Terokai data entiti khusus

Pilih entiti untuk menerokai medan dan rekod yang berbeza termasuk dalam entiti tersebut.

> [!div class="mx-imgBorder"]
> ![Pilih entiti.](media/data-manager-entities-data.png "Pilih entiti")

- Tab **Data** menunjukkan butiran penyenaraian jadual tentang rekod individu entiti.

> [!div class="mx-imgBorder"]
> ![Jadual medan.](media/data-manager-entities-fields.PNG "Jadual medan")

- Tab **Atribut** dipilih secara lalai dan menunjukkan jadual untuk menyemak butiran bagi entiti yang dipilih seperti nama medan, jenis data dan jenis. Lajur **Jenis** menunjukkan jenis berkaitan Model Data Lazim, yang mana sama ada dikenal pasti secara automatik oleh sistem atau [dipetakan secara manual](map-entities.md) oleh pengguna. Jenis ini ialah jenis semantik yang boleh berbeza daripada jenis data atribut. Sebagai contoh, medan *E-mel* di bawah mempunyai jenis data *Teks* tetapi jenis Common Data Model (semantik) mungkin *E-mel* atau *EmailAddress*.

> [!NOTE]
> Kedua-dua jadual menunjukkan hanya sampel data entiti anda. Untuk melihat set data lengkap, pergi ke halaman **Sumber data**, pilih entiti, pilih **Edit** dan lihat data entiti ini dengan editor Power Query seperti yang diterangkan dalam [Sumber data](data-sources.md).

Untuk mengetahui lebih lanjut tentang data yang dimasukkan di dalam entiti, lajur **Ringkasan** menyediakan anda dengan beberapa ciri penting data seperti batal, nilai yang hilang, nilai unik, kiraan dan pengagihan, sebagaimana berkaitan dengan data anda.

Pilih ikon carta untuk melihat ringkasan data.

> [!div class="mx-imgBorder"]
> ![Simbol ringkasan.](media/data-manager-entities-summary.png "Jadual ringkasan data")

## <a name="entity-specific-information"></a>Maklumat entiti tertentu

Bahagian berikut menyediakan maklumat tentang beberapa entiti yang dicipta sistem.

### <a name="corrupted-data-sources"></a>Sumber data rosak

Medan daripada sumber data yang diinges boleh mengandungi data yang rosak. Rekod dengan medan yang rosak terdedah dalam entiti yang dicipta sistem. Mengetahui tentang rekod rosak membantu anda mengenal pasti data yang perlu disemak dan dikemas kini pada sistem sumber. Selepas penyegaran semula sumber data seterusnya, rekod yang dibetulkan diinjes kepada Customer Insights dan diserahkan kepada proses hiliran. 

Sebagai contoh, lajur 'hari jadi' mempunyai jenis data yang ditetapkan sebagai 'tarikh'. Rekod pelanggan mempunyai hari lahir mereka dimasukkan sebagai '01/01/19777'. Sistem akan membenderakan rekod ini sebagai rosak. Seseorang kini boleh menukar hari lahir dalam sistem sumber kepada '1977'. Selepas penyegaran semula sumber data automatik, medan kini mempunyai format yang sah dan rekod akan dialih keluar daripada entiti yang rosak. 

Pergi ke **Data** > **Entiti** dan cari entiti yang rosak dalam bahagian **Sistem**. Penamaan skema entiti yang rosak: 'DataSourceName_EntityName_corrupt'.

Customer Insights masih memproses rekod yang rosak. Walau bagaimanapun, ia mungkin menyebabkan isu semasa bekerja dengan data disatukan.

Pemeriksaan berikut berjalan pada data yang diinjes untuk mendedahkan rekod rosak: 

- Nilai medan tidak sepadan dengan jenis data lajurnya.
- Medan mengandungi aksara yang menyebabkan lajur tidak sepadan dengan skema yang dijangkakan. Sebagai contoh: sebut harga yang diformatkan dengan salah, sebut harga yang tidak dilepaskan atau aksara baris baharu.
- Jika terdapat lajur datetime/date/datetimeoffset, formatnya perlu ditentukan dalam model jika tidak mengikuti format ISO standard.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
