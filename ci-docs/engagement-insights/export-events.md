---
title: Eksport peristiwa diperhalus
description: Cara mengeksport peristiwa diperhalus dan peristiwa asas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606245"
---
# <a name="export-events"></a>Eksport peristiwa

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Peristiwa mewakili tingkah laku pengguna. Peristiwa merekodkan apabila pengguna melihat halaman (peristiwa pandangan) atau berinteraksi dengan kandungan (peristiwa tindakan). Apabila anda boleh membuat keputusan sifat data yang anda mahu paparkan dalam laporan, pandangan maya data ini dipanggil *peristiwa diperhalus*. Untuk mendapatkan maklumat lanjut, lihat [Cipta dan mengubah suai segmen](refined-events.md).

- Anda boleh mengeksport peristiwa dan peristiwa diperhalus ke storan luaran. 
- Eksport merupakan strim data hadapan. Anda tidak boleh mengisi semula strim. 
- Eksport mempunyai skema tetap. Jika anda menambahkan sifat tersuai pada peristiwa, ia tidak akan disertakan. Anda perlu mencipta eksport baharu.

## <a name="prerequisites"></a>Prasyarat

Sebelum menyediakan eksport, anda perlu mempunyai akses dan langganan aktif pada portal Azure. Anda akan memerlukan maklumat akaun storan semasa proses eksport. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Cipta akaun Azure Data Lake Storage Gen 2

1. Log masuk ke portal Azure dan [cipta akaun storan baharu](/azure/storage/common/storage-account-create). 

1. Pastikan bahawa anda mendayakan **Ruang nama berhierarki** pada tab **Lanjutan**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Dayakan ruang nama berhierarki pada tab lanjutan.":::

1. Sebaik sahaja ia telah diatur letak, pergi ke akaun storan yang baru dicipta. Dalam anak tetingkap navigasi, pilih **Tetapan** > **Kunci akses**. 

1. Salin **Nama akaun** dan **Kunci** untuk menggunakannya apabila mencipta eksport baharu.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Kunci capaian dalam akaun storan.":::

## <a name="export-events"></a>Eksport peristiwa

Terdapat dua cara untuk membawa dialog **Peristiwa eksport**: 
- Pergi ke **Data** > **Eksport** dan pilih **Eksport baharu**.
- Pergi ke **Data** > **Peristiwa**, pilih **Lagi [...]** di sebelah peristiwa yang mahu anda eksport dan pilih **Eksport** daripada menu juntai bawah. 

:::image type="content" source="media/new-export.png" alt-text="Cipta eksport baharu.":::

Anda akan dibimbing melalui langkah untuk mencipta eksport:

1. Berikan **Nama eksport** dan kemudian pilih **Seterusnya**.

1. Dalam senarai juntai bawah **Pilihan peristiwa**, pilih peristiwa asas dan peristiwa diperhalus untuk disertakan dalam eksport. 

1. Dalam bahagian **Struktur fail**, pilih kadens (setiap jam atau harian) untuk mencipta fail baharu dalam storan destinasi dan kemudian pilih **Seterusnya**. Peristiwa dieksport secara berterusan apabila ia tiba.

1. Dalam dialog **Pilih format** pilih format untuk eksport anda. Pilih antara format **Common Data Model**, **CSV** dan **JSON**. Untuk menggunakan eksport dengan aplikasi Dynamics 365 lain, kami mengesyorkan format **Common Data Model**.

1. Dalam dialog **Pilih destinasi** nyatakan lokasi Azure Data Lake Storage Gen 2.
    1. **Nama akaun ADLS gen 2** ialah nama akaun storan yang anda mahu simpan eksport. 
    1. **Laluan folder** mentakrifkan tempat eksport perlu disimpan dalam sistem fail dan struktur direktori akaun storan.
    1. **Kunci berkongsi** tersedia daripada portal Azure untuk akaun storan.

1. Semak dan sahkan pilihan anda untuk menyelesaikan.

## <a name="view-and-manage-exports"></a>Lihat dan urus eksport

Sebaik sahaja anda menyediakan eksport, pergi ke **Data** > **Eksport** untuk melihatnya. Pilih **Lebih banyak [...]** bagi sebarang eksport sedia ada untuk mengedit atau memadamkannya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
