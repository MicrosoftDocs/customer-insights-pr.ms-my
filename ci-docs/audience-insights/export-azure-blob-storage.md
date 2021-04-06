---
title: Eksport data Customer Insights kepada storan Azure Blob
description: Ketahui bagaimana mengkonfigurasikan sambungan ke storan Blob Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596188"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Penyambung untuk storan Blob Azure (pratonton)

Simpan data Customer Insights anda dalam storan Azure Blob atau gunakannya untuk memindahkan data anda ke aplikasi lain.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Konfigur penyambung untuk storan Blob Azure

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Di bawah **Storan Blob Azure**, pilih **Sediakan**.

1. Masukkan **Nama akaun**, **Kekunci akaun**, dan **Bekas** untuk akaun storan Blob Azure anda.
    - Untuk mengetahui lanjut tentang cara mencari nama akaun dan kunci akaun storan Blob Azure, lihat [Urus tetapan akaun storan dalam portal Azure](/azure/storage/common/storage-account-manage).
    - Untuk mengetahui cara untuk mencipta bekas, lihat [Cipta bekas](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.

1. Pilih **Seterusnya**.

1. Pilih kotak di sebelah setiap entiti yang anda mahu eksport ke destinasi ini.

1. Pilih **Simpan**.

Data yang dieksport disimpan dalam bekas storan Blob Azure yang anda telah konfigur. Laluan folder berikut dicipta secara automatik dalam bekas anda:

- Untuk entiti sumber dan entiti yang dijana oleh sistem: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- model.json untuk entiti yang dieksport akan ditempatkan di peringkat %ExportDestinationName%
  - Contoh: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md#export-data-on-demand). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]