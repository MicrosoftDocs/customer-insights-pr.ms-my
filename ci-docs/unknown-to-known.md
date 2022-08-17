---
title: Peribadikan pengalaman anda dengan data tentang pengguna yang diketahui dan tidak diketahui
description: Masukkan maklumat tentang pengguna yang dahulunya tidak diketahui apabila anda mengetahui identiti mereka.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224306"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Peribadikan pengalaman anda dengan data tentang pengguna yang diketahui dan tidak diketahui

Menguruskan data pelanggan bukanlah cabaran baru, tetapi semakin sukar kerana pengguna menavigasi pelbagai saluran digital yang ditawarkan oleh jenama. Pengguna yang dikenali (disahkan) dalam satu saluran menjadi tidak diketahui (tidak disahkan) dalam yang lain jika tidak log masuk. Masalahnya selalunya ialah pengguna yang tidak disahkan (tidak diketahui) tidak mempunyai ID biasa. Ia boleh digunakan untuk mengaitkan atribut profil yang bermakna dan menjana profil pelanggan yang bersatu. Wawasan Pelanggan membantu menyelesaikan masalah ini dengan menelan data daripada kaedah penjejakan pada sistem sumber anda. Menggabungkan profil yang tidak diketahui dan diketahui menyediakan organisasi dengan pandangan lengkap profil terkini dan transaksi sejarah, tingkah laku dan demografi mereka. Ini bahkan melangkah lebih jauh dengan memberikan resolusi identiti yang membolehkan anda menyatukan aktiviti pelanggan di pelbagai saluran, termasuk laman web anda, pembelian di kedai, program kesetiaan, dan sebagainya.

## <a name="sample-scenario"></a>Senario sampel

Mari kita fikirkan rangkaian kopi, yang mempunyai pangkalan pelanggan yang luas yang membeli kopi dan makanan di kedai dan memesan produk dalam talian. Selalunya, pelawat dalam talian tidak disahkan semasa melayari produk, menjadikannya "pengguna yang tidak diketahui". Sukar bagi rangkaian kopi untuk memberikan tawaran dan pengalaman yang diperibadikan jika pengguna tidak diketahui. Sebaliknya, pelanggan boleh log masuk ke akaun mereka dan menjadi "pengguna terkenal" kepada syarikat dengan menyertai sistem kesetiaan, yang seterusnya membolehkan pengalaman yang lebih diperibadikan. Wawasan Pelanggan boleh membantu rangkaian kopi mendapatkan cerapan tentang pengguna yang diketahui dan tidak diketahui sebelum ini.

Dengan Wawasan Pelanggan, syarikat boleh menggabungkan profil pelanggan dengan data aktiviti daripada sesi yang tidak disahkan (tidak diketahui) selepas pengguna mendaftar masuk dan diketahui. Rangkaian kopi boleh membawa data dari sumber data lain menggunakan penyambung terbina dalam ke dalam Wawasan Pelanggan untuk menggabungkan identiti untuk pelanggan dari pelbagai saluran.

## <a name="prerequisites"></a>Prasyarat

- Data web dikumpulkan dan mengandungi "ID pelawat" untuk semua pelawat.
- Data web mengandungi "ID pengguna yang disahkan" untuk pelawat yang log masuk. ID ini dikaitkan dengan sistem kesetiaan.
- Data peristiwa bernilai tinggi seperti "Paparan produk" dan "Semak Keluar" ditakrifkan dan disertakan dalam data sumber bersama-sama dengan cap masa peristiwa dan ID peristiwa.

Jadual berikut menunjukkan contoh ringkas bagaimana peristiwa web bernilai tinggi boleh ditangkap.

|EventID|EventTimeStamp|ID Pengguna|ID Kesetiaan|Nama Acara|
|--|--|--|--|--|
|1|07-23-2022 10:00:00|abc123|--|Pandangan produk|
|2|07-23-2022 10:05:00|abc123|707|Daftar masuk kesetiaan|
|3|07-23-2022 10:10:00|abc123|707|Daftar Keluar|
|4|07-23-2022 10:20:00|xyz789|--|Pandangan produk|

## <a name="data-ingestion"></a>Pengingesan data

Data mengenai pelanggan boleh berasal dari laman web anda sebagai data acara dan ia boleh disimpan dalam perkhidmatan analisis data dalaman atau pihak ketiga anda sendiri. Data web mengandungi pengguna yang diketahui dan tidak diketahui jika laman web mempunyai aliran pengesahan yang berintegrasi dengan perkhidmatan pengesahan. Sebagai contoh, sistem eCommerce yang memerlukan pengguna memberikan butiran lengkap mereka untuk menyelesaikan transaksi pembelian. Atau sistem kesetiaan yang memerlukan pengesahan untuk mengesahkan penerima sah diskaun ganjaran.

Data peristiwa dalam contoh kami di atas mengandungi ID profil yang berbeza bagi pengguna yang diketahui dan tidak diketahui. Sekiranya 1 dan 4, pengguna tidak diketahui semasa dalam peristiwa 2 dan 3 pengguna dengan ID abc123 mendaftar ke program kesetiaan.

:::image type="content" source="media/website-data-source.png" alt-text="Sumber data termasuk laman web Contoso.":::

Untuk maklumat lanjut tentang opsyen yang tersedia untuk pengingesan data, lihat [Gambaran keseluruhan sumber data](data-sources.md).

## <a name="data-unification"></a>Penyatuan data

Penumpuan identiti yang tidak diketahui dengan identiti yang diketahui membantu membolehkan pemperibadian berdasarkan tingkah laku pengguna, tanpa mengira keadaan profil mereka (dikenali atau tidak diketahui). Kandungan diperibadikan untuk semua pengguna membantu pelanggan dengan cepat mendapatkan produk atau perkhidmatan yang paling relevan yang mereka minati pada masa itu.

Memandangkan sesetengah pengguna dalam data kami diketahui, kami boleh menggunakan Wawasan Pelanggan untuk menggabungkan data tersebut dengan profil pengguna. Untuk maklumat lanjut tentang menyatukan profil pelanggan, lihat [Gambaran keseluruhan penyatuan data](data-unification.md).

1. Pilih medan sumber daripada entiti data web. Gunakan data profil yang disimpan dalam data web anda dan pilih medan yang mewakili Id dengan data demografi.

   :::image type="content" source="media/website-source-fields.png" alt-text="Medan sumber untuk sumber data web.":::

1. Tambah peraturan untuk menggabungkan rekod pendua. Untuk data web, pilih data yang paling banyak diisi.

1. Konfigurasikan peraturan dan syarat perlawanan. Data peristiwa profil web dalam contoh ini akan dipadankan pada ID dengan profil daripada sumber data lain yang mengandungi maklumat pelanggan. Sediakan peraturan padanan yang tepat pada ID sebagai peraturan berasingan dengan setiap entiti profil lain yang mempunyai padanan kunci utama atau ID yang sepadan. Dalam contoh, data profil peristiwa web digunakan sebagai entiti padanan terakhir supaya data profil lain digabungkan terlebih dahulu.
   1. Tidak menyemak **Termasuk semua rekod** mencipta profil bersatu untuk pengguna yang diketahui dan termasuk ID pengguna yang tidak diketahui yang sepadan. Ia berguna dalam senario apabila anda berminat untuk melihat aktiviti tingkah laku masa lalu pengguna yang diketahui ketika mereka masih belum diketahui.
   1. Menyemak **Termasuk Semua rekod** mencipta rekod profil berasingan untuk pengguna yang tidak diketahui. Pengguna yang tidak diketahui mendapat ID pelanggan yang unik. Pada masa akan datang apabila profil yang diketahui dikaitkan dalam data profil acara web, maka perjalanan pengguna yang baru diketahui boleh dilihat dan digunakan untuk pemperibadian berdasarkan data tingkah laku yang tidak diketahui juga.

:::image type="content" source="media/website-match-rule.png" alt-text="Peraturan padanan untuk entiti sumber data laman web.":::

## <a name="get-insights"></a>Dapatkan wawasan

Jika profil pelanggan dicipta untuk pengguna yang tidak diketahui dan diketahui, data peristiwa web bernilai tinggi boleh digunakan sebagai [aktiviti](activities.md). Aktiviti ini boleh digunakan untuk mencipta lebih banyak cerapan. Sebagai contoh, pelanggan yang melawat laman web enam bulan yang lalu (ketika mereka masih tidak diketahui) atau pelanggan yang tidak mempunyai ID kesetiaan tidak pernah menyelesaikan pembayaran.

:::image type="content" source="media/website-known-unknown.png" alt-text="Petikan skrin halaman pelanggan dengan pelanggan yang diketahui dan tidak diketahui.":::

[Memperkayakan](enrichment-hub.md) data anda, membina [langkah-langkah](measures.md), dan membuat [segmen](segments.md) untuk pengaktifan selanjutnya.

Sebagai contoh, anda boleh membuat segmen pengguna terkenal yang melihat beberapa produk tetapi tidak pernah menyelesaikan pembayaran.

Untuk maklumat lanjut, lihat [Gambaran keseluruhan segmen](segments.md).

## <a name="activate-insights"></a>Aktifkan cerapan

Terdapat beberapa cara untuk mengeksport data anda dan mengambil tindakan berdasarkan cerapan asas.

Untuk maklumat lanjut, lihat [Gambaran keseluruhan eksport](export-destinations.md).
