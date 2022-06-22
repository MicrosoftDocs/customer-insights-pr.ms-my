---
title: Seting keselamatan dalam Wawasan Pelanggan
description: Ketahui tentang seting keselamatan dalam Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947426"
---
# <a name="security-settings-in-customer-insights"></a>Seting keselamatan dalam Wawasan Pelanggan

Halaman **Keselamatan** menyenaraikan opsyen untuk mengkonfigurasi keizinan pengguna dan ciri yang membantu menjadikan Dynamics 365 Customer Insights lebih selamat. Hanya pentadbir boleh mencapai halaman ini.

Pergi ke **Keselamatan** > **Pentadbir** untuk mengkonfigurasi seting.

Halaman **Keselamatan** termasuk tab berikut:

- [Pengguna](#users-tab)
- [API](#apis-tab)
- [Pautan Peribadi](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [Akses data pelanggan dengan selamat dengan Kotak Kunci Pelanggan (Pratonton)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Tab Pengguna

Akses kepada Wawasan Pelanggan adalah terhad kepada pengguna dalam organisasi anda yang telah ditambahkan pada aplikasi oleh pentadbir. Tab **Pengguna** membolehkan anda menguruskan akses pengguna dan keizinan mereka. Untuk maklumat lanjut, lihat [Keizinan pengguna](permissions.md).

## <a name="apis-tab"></a>Tab API

Lihat dan urus kunci untuk menggunakan [API](apis.md) Wawasan Pelanggan dengan data persekitaran anda.

Anda boleh mencipta kekunci primer dan sekunder baru dengan **memilih Jana Semula primer** atau **Jana Semula sekunder**. 

Untuk menyekat akses API ke persekitaran, pilih **Lumpuhkan**. Jika API dinyahdayakan, anda boleh memilih **Dayakan** untuk memberikan capaian sekali lagi.

## <a name="private-links-tab"></a>Tab Pautan Peribadi

[Azure Private Link](/azure/private-link/private-link-overview) mari kita Wawasan Pelanggan menyambung ke akaun anda Azure Data Lake Storage melalui titik akhir peribadi dalam rangkaian maya anda. Untuk data dalam akaun storan, yang tidak terdedah kepada internet awam, Private Link mendayakan sambungan ke rangkaian terhad tersebut.

> [!IMPORTANT]
> Keperluan peranan minimum untuk menyediakan sambungan Pautan Peribadi:
>
> - Wawasan Pelanggan: Pentadbir
> - Peranan terbina dalam Azure: [Penyumbang Akaun Storan](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Keizinan untuk peranan Azure tersuai: [Microsoft.Storage/storageAccounts/read dan Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Menyediakan Pautan Peribadi dalam Wawasan Pelanggan ialah proses dua langkah. Pertama, anda memulakan penciptaan Pautan Peribadi daripada **Pautan Peribadi Keselamatan** > **Pentadbir** > **dalam Wawasan** Pelanggan. Anak **tetingkap Tambah Pautan** Peribadi menyenaraikan akaun storan daripada penyewa anda yang anda mempunyai keizinan untuk melihat. Pilih akaun storan dan berikan persetujuan untuk mencipta Pautan Peribadi.

Seterusnya, anda perlu meluluskan Pautan Peribadi di bahagian akaun Data Lake Storage. Buka pautan yang dibentangkan pada skrin untuk meluluskan Pautan Peribadi baharu.

## <a name="key-vault-tab"></a>Tab Peti Besi Kekunci

Tab **Peti Besi** Kunci membolehkan anda memaut dan menguruskan peti besi [kunci Azure anda sendiri](/azure/key-vault/general/basic-concepts) ke persekitaran.
Key vault yang ditetapkan boleh digunakan untuk peringkat dan menggunakan rahsia dalam sempadan pematuhan organisasi. Wawasan Pelanggan boleh menggunakan rahsia dalam Azure Key Vault untuk [menyediakan sambungan](connections.md) ke sistem pihak ketiga.

Untuk maklumat lanjut, lihat [Bawa Azure key vault anda sendiri](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Akses data pelanggan dengan selamat dengan Kotak Kunci Pelanggan (Pratonton)

Wawasan Pelanggan menggunakan Power Platform keupayaan Kotak Kunci Pelanggan. Kotak Kunci Pelanggan menyediakan antara muka untuk menyemak dan meluluskan (atau menolak) permintaan capaian data. Permintaan ini berlaku apabila akses data kepada data pelanggan diperlukan untuk menyelesaikan kes sokongan. Untuk menggunakan ciri ini, Wawasan Pelanggan mesti mempunyai sambungan sedia ada ke Microsoft Dataverse persekitaran dalam penyewa anda.

Untuk maklumat lanjut tentang Kotak Kunci Pelanggan, lihat [ringkasan](/power-platform/admin/about-lockbox#summary)Power Platform Kotak Kunci Pelanggan. Artikel ini juga menerangkan [aliran kerja](/power-platform/admin/about-lockbox#workflow) dan persediaan [yang diperlukan](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) untuk mendayakan Kotak Kunci Pelanggan.

> [!IMPORTANT]
> Pentadbir global untuk Power Platform atau Power Platform pentadbir boleh meluluskan permintaan Peti Kunci Pelanggan yang dikeluarkan untuk Wawasan Pelanggan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
