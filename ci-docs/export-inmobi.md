---
title: Eksport data Wawasan Pelanggan ke InMobi
description: Ketahui cara mengkonfigurasi sambungan dan eksport ke InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059615"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Eksport senarai segmen dan data lain ke InMobi (pratonton)

Eksport senarai segmen atau data lain daripada contoh Wawasan Pelanggan anda ke [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Prasyarat

1. Anda mempunyai [akaun](https://www.inmobi.com/) InMobi dan kelayakan pentadbir.
1. Anda mempunyai nama akaun storan Azure Blob dan kunci akaun yang sepadan. Untuk maklumat lanjut, lihat [Menguruskan seting akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage). Terdapat bekas dalam akaun storan untuk mengeksport data dalamMobi. Untuk maklumat lanjut, lihat [Mencipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi akan mencipta sambungan terus ke Storan Blob anda, dan mengkonfigurasi import automatik data anda ke InMobi. Hubungi wakil InMobi anda untuk memulakan proses.

## <a name="known-limitations"></a>Had diketahui

1. Untuk Azure Blob Storage, anda boleh memilih antara [prestasi Standard dan peringkat](/azure/storage/blobs/storage-blob-performance-tiers) prestasi Premium. Jika anda memilih tingkat prestasi Premium, pilih [blob blok premium sebagai jenis akaun](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Sediakan sambungan ke Azure Blob Storage dan konfigurasikan eksport

1. Ikut arahan untuk [menyediakan sambungan ke Storan](export-azure-blob-storage.md) Azure Blob anda.
2. Ikut arahan untuk [mengkonfigurasi eksport](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
