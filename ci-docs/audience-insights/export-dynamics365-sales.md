---
title: Eksport data Customer Insights ke Dynamics 365 Sales
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643829"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Penyambung untuk Dynamics 365 Sales (pratonton)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.

## <a name="prerequisite"></a>Prasyarat

Rekod kenalan [daripada Dynamics 365 Sales yang diinges menggunakan Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>Konfigur penyambung untuk Jualan

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Di bawah **Dynamics 365 Sales**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

1. Masukkan URL Jualan organisasi anda dalam medan **Alamat pelayan**.

1. Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Sales.

1. Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.

1. Pilih **Seterusnya**.

1. Pilih satu atau lebih segmen.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).
