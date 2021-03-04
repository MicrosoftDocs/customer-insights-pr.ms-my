---
title: Perkayakan profil pelanggan disatukan
description: Gunakan keupayaan untuk memperkayakan data pelanggan anda.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269479"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan":::

Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk bekerja dengan pilihan pengayaan.    
Anda perlu mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan. Untuk maklumat lanjut, lihat [Keizinan](permissions.md).

Pada tab **Temui**, anda akan menemui pengayaan yang berikut:

- [Jenama](enrichment-microsoft-graph.md) disediakan oleh Microsoft Graph
- [Kepentingan](enrichment-microsoft-graph.md) disediakan oleh Microsoft Graph
- [Data syarikat](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Demografik](enrichment-experian.md) disediakan oleh Experian
- [Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies
- [Data tersuai](enrichment-SFTP-custom-import.md) melalui Protokol Pemindahan Fail Selamat (SFTP)

Pada tab **Pengayaan saya**, anda boleh melihat pengayaan yang telah anda konfigurasikan dan mengedit sifatnya.

## <a name="manage-existing-enrichments"></a>Mengurus pengayaan sedia ada

Pergi ke **Pengayaan saya** untuk melihat semua pengayaan dikonfigurasi. Setiap pengayaan diwakili sebagai baris yang termasuk maklumat tambahan tentang pengayaan.

Pilih pengayaan untuk melihat pilihan tersedia. Secara alternatif, anda boleh melihat elipsis (...) pada senarai item untuk melihat pilihan.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengurus pengayaan dalam senarai pengayaan":::

- **Lihat** butiran pengayaan dengan bilangan profil pelanggan yang dikayakan.
- **Edit** konfigurasi pengayaan.
- **Jalankan** pengayaan untuk mengemas kini profil pelanggan dengan data terkini.
- **Nyahaktifkan** pengayaan sedia ada untuk menghentikannya daripada penyegaran semula secara automatik dengan setiap segar semula dijadualkan. Data daripada segar semula terakhir yang berjaya akan terus tersedia. **Aktifkan** pengayaan yang tidak aktif untuk memulakan semula penyegaran semula secara automatik dengan setiap segar semula dijadualkan.
- **Padam** pengayaan.

Anda boleh menjalankan atau menyahaktifkan berbilang pengayaan sekaligus dengan memilihnya dalam senarai. Pilihan lihat dan edit tidak tersedia sebagai tindakan pukal dan hanya berfungsi untuk satu pengayaan dalam satu masa.


[!INCLUDE[footer-include](../includes/footer-banner.md)]