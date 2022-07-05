---
title: Bekerja dengan akaun perniagaan
description: Ketahui tentang akaun perniagaan sebagai khalayak sasaran utama dalam Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: 9bf91671b744198b2f37391edc7abf58eca3c820
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053124"
---
# <a name="work-with-business-accounts"></a>Bekerja dengan akaun perniagaan

Ini Dynamics 365 Customer Insights membolehkan anda mengkonfigurasi persekitaran anda untuk khalayak sasaran utama yang berbeza: pengguna individu (B-to-C) dan akaun perniagaan (B-to-B). Dalam senario niaga-ke-pengguna, data berpusat di sekitar individu. Untuk niaga-ke-niaga, khalayak sasaran utama ialah akaun – organisasi atau syarikat - dan kenalan. Artikel ini membantu anda bermula dengan persekitaran untuk akaun perniagaan. Ia menyenaraikan perbezaan untuk kawasan ciri dalam Wawasan Pelanggan, bergantung pada fokus persekitaran anda. Untuk maklumat lanjut tentang perbezaan, semak dokumen kawasan ciri. 

## <a name="create-an-environment-for-business-accounts"></a>Cipta persekitaran untuk akaun perniagaan

Pentadbir boleh [mencipta persekitaran dalam organisasi sedia ada](create-environment.md). Langkah dalam proses mencipta persekitaran baharu yang meminta pentadbir untuk khalayak sasaran utama persekitaran. Sekiranya ia adalah persediaan awal selepas membeli lesen, pengalaman berpandu membantu dengan penciptaan persekitaran pertama.

Anda boleh kemudian [menginjes data](data-sources.md) untuk akaun perniagaan dan kenalan yang berkaitan sebagai sumber data dari semua sumber yang disokong.

Selepas menyatukan data, [tentukan hierarki akaun](relationships.md#set-up-account-hierarchies) sebagai sebahagian daripada konfigurasi perhubungan. Anda juga boleh [mengkonfigurasi pemetaan semantik](semantic-mappings.md) untuk menyambungkan entiti kenalan dan akaun. 

## <a name="switch-between-primary-target-audience"></a>Tukar antara khalayak sasaran utama

Jika organisasi anda mengekalkan persekitaran untuk pelanggan individu dan akaun perniagaan, anda boleh menggunakan penukar dalam tetingkap kiri untuk memilih khalayak sasaran utama.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Penukar untuk mengubah khalayak sasaran utama antara pelanggan individu dan akaun perniagaan.":::

## <a name="supported-feature-areas"></a>Kawasan ciri yang disokong

- [Aktiviti](activities.md): Sokongan untuk akaun dan kenalan berkaitan untuk mencipta aktiviti dan menunjukkannya dalam garis masa.
- [Perhubungan](relationships.md): Wizard aktiviti membantu mencipta perhubungan antara entiti supaya pandangan akaun boleh menunjukkan semua aktiviti daripada kenalan. Kenalan boleh menggerudi untuk melihat kenalan pandangan dan hierarki boleh digunakan untuk pengagregatan aktiviti akaun.
- [Ukuran](measures.md): Menyokong ukuran yang dicipta daripada pembina ukuran dengan satu pengiraan. Tetapan pilihan membenarkan gulungan untuk sub akaun apabila mencipta ukuran.
- [Segmen](segments.md): Menyokong segmen yang dicipta dari awal dengan pembina segmen. Pengendali baharu membenarkan penggabungan hierarki akaun apabila membina segmen.
- [Data diinjes](data-sources.md): Semua ciri dalam kawasan ini adalah sama untuk akaun perniagaan dan pelanggan individu.
- [Data penyatuan](data-unification.md): Semua ciri dalam kawasan ini adalah sama untuk akaun perniagaan dan pelanggan individu.
- [Pengayaan](enrichment-hub.md): Sesetengah jenis pengayaan tersedia hanya untuk senario pelanggan individu sementara yang lain tersedia secara eksklusif untuk akaun perniagaan.
- [Ramalan dan model di luar kotak](predictions-overview.md): Ramalan pulangan transaksi mengandungi langkah tambahan untuk akaun perniagaan. Ramalan lain hanya tersedia untuk pelanggan individu.
- [Pengaktifan dan eksport](export-destinations.md): Eksport tersedia untuk akaun perniagaan dan pelanggan individu. Sesetengah eksport memerlukan konfigurasi tambahan dan maklumat kenalan diunjurkan dalam segmen dasar untuk menjadi sah untuk akaun perniagaan.
- [Tetapan sistem](system.md) dan [pengurusan pengguna](permissions.md): Semua ciri dalam kawasan ini adalah sama untuk akaun perniagaan dan pelanggan individu.

