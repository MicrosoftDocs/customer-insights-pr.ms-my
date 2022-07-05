---
title: Gambaran keseluruhan pengayaan data (pratonton)
description: Gunakan keupayaan daripada Microsoft dan perkhidmatan pihak ketiga yang lain untuk memperkayakan data pelanggan anda.
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
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053891"
---
# <a name="data-enrichment-preview-overview"></a>Gambaran keseluruhan pengayaan data (pratonton)

Gunakan data daripada sumber seperti Microsoft dan rakan kongsi lain untuk mengayakan data pelanggan anda. Pengayaan pihak ketiga dikonfigurasikan menggunakan [sambungan](connections.md), yang mana pentadbir menyediakan kelayakan dan persetujuan untuk pindahan data. Sambungan ini boleh digunakan oleh pentadbir dan penyumbang untuk konfigurasikan pengayaan.  

## <a name="multiple-enrichments-of-the-same-type"></a>Pelbagai pengayaan untuk jenis yang sama

Entiti yang akan diperkaya ditentukan semasa konfigurasi pengayaan, yang membolehkan anda memperkayakan hanya subset profil anda. Contohnya, memperkaya data hanya untuk segmen tertentu. Anda boleh mengkonfigurasikan beberapa pengayaan jenis yang sama dan menggunakan semula sambungan yang sama. Sesetengah pengayaan mempunyai had bilangan pengayaan jenis yang sama yang boleh dicipta. Had dan penggunaan semasa boleh dilihat pada setiap jubin pada **tab** Discover **halaman Pengayaan**.

## <a name="enrich-data-sources-before-unification"></a>Memperkayakan sumber data sebelum penyatuan

Anda boleh memperkayakan data pelanggan anda sebelum penyatuan data untuk membantu meningkatkan kualiti padanan data. Untuk maklumat lanjut, lihat [pengayaan sumber data](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Cipta pengayaan

Anda perlu mempunyai keizinan [Penyumbang atau Pentadbir](permissions.md) untuk mencipta atau mengedit pengayaan.

Pergi ke **Data** > **Pengayaan**. Tab **Discover** menunjukkan semua opsyen pengayaan yang disokong.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Halaman hab pengayaan.":::

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

## <a name="manage-existing-enrichments"></a>Mengurus pengayaan sedia ada

Pergi ke **Data** > **Pengayaan**. **Pada tab Pengayaan saya**, lihat pengayaan yang dikonfigurasi, status mereka, bilangan pelanggan yang diperkaya dan kali terakhir data disegarkan semula. Anda boleh mengisih senarai pengayaan mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari pengayaan yang anda ingin uruskan.

Pilih pengayaan untuk melihat tindakan yang tersedia.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Pilihan untuk mengurus pengayaan dalam senarai pengayaan.":::

- **Lihat** butiran pengayaan dengan bilangan profil pelanggan yang dikayakan.
- **Edit** konfigurasi pengayaan.
- [**Jalankan**](#run-or-refresh-enrichments) pengayaan untuk mengemas kini profil pelanggan dengan data terkini. Jalankan pelbagai pengayaan sekaligus dengan memilihnya dalam senarai.
- **Mengaktifkan** atau **Menyahaktifkan** pengayaan. Pengayaan tidak aktif tidak akan disegarkan semula semasa segar semula [yang](system.md#schedule-tab) dijadualkan.
- **Padamkan** pengayaan.

Anda juga boleh membuat [segmen](segments.md) atau [langkah](measures.md) daripada pengayaan.

## <a name="run-or-refresh-enrichments"></a>Jalankan atau segar semula pengayaan

Setelah dijalankan, pengayaan boleh disegarkan semula pada jadual automatik atau disegarkan secara manual atas permintaan.

1. Untuk menyegar semula satu atau lebih pengayaan secara manual, pilihnya dan pilih **Jalankan**. Untuk [menjadualkan segar semula](system.md#schedule-tab) automatik, pergi ke **Jadual** > **Sistem** > **Pentadbir**. Masa pemprosesan bergantung pada saiz data pelanggan anda.

1. Secara pilihan, [lihat kemajuan proses](#see-the-progress-of-the-enrichment-process) pengayaan.

1. Selepas proses pengayaan selesai, pergi ke **Pengayaan saya** untuk menyemak data profil pelanggan yang baru diperkaya, masa kemas kini terakhir, dan bilangan profil yang diperkaya.

1. Pilih pengayaan untuk melihat [hasil](#view-enrichment-results) pengayaan.

### <a name="see-the-progress-of-the-enrichment-process"></a>Lihat kemajuan proses pengayaan

Anda boleh menemukan butiran tentang pemprosesan pengayaan, termasuk status dan isu yang berpotensi semasa penyegaran semula atau selepas segar semula selesai. Fahami proses yang terlibat untuk menyegarkan semula pengayaan dan tempoh masa yang diambil untuk menjalankan proses tersebut. Status pengayaan disokong untuk Experian, Leadspace, di sini teknologi, Import SFTP, dan Azure Maps.

1. Pergi ke **Data** > **Pengayaan**.
1. **Dalam tab Pengayaan saya**, pilih status pengayaan untuk membuka anak tetingkap sisi.
1. Dalam anak tetingkap **Butiran kemajuan**, kembangkan bahagian **Pengayaan**.
1. Di bawah pengayaan yang mahu anda lihat kemajuan, pilih **Lihat butiran**.
1. Dalam anak tetingkap **Butiran tugas**, pilih **Tunjukkan butiran** untuk melihat proses yang terlibat dalam pengemaskinian pengayaan dan status proses tersebut.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

Selepas pengayaan selesai, semak semula keputusan pengayaan.

1. Pergi ke **Data** > **Pengayaan**.
1. **Dalam tab Pengayaan saya**, pilih pengayaan yang anda ingin lihat.

Semua pengayaan menunjukkan maklumat asas seperti bilangan profil yang diperkaya dan bilangan profil yang diperkaya dari masa ke masa. Jubin **pratonton** pelanggan Enriched menunjukkan sampel entiti pengayaan yang dijana. Untuk melihat pandangan terperinci, pilih **Lihat lebih lanjut** dan pilih **tab Data**.

:::image type="content" source="media/enrichments-results.png" alt-text="Halaman hasil pengayaan.":::

Sekiranya ada, **Bilangan pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap medan yang diperkaya.

Sesetengah pengayaan juga menunjukkan maklumat khusus untuk jenis pengayaan. Untuk maklumat lanjut, lihat dokumentasi yang berkaitan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
