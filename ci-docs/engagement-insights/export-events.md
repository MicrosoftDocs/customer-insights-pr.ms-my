---
title: Eksport peristiwa diperhalus
description: Cara mengeksport peristiwa diperhalus dan peristiwa asas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032396"
---
# <a name="export-events"></a>Eksport peristiwa

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Peristiwa mewakili tingkah laku pengguna. Peristiwa merekodkan apabila pengguna melihat halaman (peristiwa pandangan) atau berinteraksi dengan kandungan (peristiwa tindakan). Apabila anda boleh membuat keputusan sifat data yang anda mahu paparkan dalam laporan, pandangan maya data ini dipanggil *peristiwa diperhalus*. 

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

Terdapat dua cara untuk mengeksport peristiwa: 
- Pergi ke **Data** > **Eksport** dan pilih **Eksport baharu**.
- Pergi ke **Data** > **Peristiwa**, pilih **Lagi [...]** di sebelah peristiwa yang mahu anda eksport dan pilih **Eksport** daripada menu juntai bawah. 

Anda akan dibimbing melalui langkah untuk mencipta eksport:

1. Berikan **Nama eksport**.

1. Dalam senarai juntai bawah **Pilihan peristiwa**, pilih peristiwa asas dan peristiwa diperhalus untuk disertakan dalam eksport. 

1. Di bawah **Struktur fail**, pilih kadens untuk mencipta fail baharu dalam storan destinasi. Peristiwa dieksport secara berterusan apabila ia tiba.

1. Pilih format untuk eksport anda. Anda boleh memilih antara format **Common Data Model**, **CSV** dan **JSON**. Untuk menggunakan eksport dengan aplikasi Dynamics 365 yang lain, kami mengesyorkan menggunakan format Common Data Model.

1. Dalam langkah **Pilih destinasi**, tentukan lokasi Azure Data Lake Storage Gen 2.
    1. **Nama akaun ADLS gen 2** ialah nama akaun storan yang anda mahu simpan eksport. 
    1. **Laluan folder** mentakrifkan tempat eksport perlu disimpan dalam sistem fail dan struktur direktori akaun storan.
    1. **Kunci berkongsi** tersedia daripada portal Azure untuk akaun storan.

1. Semak dan sahkan pilihan anda.

## <a name="view-and-manage-exports"></a>Lihat dan urus eksport

Sebaik sahaja anda menyediakan eksport, pergi ke **Data** > **Eksport** untuk melihatnya. Pilih **Lebih banyak [...]** bagi sebarang eksport sedia ada untuk mengedit atau memadamkannya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]