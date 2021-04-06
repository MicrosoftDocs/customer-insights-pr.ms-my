---
title: Mengintegrasikan data web daripada wawasan penglibatan dengan wawasan khalayak
description: Membawa maklumat web tentang pelanggan daripada wawasan penglibatan kepada wawasan khalayak.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597476"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Mengintegrasikan data web daripada wawasan penglibatan dengan wawasan khalayak

Pelanggan sering melakukan transaksi hari je hari mereka dalam talian menggunakan laman web. Keupayaan wawasan penglibatan Dynamics 365 Customer Insights ialah penyelesaian berguna untuk mengintegrasikan data web sebagai sumber. Sebagai tambahan kepada transaksi, demografik atau data tingkah laku kita boleh melihat aktiviti pada web dalam profil pelanggan disatukan. Kita boleh menggunakan profil ini untuk mendapatkan wawasan tambahan seperti segmen, langkah atau ramalan untuk pengaktifan khalayak.

Artikel ini menerangkan langkah untuk membawa data aktiviti web pelanggan anda daripada wawasan penglibatan ke dalam persekitaran wawasan khalayak sedia ada anda.

Dalam contoh ini, kami menganggap persekitaran yang mengandungi profil pelanggan disatukan. Profil tersebut disatukan dengan sumber daripada tinjauan, jualan runcit dan sistem tiket. Ia juga menunjukkan aktiviti yang berkaitan dengan pelanggan. 

Kini, kami ingin tahu jika pelanggan melawat sifat web kami dan memahami aktiviti mereka. Aktiviti termasuk, contohnya, laman web yang dilawati atau halaman produk yang dilihat daripada pautan yang diterima dalam e-mel.

## <a name="prerequisites"></a>Prasyarat

Untuk mengintegrasikan data daripada wawasan penglibatan, beberapa prasyarat perlu dipenuhi: 

- Mengintegrasikan SDK wawasan penglibatan dengan laman web anda. Untuk maklumat lanjut, lihat [Mari bermula dengan SDK web](../engagement-insights/instrument-website.md).
- Mengeksport peristiwa web daripada wawasan penglibatan memerlukan akses kepada akaun storan ADLS Gen 2 yang akan digunakan untuk membuktikan data peristiwa web kepada wawasan khalayak. Untuk maklumat lanjut, lihat [Eksport peristiwa](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Mengkonfigurasikan peristiwa yang ditapis dalam wawasan penglibatan

Selepas pentadbir berinstrumen sebuah laman web dengan SDK wawasan penglibaran, *peristiwa asas* dikumpulkan apabila pengguna melihat halaman web atau klik di mana-mana. Peristiwa asas cenderung untuk mengandungi banyak butiran. Bergantung pada kes penggunaan anda, anda hanya memerlukan subset data dalam peristiwa asas. Wawasan interaksi membolehkan anda mencipta *peristiwa ditapis* yang hanya mengandungi sifat peristiwa asas yang anda pilih.     

Untuk maklumat lanjut, lihat [Cipta dan ubah suai peristiwa yang ditapis](../engagement-insights/refined-events.md).

Pertimbangan apabila mencipta peristiwa yang ditapis: 

- Berikan nama yang bermakna untuk peristiwa yang ditapis. Ia akan digunakan sebagai nama aktiviti dalam wawasan khalayak.
- Pilih sekurang-kurangnya sifat berikut untuk mencipta aktiviti dalam wawasan khalayak: 
    - Signal.Action.Name - menunjukkan butiran aktiviti
    - Signal.User.Id - digunakan untuk memetakan dengan ID pelanggan
    - Isyarat. lihat. URI - digunakan sebagai alamat web sebagai asas untuk segmen atau langkah
    - Signal.Export.Id - untuk menggunakan sebagai kunci utama bagi peristiwa <!-- system generated, do we need to list?-->
    - Isyarat. Cap waktu - untuk menentukan tarikh dan masa aktiviti

Pilih penapis untuk fokus pada acara dan halaman yang penting untuk kes kegunaan anda. Dalam contoh ini, kami akan menggunakan nama tindakan "Promosi e-mel".

## <a name="export-the-refined-web-events"></a>Eksport Peristiwa Web yang Ditapis 

Selepas menentukan peristiwa yang ditapis ditakrifkan, anda perlu mengkonfigurasikan eksport data peristiwa kepada Azure Data Lake Storage, yang boleh ditetapkan sebagai sumber data untuk pengingesan dalam wawasan khalayak. Eksport berlaku secara kerap semasa peristiwa mengalifr daripada sifat web.

Untuk maklumat lanjut, lihat [Eksport peristiwa](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Inges data peristiwa kepada wawasan khalayak

Sekarang anda telah menentukan peristiwa yang ditapis dan mengkonfigurasi eksport, kita bergerak untuk mengambil data kepada wawasan khalayak. Anda perlu mencipta sumber data baharu berdasarkan folder Common Data Model. Masukkan butiran untuk akaun storan yang anda eksport peristiwa tersebut. Dalam fail *default.cdm.json*, pilih peristiwa yang ditapis untuk mengambil dan mencipta entiti dalam wawasan khalayak.

Untuk maklumat lanjut, lihat [Sambung ke folder Common Data Model menggunakan akaun Azure Data Lake](connect-common-data-model.md)


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Kaitkan data peristiwa yang ditapis sebagai aktiviti profil pelanggan

Selepas melengkapkan entiti pengingesan, anda boleh mengkonfigurasikan aktiviti untuk profil pelanggan.

Untuk maklumat lanjut, lihat [Aktiviti pelanggan](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Halaman aktiviti dengan anak tetingkap aktiviti Edit dikembangkan dan medan yang diisi.":::

Konfigurasikan aktiviti baharu dengan pemetaan berikut: 

- **Kunci Utama:** Signal.Export.Id, ID unik yang tersedia untuk setiap rekod peristiwa dalam wawasan penglibatan. Sifat ini dijana secara automatik.

- **Cap waktu:** Signal.Timestamp dalam sifat peristiwa.

- **Peristiwa:** Signal.Name, nama peristiwa yang anda mahu jejak.

- **Alamat web:** Signal.View.Uri merujuk pada uri laman yang mencipta peristiwa tersebut.

- **Butiran:** Signal.Action.Name untuk mewakili maklumat untuk mengaitkan dengan peristiwa tersebut. Sifat yang dipilih dalam kes ini menunjukkan bahawa peristiwa adalah untuk promosi e-mel.

- **Jenis aktiviti:** Dalam contoh ini, kita pilih WebLog jenis aktiviti sedia ada. Pemilihan ini adalah pilihan penapis berguna untuk menjalankan model ramalan atau membuat segmen berdasarkan jenis aktiviti ini.

- **Sediakan perhubungan:** Tetapan penting ini menjalin hubungan aktiviti kepada profil pelanggan sedia ada. **Signal.User.Id** ialah pengecam yang dikonfigurasikan dalam SDK untuk dikumpulkan dan yang berkaitan dengan ID pengguna dalam sumber data lain yang dikonfigurasikan dalam wawasan khalayak. Dalam contoh ini, kami mengkonfigurasi hubungan antara Signal.User.Id dan RetailCustomers:CustomerRetailId, yang merupakan kunci utama yang telah diungkam dalam cara proses penyatuan data.


Selepas memproses aktiviti, anda boleh menyemak rekod pelanggan dan membuka kad pelanggan untuk melihat aktiviti daripada wawasan penglibatan dalam garis masa. 

> [!TIP]
> Untuk mencari id pelanggan yang mempunyai aktiviti wawasan penglibatan, pergi ke **Entiti** dan pratonton data untuk entiti UnifiedActivity. ActivityTypeDisplay = WebLog mengandungi aktiviti wawasan penglibatan yang dikonfigurasikan dalam contoh di atas. Salin ID pelanggan untuk antara rekod tersebut dan untuk ID pada halaman **Pelanggan**.

## <a name="next-steps"></a>Langkah-langkah Berikutnya

Anda kini boleh mencipta [segmen](segments.md), [langkah](measures.md) dan [ramalan](predictions.md) untuk membuat sambungan yang bermakna dengan pelanggan anda.


[!INCLUDE[footer-include](../includes/footer-banner.md)]