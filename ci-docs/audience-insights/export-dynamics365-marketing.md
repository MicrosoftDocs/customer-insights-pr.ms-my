---
title: Eksport data Customer Insights ke Dynamics 365 Marketing
description: Ketahui bagaimana mengkonfigur sambungan ke Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597614"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Penyambung untuk Dynamics 365 Marketing (pratonton)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Gunakan [segmen](segments.md) untuk menjana kumpulan tertentu kempen dan kenalan pelanggan dengan Dynamics 365 Marketing. Untuk maklumat lanjut, lihat [Gunakan segmen daripada Dynamics 365 Customer Insights dengan Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

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