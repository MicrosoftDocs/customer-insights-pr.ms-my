---
title: Eksport data Customer Insights ke Dynamics 365 Sales
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269019"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Penyambung untuk Dynamics 365 Sales (pratonton)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan data pelanggan anda untuk mencipta senarai pemasaran, menyusuli aliran kerja dan menghantar promosi dengan Dynamics 365 Sales.

## <a name="prerequisite"></a>Prasyarat

1. Rekod kenalan mesti wujud dalam Dynamics 365 Sales sebelum anda boleh mengeksport segmen daripada Customer Insights ke Jualan. Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Sales menggunakan Common Data Services](connect-power-query.md).

   > [!NOTE]
   > Mengeksport segmen daripada wawasan khalayak kepada Jualan tidak akan mencipta rekod kenalan baharu dalam tika Jualan. Rekod kenalan daripada Jualan mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data. Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]