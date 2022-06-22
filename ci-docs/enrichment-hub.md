---
title: Perkayakan profil pelanggan disatukan
description: Gunakan keupayaan untuk memperkayakan data pelanggan anda.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954052"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Pengayaan untuk profil pelanggan (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan.":::

Pergi ke **Pengayaan** > **Data** untuk bekerja dengan opsyen pengayaan.  

Anda perlu mempunyai keizinan Penyumbang atau Pentadbir untuk mencipta atau mengedit pengayaan. Untuk maklumat lanjut, lihat [Keizinan](permissions.md).

Pada tab **Terokai**, anda akan mencari semua pilihan pengayaan yang disokong.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- [Identiti](enrichment-liveramp.md) AbiliTec yang disediakan oleh LiveRamp AbiliTec
- [Jenama](enrichment-microsoft.md) disediakan oleh Microsoft
- [Demografi](enrichment-experian.md) disediakan oleh Experian
- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft
- [Minat](enrichment-microsoft.md) disediakan oleh Microsoft
- [Data lokasi yang](enrichment-azure-maps.md) disediakan oleh Microsoft Azure Peta
- [Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies
- [Data](enrichment-SFTP-custom-import.md) tersuai SFTP melalui Protokol Pemindahan Fail Selamat (SFTP)

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- [Data penglibatan akaun yang](enrichment-office.md) disediakan oleh Microsoft
- [Data syarikat yang](enrichment-dnb.md) disediakan oleh Dun & Bradstreet
- [Data syarikat](enrichment-leadspace.md) yang disediakan oleh Leadspace
- [Alamat dipertingkatkan](enrichment-enhanced-addresses.md) yang disediakan oleh Microsoft
- [Data syarikat dipertingkatkan yang](enrichment-enhanced-company-data.md) disediakan oleh Microsoft
- [Data lokasi yang](enrichment-azure-maps.md) disediakan oleh Microsoft Azure Peta
- [Data lokasi](enrichment-here.md) yang disediakan oleh HERE Technologies
- [Data](enrichment-SFTP-custom-import.md) tersuai SFTP melalui Protokol Pemindahan Fail Selamat (SFTP)

---

Pada tab **Pengayaan saya**, anda boleh melihat pengayaan yang telah anda konfigurasikan dan mengedit sifatnya. Anda juga boleh membuat [segmen](segments.md) atau [langkah](measures.md) daripada pengayaan.

## <a name="manage-existing-enrichments"></a>Mengurus pengayaan sedia ada

Pergi ke tab **Pengayaan Saya** untuk melihat semua pengayaan yang dikonfigurasikan. Setiap pengayaan diwakili sebagai baris yang termasuk maklumat tambahan tentang pengayaan.

Pilih pengayaan untuk melihat pilihan yang tersedia. Anda juga boleh memilih elipsis menegak (&vellip;) pada item senarai untuk melihat pilihan. Jika anda mengkonfigurasi beberapa pengayaan, anda boleh menggunakan kotak carian untuk mencarinya dengan cepat.

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

Entiti yang akan diperkaya ditentukan semasa konfigurasi pengayaan, yang membolehkan anda memperkayakan hanya subset profil anda. Contohnya, memperkaya data hanya untuk segmen tertentu. Anda boleh mengkonfigurasikan beberapa pengayaan jenis yang sama dan menggunakan semula sambungan yang sama. Sesetengah pengayaan mempunyai had bilangan pengayaan jenis yang sama yang boleh dicipta. Had dan penggunaan semasa boleh dilihat pada setiap jubin pada **tab** Discover **halaman Pengayaan**.

## <a name="enrich-data-sources-before-unification"></a>Memperkayakan sumber data sebelum penyatuan

Anda boleh memperkayakan data pelanggan anda sebelum penyatuan data untuk membantu meningkatkan kualiti padanan data. Untuk maklumat lanjut, lihat [pengayaan](data-sources-enrichment.md) sumber data.

## <a name="run-or-refresh-enrichments"></a>Jalankan atau segar semula pengayaan

1. Untuk memulakan proses pengayaan, pilih **Jalankan**. Atau, biarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada segar semula [yang](system.md#schedule-tab) dijadualkan. Masa pemprosesan bergantung pada saiz data pelanggan anda.

1. Secara pilihan, [lihat kemajuan proses](#see-the-progress-of-the-enrichment-process) pengayaan.

1. Selepas proses pengayaan selesai, pergi ke **Pengayaan saya** untuk menyemak data profil pelanggan yang baru diperkaya, masa kemas kini terakhir, dan bilangan profil yang diperkaya.

1. Pilih pengayaan untuk melihat [hasil](#enrichment-results) pengayaan.

### <a name="see-the-progress-of-the-enrichment-process"></a>Lihat kemajuan proses pengayaan

Anda boleh menemukan butiran tentang pemprosesan pengayaan, termasuk status dan isu yang berpotensi semasa penyegaran semula atau selepas segar semula selesai. Fahami proses yang terlibat untuk menyegarkan semula pengayaan dan tempoh masa yang diambil untuk menjalankan proses tersebut. Status pengayaan disokong untuk Experian, Leadspace, di sini teknologi, Import SFTP, dan Azure Maps.

1. Pergi ke **Data** > **Pengayaan**.
1. **Dalam tab Pengayaan saya**, pilih status pengayaan untuk membuka anak tetingkap sisi.
1. Dalam anak tetingkap **Butiran kemajuan**, kembangkan bahagian **Pengayaan**.
1. Di bawah pengayaan yang mahu anda lihat kemajuan, pilih **Lihat butiran**.
1. Dalam anak tetingkap **Butiran tugas**, pilih **Tunjukkan butiran** untuk melihat proses yang terlibat dalam pengemaskinian pengayaan dan status proses tersebut.

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas pengayaan selesai, semak semula keputusan pengayaan.

1. Pergi ke **Data** > **Pengayaan**.
1. **Dalam tab Pengayaan saya**, pilih pengayaan yang anda inginkan maklumat.

Semua pengayaan menunjukkan maklumat asas seperti bilangan profil yang diperkaya dan bilangan profil yang diperkaya dari masa ke masa. Jubin **pratonton** pelanggan Enriched menunjukkan sampel entiti pengayaan yang dijana. Untuk melihat pandangan terperinci, pilih **Lihat lebih lanjut** dan pilih **tab Data**.

:::image type="content" source="media/enrichments-results.png" alt-text="Halaman hasil pengayaan.":::

Sekiranya ada, **Bilangan pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap medan yang diperkaya.

Sesetengah pengayaan juga menunjukkan maklumat khusus untuk jenis pengayaan. Untuk maklumat lanjut, lihat dokumentasi yang berkaitan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
