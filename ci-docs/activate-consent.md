---
title: Aktifkan peraturan persetujuan untuk segmen
description: Ikuti langkah-langkah ini untuk memautkan data persetujuan dan mengaktifkan semakan persetujuan dalam Dynamics 365 Customer Insights. Pentadbir juga boleh menyahdayakan semakan persetujuan.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755181"
---
# <a name="activate-consent-rules"></a>Aktifkan peraturan persetujuan

[Pusat Persetujuan (pratonton)](consent-management/overview.md) membantu anda mengharmonikan data persetujuan daripada pelbagai sumber. Gunakan entiti Persetujuan *bersatu* untuk menggunakan semakan persetujuan lalai. Selepas mengimport data persetujuan dan mengkonfigurasi peraturan peta, *entiti Persetujuan* disegerakkan secara automatik ke Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Dayakan semakan persetujuan

Dengan data persetujuan yang diimport ke Pusat Persetujuan (pratonton) dan peraturan yang disediakan, anda boleh mendayakan semakan persetujuan. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Tab persetujuan dalam seting Wawasan Pelanggan dengan data persetujuan yang diaktifkan.":::

1. Dalam Customer Insights, pergi ke **Pentadbir** > **Sistem**.

1. **Pilih tab Persetujuan (pratonton**).

1. **Dalam seksyen Dayakan semakan** persetujuan, setkan togol kepada **Hidup** untuk semua kawasan yang anda ingin dayakan.

1. **Pilih kotak semak Benarkan penggantian peraturan** persetujuan lalai untuk mengalih keluar semakan persetujuan lalai yang dikuatkuasakan pada segmen tertentu. 

1. Dalam menu juntai bawah, pilih tempat yang anda mahu benarkan penggantian.     

1. **Dalam seksyen Pautkan persetujuan kepada profil** pelanggan, pilih atribut yang digunakan sebagai pengecam untuk memautkan data persetujuan kepada data pelanggan. Ia mungkin akan menjadi nombor telefon atau alamat e-mel. 

1. Pilih **Simpan** untuk menggunakan seting anda.

## <a name="disable-consent-checks"></a>Lumpuhkan semakan persetujuan

Untuk berhenti menggunakan data persetujuan dalam Wawasan Pelanggan, pentadbir perlu mengemas kini seting sistem dengan sewajarnya.

1. Dalam Customer Insights, pergi ke **Pentadbir** > **Sistem**.

1. **Pilih tab Persetujuan (pratonton**).

1. **Dalam seksyen Dayakan semakan** persetujuan, setkan togol kepada **Mati**.

> [!TIP]
> Untuk berhenti menggunakan keupayaan pengurusan persetujuan, lihat [Seting sistem dalam Pusat Persetujuan (pratonton)](consent-management/system-settings.md).
