---
title: Memperkayakan profil pelanggan dengan alamat yang dipertingkatkan (mengandungi video)
description: Perkayakan dan normalkan maklumat alamat profil pelanggan dengan model Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 01f1c917c75e932cc69f4c7251e57524fc859dce
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082076"
---
# <a name="enrich-customer-profiles-with-enhanced-addresses"></a>Memperkayakan profil pelanggan dengan alamat yang dipertingkatkan

Alamat dalam data anda boleh tidak berstruktur, tidak lengkap atau tidak betul. Gunakan model Microsoft untuk menormalkan dan memperkayakan alamat anda ke dalam [Format Model Data Tersuai](/common-data-model/schema/core/applicationcommon/address) untuk ketepatan dan wawasan yang lebih baik.

Anda juga [boleh memperkayakan alamat pada sumber](data-sources-enrichment.md) data untuk meningkatkan ketepatan padanan dalam proses penyatuan data. 

## <a name="how-we-enhance-addresses"></a>Cara kami mempertingkatkan alamat

Model kami akan melalui proses dua langkah untuk meningkatkan alamat. Pertama, ia menghuraikan alamat untuk mengenal pasti komponennya dan menempatkannya ke dalam format berstruktur. Kemudian, kami menggunakan AI untuk membetulkan, melengkapkan dan menyeragamkan nilai dalam alamat.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Contoh

Maklumat alamat mungkin dalam format bukan standard dan mengandungi ralat ejaan. Model boleh membetulkan isu ini dan mencipta alamat yang konsisten dalam profil pelanggan disatukan.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Batasan

Alamat dipertingkatkan hanya berfungsi dengan nilai yang sudah wujud dalam data alamat anda yang ditelan. Model tidak:

1. Tentu sah jika alamat adalah alamat yang sah.
2. Sahkan Jika sebarang nilai seperti poskod atau nama jalan adalah sah.
3. Tukar nilai yang tidak dikenali.

Model menggunakan teknik berasaskan pembelajaran mesin untuk meningkatkan alamat. Seperti mana-mana model berasaskan pembelajaran mesin, ketepatan 100 peratus tidak dijamin.

## <a name="supported-countries-or-regions"></a>Negara atau rantau yang disokong

Kami kini menyokong memperkaya alamat dalam negara atau rantau ini:

- Australia
- Kanada
- Perancis
- Jerman
- Itali
- Jepun
- United Kingdom
- Amerika Syarikat

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Kayakan data saya** pada jubin **Alamat dipertingkatkan**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Tangkapan skrin jubin alamat yang Dipertingkatkan.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Pilih cara alamat diformatkan dalam set data anda. Pilih **Alamat atribut tunggal** jika alamat dalam data anda menggunakan medan tunggal. Pilih **Alamat berbilang atribut** jika alamat dalam data anda menggunakan lebih daripada satu medan data.

1. Pilih **Seterusnya** dan petakan medan alamat daripada entiti pelanggan bersatu anda.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Halaman pemetaan medan alamat yang dipertingkatkan.":::

   > [!NOTE]
   > Negara/Rantau adalah wajib dalam kedua-dua alamat satu atribut dan berbilang atribut. Alamat yang tidak mengandungi nilai yang sah atau nilai negara/rantau yang disokong tidak akan diperkaya.

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Berikan Nama** untuk pengayaan dan **entiti** Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Bilangan pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap medan yang diperkaya.

### <a name="overview-card"></a>Kad Gambaran Keseluruhan

Kad **gambaran keseluruhan** Pelanggan mengubah butiran tentang liputan pengayaan:

- **Alamat diproses dan diubah**: Bilangan profil pelanggan dengan alamat yang berjaya diperkaya.
- **Alamat diproses dan tidak diubah**: Bilangan profil pelanggan dengan alamat yang dikenali tetapi tidak diubah. Ia biasanya berlaku apabila data input sah dan tidak boleh diperbaiki oleh pengayaan.
- **Alamat tidak diproses dan tidak diubah**: Bilangan profil dengan alamat yang tidak dikenali. Biasanya untuk data input yang tidak sah atau tidak disokong oleh pengayaan.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
