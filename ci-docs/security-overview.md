---
title: Seting keselamatan dalam Dynamics 365 Customer Insights
description: Ketahui tentang seting keselamatan dalam Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653814"
---
# <a name="security-overview-page"></a>Halaman gambaran keseluruhan keselamatan

Halaman **Keselamatan** menyenaraikan opsyen untuk mengkonfigurasi keizinan pengguna dan ciri yang membantu menjadikan Dynamics 365 Customer Insights lebih selamat. Hanya pentadbir boleh mencapai halaman ini. 

Pergi ke **AdminSecurity** > **untuk** mengkonfigurasi seting.

Halaman **Keselamatan** termasuk tab berikut:
- [Pengguna](#users-tab)
- [API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>Tab Pengguna

Akses kepada Wawasan Pelanggan adalah terhad kepada pengguna dalam organisasi anda yang telah ditambahkan pada aplikasi oleh pentadbir. Tab **Pengguna** membolehkan anda menguruskan akses pengguna dan keizinan mereka. Untuk maklumat lanjut, lihat [Keizinan pengguna](permissions.md).

## <a name="apis-tab"></a>Tab API

Lihat dan urus kunci untuk menggunakan [API](apis.md) Wawasan Pelanggan dengan data persekitaran anda.

Anda boleh mencipta kekunci primer dan sekunder baru dengan **memilih Jana Semula primer** atau **Jana Semula sekunder**. 

Untuk menyekat akses API ke persekitaran, pilih **Lumpuhkan**. Jika API dinyahdayakan, anda boleh memilih **Dayakan** untuk memberikan capaian sekali lagi.

## <a name="key-vault-tab"></a>Tab Peti Besi Kekunci

Tab **Peti Besi** Kunci membolehkan anda memaut dan menguruskan peti besi [kunci Azure anda sendiri](/azure/key-vault/general/basic-concepts) ke persekitaran.
Key vault yang ditetapkan boleh digunakan untuk peringkat dan menggunakan rahsia dalam sempadan pematuhan organisasi. Wawasan Pelanggan boleh menggunakan rahsia dalam Azure Key Vault untuk [menyediakan sambungan](connections.md) ke sistem pihak ketiga.

Untuk maklumat lanjut, lihat [Bawa Azure key vault anda sendiri](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
