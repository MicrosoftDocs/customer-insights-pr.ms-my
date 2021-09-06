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
ms.openlocfilehash: 137de726b243b501491fcbe7866820aaee26097fcf379270c423c277374ae9a4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033826"
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
