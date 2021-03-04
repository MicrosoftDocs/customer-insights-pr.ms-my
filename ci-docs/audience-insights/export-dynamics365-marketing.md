---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269065"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Penyambung untuk Dynamics 365 Marketing (pratonton)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing. Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Prasyarat

- Rekod kenalan mesti wujud dalam Dynamics 365 Marketing sebelum anda boleh mengeksport segmen daripada Customer Insights ke Pemasaran. Baca lebih lanjut tentang cara untuk menginges kenalan dalam [Dynamics 365 Marketing menggunakan Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Mengeksport segmen daripada wawasan khalayak kepada Pemasaran tidak akan mencipta rekod kenalan baharu dalam tika Pemasaran. Rekod kenalan daripada Pemasaran mesti diinges dalam wawasan khalayak dan digunakan sebagai sumber data. Mereka juga perlu dimasukkan dalam entiti Pelanggan disatukan untuk memetakan ID pelanggan kepada ID kenalan sebelum segmen boleh dieksport.

## <a name="configure-the-connector-for-marketing"></a>Konfigur penyambung untuk Pemasaran

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Di bawah **Dynamics 365 Marketing**, pilih **Sediakan**.

1. Berikan destinasi eksport anda nama yang mudah dikenali dalam medan **Nama paparan**.

1. Masukkan URL Pemasaran organisasi anda dalam medan **Alamat pelayan**.

1. Dalam bahagian **Akaun pentadbir pelayan**, pilih **Daftar masuk** dan pilih akaun Dynamics 365 Marketing.

1. Petakan medan ID pelanggan ke ID Kenalan Dynamics 365.

1. Pilih **Seterusnya**.

1. Pilih satu atau lebih segmen.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]