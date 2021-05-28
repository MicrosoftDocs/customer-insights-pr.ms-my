---
title: Perkayakan profil pelanggan disatukan
description: Gunakan keupayaan untuk memperkayakan data pelanggan anda.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954498"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan":::

Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk bekerja dengan pilihan pengayaan.    
Anda perlu mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan. Untuk maklumat lanjut, lihat [Keizinan](permissions.md).

Pada tab **Temui**, anda akan menemui pengayaan yang berikut:

- [Jenama](enrichment-microsoft.md) disediakan oleh Microsoft
- [Minat](enrichment-microsoft.md) disediakan oleh Microsoft
- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft
- [Data syarikat](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Demografik](enrichment-experian.md) disediakan oleh Experian
- [Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies
- [Data tersuai](enrichment-SFTP-custom-import.md) melalui Protokol Pemindahan Fail Selamat (SFTP)

Pada tab **Pengayaan saya**, anda boleh melihat pengayaan yang telah anda konfigurasikan dan mengedit sifatnya.

## <a name="manage-existing-enrichments"></a>Mengurus pengayaan sedia ada

Pergi ke **Pengayaan saya** untuk melihat semua pengayaan dikonfigurasi. Setiap pengayaan diwakili sebagai baris yang termasuk maklumat tambahan tentang pengayaan.

Pilih pengayaan untuk melihat pilihan tersedia. Anda juga boleh memilih elipsis (...) pada item senarai untuk melihat pilihan.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengurus pengayaan dalam senarai pengayaan":::

- **Lihat** butiran pengayaan dengan bilangan profil pelanggan yang dikayakan.
- **Edit** konfigurasi pengayaan.
- **Jalankan** pengayaan untuk mengemas kini profil pelanggan dengan data terkini.
- **Nyahaktifkan** pengayaan sedia ada untuk menghentikannya daripada penyegaran semula secara automatik dengan setiap segar semula dijadualkan. Data daripada segar semula terakhir yang berjaya akan terus tersedia. **Aktifkan** pengayaan yang tidak aktif untuk memulakan semula penyegaran semula secara automatik dengan setiap segar semula dijadualkan.
- **Padam** pengayaan.

Anda boleh menjalankan atau menyahaktifkan berbilang pengayaan sekaligus dengan memilihnya dalam senarai. Pilihan lihat dan edit tidak tersedia sebagai tindakan pukal dan hanya berfungsi untuk satu pengayaan dalam satu masa.

## <a name="enrichments-and-connections"></a>Sambungan untuk pengayaan

Pengayaan pihak ketiga dikonfigurasikan menggunakan [sambungan](connections.md), yang mana pentadbir menyediakan kelayakan dan persetujuan untuk pindahan data. Sambungan boleh digunakan oleh pentadbir dan penyumbang untuk mengkonfigurasikan pengayaan.  

## <a name="multiple-enrichments-of-the-same-type"></a>Pelbagai pengayaan untuk jenis yang sama

Entiti yang akan diperkaya ditentukan semasa konfigurasi pengayaan, yang membolehkan anda memperkayakan hanya subset profil anda. Contohnya, memperkayakan data hanya untuk segmen tertentu. Anda boleh mengkonfigurasikan beberapa pengayaan jenis yang sama dan menggunakan semula sambungan yang sama. Sesetengah pengayaan mempunyai had bilangan pengayaan jenis yang sama yang boleh dicipta. Had dan penggunaan semasa boleh dilihat pada halaman **Pengayaan**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
