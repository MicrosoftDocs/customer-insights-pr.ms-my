---
title: Pengayaan peningkatan alamat (mengandungi video)
description: Perkayakan dan normalkan maklumat alamat profil pelanggan dengan model Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
---

# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Pengayaan profil pelanggan dengan alamat yang dipertingkatkan

Alamat dalam data anda boleh tidak berstruktur, tidak lengkap atau tidak betul. Gunakan model Microsoft untuk menormalkan dan memperkayakan alamat anda ke dalam [Format Model Data Tersuai](/common-data-model/schema/core/applicationcommon/address) untuk ketepatan dan wawasan yang lebih baik.

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

### <a name="limitations"></a>Had

Alamat yang dipertingkatkan hanya berfungsi dengan nilai yang sudah wujud dalam data alamat diinges anda. Model tidak: 

1. Tentu sah jika alamat adalah alamat yang sah.
2. Sahkan Jika sebarang nilai seperti poskod atau nama jalan adalah sah.
3. Tukar nilai yang tidak dikenali.

Model menggunakan teknik berasaskan pembelajaran mesin untuk meningkatkan alamat. Walaupun kami menggunakan ambang keyakinan yang tinggi apabila model mengubah nilai input, seperti mana-mana model berasaskan pembelajaran mesin, ketepatan 100 peratus tidak dijamin.

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

Alamat mesti mengandungi nilai negara/rantau. Kami tidak memproses alamat untuk negara atau rantau yang tidak disokong dan alamat yang tidak mempunyai negara atau rantau yang disediakan.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan**.

1. Pilih **Kayakan data saya** pada jubin **Alamat dipertingkatkan**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Tangkapan skrin jubin alamat yang Dipertingkatkan.":::

1. Pilih **Set data pelanggan** dan pilih entiti yang mengandungi alamat yang anda mahu perkayakan. Anda boleh memilih entiti *Pelanggan* untuk memperkayakan alamat dalam semua profil pelanggan anda atau memilih entiti segmen untuk memperkayakan alamat hanya dalam profil pelanggan yang terkandung dalam segmen itu.

1. Pilih cara alamat diformatkan dalam set data anda. Pilih **Alamat atribut tunggal** jika alamat dalam data anda menggunakan medan tunggal. Pilih **Alamat berbilang atribut** jika alamat dalam data anda menggunakan lebih daripada satu medan data.

   > [!NOTE]
   > Negara/Rantau adalah wajib dalam kedua-dua alamat satu atribut dan berbilang atribut. Alamat yang tidak mengandungi nilai yang sah atau nilai negara/rantau yang disokong tidak akan diperkaya.

1.  Petakan medan alamat daripada entiti pelanggan disatukan anda.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Halaman pemetaan medan alamat yang dipertingkatkan.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. Berikan nama untuk pengayaan dan entiti output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

## <a name="enrichment-results"></a>Keputusan pengayaan

Untuk memulakan proses pengayaan, pilih **Jalankan** daripada bar perintah. Anda juga boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula dijadualkan](system.md#schedule-tab). Masa pemprosesan bergantung pada saiz data pelanggan anda.

Selepas proses pengayaan selesai, anda boleh menyemak data profil pelanggan yang baru diperkaya di bawah **Pengayaan saya**. Di samping itu, anda akan menemui masa kemas kini yang terakhir dan bilangan profil yang diperkaya.

Anda boleh melihat sampel data yang diperkaya dalam **jubin pratonton** pelanggan diperkaya. Pilih **Lihat lebih lanjut** dan pilih **tab Data** untuk mengakses pandangan terperinci setiap profil yang diperkaya.

### <a name="overview-card"></a>Kad gambaran keseluruhan

Kad gambaran keseluruhan menunjukkan butiran mengenai liputan pengayaan. 

* **Alamat diproses dan diubah**: Bilangan profil pelanggan dengan alamat yang berjaya diperkaya.

* **Alamat diproses dan tidak berubah**: Bilangan profil pelanggan dengan alamat yang diiktiraf tetapi tidak diubah. Ia biasanya berlaku apabila data input sah dan tidak boleh diperbaiki oleh pengayaan.

* **Alamat tidak diproses dan tidak diubah**: Bilangan profil dengan alamat yang tidak dikenali. Biasanya untuk data input yang tidak sah atau tidak disokong oleh pengayaan.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
