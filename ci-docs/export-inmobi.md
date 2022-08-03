---
title: Eksport data Wawasan Pelanggan ke InMobi
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195899"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Eksport data Wawasan Pelanggan ke InMobi (pratonton)

Eksport senarai segmen atau data lain daripada contoh Wawasan Pelanggan anda ke [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Prasyarat

- Akaun [InMobi](https://www.inmobi.com/) dan kelayakan pentadbir.
- [Nama akaun](/azure/storage/blobs/create-data-lake-storage-account) Azure Blob Storage dan kunci akaun. Untuk mencari nama dan kunci, lihat [Menguruskan tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
- Bekas [Storan](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) Azure Blob untuk mengeksport data InMobi.
- InMobi akan mencipta sambungan terus ke Storan Blob anda, dan mengkonfigurasi import automatik data anda ke InMobi. Hubungi wakil InMobi anda untuk memulakan proses.

## <a name="known-limitations"></a>Had diketahui

- Untuk Azure Blob Storage, pilih antara [prestasi Standard dan peringkat prestasi Premium](/azure/storage/blobs/storage-blob-performance-tiers). Jika anda memilih tingkat prestasi Premium, pilih [blob blok premium sebagai jenis akaun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Sediakan sambungan ke Azure Blob Storage

[Sediakan sambungan ke Azure Blob Storage anda](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Konfigurasikan eksport

[Konfigurasikan eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
