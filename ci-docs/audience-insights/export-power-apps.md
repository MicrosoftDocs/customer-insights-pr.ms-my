---
title: Penyambung Power Apps
description: Sambung dengan Power Apps and Power Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406436"
---
# <a name="microsoft-power-apps-connector-preview"></a>Penyambung Microsoft Power Apps (pratonton)

Bawa profil pelanggan disatukan ke dalam aplikasi diperibadikan anda Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Sambung Power Apps dan Dynamics 365 Customer Insights

Customer Insights ialah salah satu daripada banyak [sumber yang tersedia untuk data dalam Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

Rujuk kepada dokumentasi Power Apps untuk mengetahui cara untuk [menambah sambungan data kepada aplikasi](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). Kami juga mengesyorkan anda mengulas [cara Power Apps menggunakan perwakilan untuk mengendalikan set data yang besar dalam aplikasi Kanvas](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entiti tersedia

Selepas menambah Customer Insights sebagai sambungan data, anda boleh memilih entiti berikut dalam Power Apps:

- Pelanggan: untuk menggunakan data daripada [profil pelanggan disatukan](customer-profiles.md).
- Aktiviti Pelanggan Disatukan: untuk memaparkan [garis masa](activities.md) pada aplikasi.

## <a name="limitations"></a>Had

### <a name="retrievable-entities"></a>Entiti boleh diperoleh

Anda hanya boleh memperoleh entiti **Pelanggan**, **Aktiviti Disatukan** dan **Segmen** melalui penyambung Power Apps. Entiti lain ditunjukkan kerana penyambung asas menyokongnya melalui pencetus dalam Power Automate.  

### <a name="delegation"></a>Perwakilan

Kerja penugasan untuk entiti Pelanggan dan entiti Aktiviti Disatukan. 

- Delegasi untuk entiti **Pelanggan**: Untuk menggunakan delegasi untuk entiti ini, medan perlu diindeks dalam [Indeks carian & penapis](search-filter-index.md).  

- Penugasan untuk **Aktiviti Disatukan**: Penugasan untuk entiti ini hanya berfungsi untuk medan **ActivityId** dan **CustomerId**.  

- Untuk maklumat lanjut tentang penugasan, lihat [Fungsi dan operasi boleh ditugaskan Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Contoh kawalan galeri

Sebagai contoh, anda menambahkan profil pelanggan ke [kawalan galeri](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. Tambah kawalan **Galeri** kepada aplikasi yang anda sedang bina.

> [!div class="mx-imgBorder"]
> ![Tambah elemen galeri](media/connector-powerapps9.png "Tambah elemen galeri")

1. Pilih **Pelanggan** sebagai sumber data untuk item.

    > [!div class="mx-imgBorder"]
    > ![Pilih sumber data](media/choose-datasource-powerapps.png "Pilih sumber data")

1. Anda boleh mengubah panel data pada bahagian kanan untuk memilih medan bagi entiti Pelanggan untuk ditunjukkan pada galeri.

1. Jika anda mahu menunjukkan mana-mana medan daripada pelanggan terpilih pada galeri, isikan sifat Teks bagi label:  **{Name_of_the_gallery}.Selected.{property_name}**

    Contoh: Gallery1.Selected.address1_city

1. Untuk memaparkan garis masa yang disatukan untuk pelanggan, tambahan elemen Galeri dan tambahkan sifat Item: **Penapis('UnifiedActivity', CustomerId = {Customer_Id})**

    Contoh: Penapis('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)
