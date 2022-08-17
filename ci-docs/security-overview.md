---
title: Konfigurasikan seting keselamatan
description: Ketahui tentang seting keselamatan dalam Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ea21163d7dd05370de28ca8340ae9583846adb26
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246073"
---
# <a name="configure-security-settings"></a>Konfigurasikan seting keselamatan

Urus kekunci API, akses data pelanggan dan sediakan Pautan Peribadi Azure.

## <a name="manage-api-keys"></a>Urus kekunci API

Lihat dan urus kekunci untuk menggunakan [API](apis.md) Wawasan Pelanggan dengan data dalam persekitaran anda.

1. Pergi ke **Keselamatan** > **Sistem** dan pilih **tab API**.

1. Jika capaian API ke persekitaran belum disediakan, pilih **Dayakan**. Atau, untuk menyekat akses API ke persekitaran, pilih **Lumpuhkan** dan sahkan.

1. Uruskan kekunci API utama dan sekunder:

   1. Untuk menunjukkan kekunci API utama atau sekunder, pilih **simbol Tunjukkan**.

   1. Untuk menyalin kekunci API utama atau sekunder, pilih **simbol Salin**.

   1. Untuk mencipta kekunci API primer atau sekunder baru, pilih **Jana Semula primer** atau **Jana Semula sekunder**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Akses data pelanggan dengan selamat dengan Peti Kunci Pelanggan (Pratonton)

Wawasan Pelanggan menggunakan Power Platform keupayaan Peti Kunci Pelanggan. Kotak Kunci Pelanggan menyediakan antara muka untuk menyemak dan meluluskan (atau menolak) permintaan akses data. Permintaan ini berlaku apabila akses data kepada data pelanggan diperlukan untuk menyelesaikan kes sokongan. Untuk menggunakan ciri ini, Wawasan Pelanggan mesti mempunyai sambungan sedia ada ke Microsoft Dataverse persekitaran dalam penyewa anda.

Untuk maklumat lanjut tentang Peti Kunci Pelanggan, lihat [ringkasan](/power-platform/admin/about-lockbox#summary)Power Platform Peti Kunci Pelanggan. Artikel ini juga menerangkan [aliran kerja](/power-platform/admin/about-lockbox#workflow) dan persediaan [yang diperlukan](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) untuk mendayakan Kotak Kunci Pelanggan.

> [!IMPORTANT]
> Pentadbir global untuk Power Platform atau Power Platform pentadbir boleh meluluskan permintaan Kotak Kunci Pelanggan yang dikeluarkan untuk Wawasan Pelanggan.

## <a name="set-up-an-azure-private-link"></a>Sediakan Pautan Peribadi Azure

[Azure Private Link](/azure/private-link/private-link-overview) mari kita Wawasan Pelanggan menyambung ke akaun anda Azure Data Lake Storage melalui titik akhir peribadi dalam rangkaian maya anda. Untuk data dalam akaun storan, yang tidak terdedah kepada internet awam, Pautan Peribadi mendayakan sambungan ke rangkaian terhad tersebut.

> [!IMPORTANT]
> Keperluan peranan minimum untuk menyediakan sambungan Pautan Peribadi:
>
> - Wawasan Pelanggan: Pentadbir
> - Azure terbina dalam role: [Penyumbang Akaun Storan](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Keizinan untuk peranan Azure tersuai: [Microsoft.Storage/storageAccounts/read dan Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Dalam Wawasan Pelanggan, pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **Pautan Peribadi**.

1. Pilih **Tambah Pautan Peribadi**.

   Anak **tetingkap Tambah Pautan Peribadi** menyenaraikan akaun storan daripada penyewa anda yang anda mempunyai keizinan untuk dilihat.

1. Pilih langganan, kumpulan sumber dan akaun storan.

1. [Semak privasi dan pematuhan](connections.md#data-privacy-and-compliance) data dan pilih **Saya bersetuju**.

1. Pilih **Simpan**.

1. Pergi ke akaun Penyimpanan Tasik Data anda dan buka pautan yang dipaparkan pada skrin.

1. Luluskan Pautan Peribadi.


[!INCLUDE [footer-include](includes/footer-banner.md)]
