---
title: Penyambung Power Apps (pratonton)
description: Sambung dengan Power Apps and Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055271"
---
# <a name="power-apps-connector-preview"></a>Penyambung Power Apps (pratonton)

Bawa profil pelanggan disatukan ke dalam aplikasi diperibadikan anda Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Sambung Power Apps dan Dynamics 365 Customer Insights

Customer Insights ialah salah satu daripada banyak [sumber yang tersedia untuk data dalam Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Rujuk kepada dokumentasi Power Apps untuk mengetahui cara untuk [menambah sambungan data kepada aplikasi](/powerapps/maker/canvas-apps/add-data-connection). Kami juga mengesyorkan anda mengulas [cara Power Apps menggunakan perwakilan untuk mengendalikan set data yang besar dalam aplikasi Kanvas](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entiti tersedia

Selepas menambah Customer Insights sebagai sambungan data, anda boleh memilih entiti berikut dalam Power Apps:

- **Pelanggan**: untuk menggunakan data daripada [profil pelanggan disatukan](customer-profiles.md).
- **UnifiedActivity** : untuk memaparkan [garis masa aktiviti](activities.md) dalam aplikasi.
- **ContactProfile** : untuk memaparkan kenalan pelanggan. Entiti ini hanya tersedia dalam persekitaran Wawasan Pelanggan untuk akaun perniagaan.

## <a name="limitations"></a>Batasan

### <a name="retrievable-entities"></a>Entiti boleh diperoleh

Anda hanya boleh mendapatkan **Pelanggan**, **UnifiedActivity**, **Segmen**, dan entiti **ContactProfile** melalui penyambung Power Apps. ContactProfile hanya tersedia dalam contoh Wawasan Pelanggan untuk akaun perniagaan. Entiti lain ditunjukkan kerana penyambung asas menyokongnya melalui pencetus dalam Power Automate.

Anda boleh melakukan maksimum 100 panggilan setiap 60 saat. Anda boleh memanggil titik akhir API beberapa kali dengan menggunakan parameter $skip. [Ketahui lebih lanjut tentang parameter $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Perwakilan

Penugasan berfungsi untuk entiti **Pelanggan** dan entiti **UnifiedActivity**. 

- Delegasi untuk entiti **Pelanggan**: Untuk menggunakan delegasi untuk entiti ini, medan perlu diindeks dalam [Indeks carian & penapis](search-filter-index.md).  
- Penugasan untuk **Aktiviti Disatukan**: Penugasan untuk entiti ini hanya berfungsi untuk medan **ActivityId** dan **CustomerId**.  
- Penugasan untuk **ContactProfile**: Penugasan untuk entiti ini hanya berfungsi untuk medan **Contactid** dan **CustomerId**. ContactProfile hanya tersedia dalam persekitaran Wawasan Pelanggan untuk akaun perniagaan.

Untuk maklumat lanjut tentang penugasan pergi ke [Fungsi dan operasi yang ditugaskan Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Contoh kawalan galeri

Anda boleh menambahkan profil pelanggan ke [kawalan galeri](/powerapps/maker/canvas-apps/add-gallery).

1. Tambah kawalan **galeri** kepada aplikasi yang anda sedang bina.

    > [!div class="mx-imgBorder"]
    > ![Tambah elemen galeri.](media/connector-powerapps9.png "Tambah elemen galeri.")

2. Pilih **Pelanggan** sebagai sumber data untuk item.

    > [!div class="mx-imgBorder"]
    > ![Pilih sumber data.](media/choose-datasource-powerapps.png "Pilih sumber data.")

3. Anda boleh mengubah panel data pada bahagian kanan untuk memilih medan bagi entiti Pelanggan untuk ditunjukkan pada galeri.

4. Jika anda mahu menunjukkan sebarang medan daripada pelanggan yang dipilih pada galeri, isikan sifat **Teks** penggunaan label **{Name_of_the_gallery}.Dipilih.{property_name}**  
    - Contoh: _Gallery1.Selected.address1_city_

5. Untuk memaparkan garis masa disatukan untuk pelanggan, tambah elemen galeri, dan tambah sifat **Item** menggunakan **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Contoh: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
