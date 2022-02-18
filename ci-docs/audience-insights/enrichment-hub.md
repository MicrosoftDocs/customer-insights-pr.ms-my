---
title: Perkayakan profil pelanggan disatukan
description: Gunakan keupayaan untuk memperkayakan data pelanggan anda.
ms.date: 02/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5c3dda3b9bae828857258025ff79958ee22bdb6f
ms.sourcegitcommit: a399bd17523c8d06afd7d78af4fc711f93c0e8be
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/07/2022
ms.locfileid: "8098800"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan.":::

Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan** untuk bekerja dengan pilihan pengayaan.  

Anda perlu mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan. Untuk maklumat lanjut, lihat [Keizinan](permissions.md).

Pada tab **Terokai**, anda akan mencari semua pilihan pengayaan yang disokong.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- [Jenama](enrichment-microsoft.md) disediakan oleh Microsoft
- [Minat](enrichment-microsoft.md) disediakan oleh Microsoft
- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft 
- [Demografi](enrichment-experian.md) disediakan oleh Experian
- [Data tersuai](enrichment-SFTP-custom-import.md) melalui Protokol Pemindahan Fail Selamat (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) disediakan oleh Microsoft
- [Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies 

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- [Data syarikat](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft 
- [Data](enrichment-enhanced-company-data.md) syarikat yang dipertingkatkan yang disediakan oleh Microsoft
- [Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies 
- [Data tersuai](enrichment-SFTP-custom-import.md) melalui Protokol Pemindahan Fail Selamat (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) disediakan oleh Microsoft
- [Data penglibatan akaun](enrichment-office.md) yang disediakan oleh Microsoft

---

Pada tab **Pengayaan saya**, anda boleh melihat pengayaan yang telah anda konfigurasikan dan mengedit sifatnya.

## <a name="manage-existing-enrichments"></a>Mengurus pengayaan sedia ada

Pergi ke tab **Pengayaan Saya** untuk melihat semua pengayaan yang dikonfigurasikan. Setiap pengayaan diwakili sebagai baris yang termasuk maklumat tambahan tentang pengayaan.

Pilih pengayaan untuk melihat pilihan yang tersedia. Anda juga boleh memilih elipsis (...) pada item senarai untuk melihat pilihan. Jika anda mengkonfigurasi beberapa pengayaan, anda boleh menggunakan kotak carian untuk mencarinya dengan cepat.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengurus pengayaan dalam senarai pengayaan.":::

- **Lihat** butiran pengayaan dengan bilangan profil pelanggan yang dikayakan.
- **Edit** konfigurasi pengayaan.
- **Jalankan** pengayaan untuk mengemas kini profil pelanggan dengan data terkini.
- **Nyahaktifkan** pengayaan sedia ada untuk menghentikannya daripada penyegaran semula secara automatik dengan setiap segar semula dijadualkan. Data daripada segar semula terakhir yang berjaya akan terus tersedia. **Aktifkan** pengayaan yang tidak aktif untuk memulakan semula penyegaran semula secara automatik dengan setiap segar semula dijadualkan.
- **Padamkan** pengayaan.

Jalankan atau nyahaktifkan berbilang pengayaan secara serentak dengan memilihnya dalam senarai. Pilihan pandangan dan edit tidak tersedia sebagai tindakan pukal. Ia hanya berfungsi untuk satu pengayaan pada satu masa.

## <a name="enrichments-and-connections"></a>Sambungan untuk pengayaan

Pengayaan pihak ketiga dikonfigurasikan menggunakan [sambungan](connections.md), yang mana pentadbir menyediakan kelayakan dan persetujuan untuk pindahan data. Sambungan ini boleh digunakan oleh pentadbir dan penyumbang untuk konfigurasikan pengayaan.  

## <a name="multiple-enrichments-of-the-same-type"></a>Pelbagai pengayaan untuk jenis yang sama

Entiti yang akan diperkaya ditentukan semasa konfigurasi pengayaan, yang membolehkan anda memperkayakan hanya subset profil anda. Contohnya, memperkaya data hanya untuk segmen tertentu. Anda boleh mengkonfigurasikan beberapa pengayaan jenis yang sama dan menggunakan semula sambungan yang sama. Sesetengah pengayaan mempunyai had bilangan pengayaan jenis yang sama yang boleh dicipta. Had dan penggunaan semasa boleh dilihat pada halaman **Pengayaan**.

## <a name="see-the-progress-of-the-enrichment-process"></a>Lihat kemajuan proses pengayaan

Anda boleh menemukan butiran tentang pemprosesan pengayaan, termasuk status dan isu yang berpotensi semasa penyegaran semula atau selepas segar semula selesai. Fahami proses yang terlibat untuk menyegarkan semula pengayaan dan tempoh masa yang diambil untuk menjalankan proses tersebut. Status pengayaan disokong untuk Experian, Leadspace, di sini teknologi, Import SFTP, dan Azure Maps.

Untuk melihat status pengayaan

1. Pergi ke **Data** > **Pengayaan**. 
1. Dalam tab **Penggayaan saya**, pilih status pengayaan untuk membuka anak tetingkap sisi. 
1. Dalam anak tetingkap **Butiran kemajuan**, kembangkan bahagian **Pengayaan**. 
1. Di bawah pengayaan yang mahu anda lihat kemajuan, pilih **Lihat butiran**. 
1. Dalam anak tetingkap **Butiran tugas**, pilih **Tunjukkan butiran** untuk melihat proses yang terlibat dalam pengemaskinian pengayaan dan status proses tersebut. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
