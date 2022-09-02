---
title: Mengkonfigurasikan seting keselamatan
description: Ketahui tentang seting keselamatan dalam Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387260"
---
# <a name="configure-security-settings"></a>Mengkonfigurasikan seting keselamatan

Uruskan kekunci API, capai data pelanggan dan sediakan Pautan Peribadi Azure.

## <a name="manage-api-keys"></a>Uruskan kekunci API

Lihat dan uruskan kunci untuk menggunakan [API](apis.md) Wawasan Pelanggan dengan data dalam persekitaran anda.

1. Pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **API**.

1. Jika capaian API ke persekitaran belum disediakan, pilih **Dayakan**. Atau, untuk menyekat akses API kepada persekitaran, pilih **Nyahdayakan** dan sahkan.

1. Menguruskan kekunci API primer dan sekunder:

   1. Untuk menunjukkan kekunci API primer atau sekunder, pilih **Simbol Tunjukkan** .

   1. Untuk menyalin kekunci API primer atau sekunder, pilih **simbol Salin** .

   1. Untuk mencipta kekunci API primer atau sekunder baharu, pilih **Jana semula sekolah rendah** atau **jana semula sekunder**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Capai data pelanggan dengan Peti Kunci Pelanggan (Pratonton) dengan selamat

Wawasan Pelanggan menggunakan Power Platform keupayaan Kotak Kunci Pelanggan. Peti Kunci Pelanggan menyediakan antara muka untuk menyemak dan meluluskan (atau menolak) permintaan akses data. Permintaan ini berlaku apabila akses data kepada data pelanggan diperlukan untuk menyelesaikan kes sokongan. Untuk menggunakan ciri ini, Wawasan Pelanggan mesti mempunyai sambungan sedia ada kepada Microsoft Dataverse persekitaran dalam penyewa anda.

Untuk maklumat lanjut tentang Peti Kunci Pelanggan, lihat [ringkasan](/power-platform/admin/about-lockbox#summary) Power Platform Kotak Kunci Pelanggan. Artikel ini juga menerangkan [aliran kerja](/power-platform/admin/about-lockbox#workflow) dan persediaan [yang diperlukan](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) untuk mendayakan Peti Kunci Pelanggan.

> [!IMPORTANT]
> Pentadbir global untuk Power Platform atau Power Platform pentadbir boleh meluluskan permintaan Peti Kunci Pelanggan yang dikeluarkan untuk Wawasan Pelanggan.

## <a name="set-up-an-azure-private-link"></a>Menyediakan Pautan Peribadi Azure

[Azure Private Link](/azure/private-link/private-link-overview) membolehkan Wawasan Pelanggan menyambung ke akaun anda Azure Data Lake Storage melalui titik akhir peribadi dalam rangkaian maya anda. Untuk data dalam akaun storan, yang tidak terdedah kepada internet awam, Pautan Peribadi mendayakan sambungan ke rangkaian terhad tersebut.

> [!IMPORTANT]
> Keperluan peranan minimum untuk menyediakan sambungan Pautan Peribadi:
>
> - Wawasan Pelanggan: Pentadbir
> - Peranan terbina dalam Azure: [Penyumbang Akaun Storan](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Keizinan untuk peranan Azure tersuai: [Microsoft.Storage/storageAccounts/read dan Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Dalam Wawasan Pelanggan, pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **Pautan** Peribadi.

1. Pilih **Tambah Pautan Peribadi**.

   Anak **tetingkap Tambah Pautan** Persendirian menyenaraikan akaun storan daripada penyewa anda yang anda mempunyai keizinan untuk melihat.

1. Pilih langganan, kumpulan sumber dan akaun storan.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan**.

1. Pergi ke akaun Storan Tasik Data anda dan buka pautan yang dipaparkan pada skrin.

1. Luluskan Pautan Peribadi.


[!INCLUDE [footer-include](includes/footer-banner.md)]
