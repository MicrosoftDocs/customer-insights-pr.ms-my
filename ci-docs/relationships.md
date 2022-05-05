---
title: Hubungan antara entiti dan laluan entiti
description: Cipta dan urus hubungan antara entiti daripada berbilang sumber data.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: a7b10d985d5cba64b25595a3d7c101d6cb5c62a5
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 04/27/2022
ms.locfileid: "8643807"
---
# <a name="relationships-between-entities"></a>Perhubungan antara entiti

Perhubungan menghubungkan entiti dan mentakrifkan graf data anda apabila entiti berkongsi pengecam biasa, iaitu kunci asing. Kunci asing ini boleh dirujuk daripada satu entiti ke entiti lain. Entiti yang berhubung membolehkan definisi segmen dan ukuran berdasarkan berbilang sumber data.

Terdapat tiga jenis perhubungan: 
- Perhubungan sistem tidak boleh diedit, yang dicipta oleh sistem sebagai sebahagian daripada proses penyatuan data
- Perhubungan yang diwarisi dan tidak boleh diedit, yang dicipta secara automatik daripada pengingesan sumber data 
- Perhubungan tersuai boleh diedit, yang dicipta dan dikonfigurasikan oleh pengguna

## <a name="non-editable-system-relationships"></a>Perhubungan sistem tidak boleh diedit

Semasa penyatuan data, perhubungan sistem dicipta secara automatik berdasarkan padanan pintar. Perhubungan ini membantu untuk mengaitkan rekod profil pelanggan dengan rekod yang sepadan. Gambar rajah berikut menggambarkan penciptaan tiga perhubungan berdasarkan sistem. Entiti pelanggan dipadankan dengan entiti lain untuk menghasilkan entiti *Pelanggan* disatukan.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Gambar rajah dengan laluan hubungan untuk entiti pelanggan dengan tiga hubungan 1-n.":::

- **Perhubungan *CustomerToContact*** dicipta antara entiti *Pelanggan* dengan entiti *Kenalan*. Entiti *Pelanggan* memperoleh medan kunci **Contact_contactID** untuk mengaitkan dengan entiti *Kenalan* medan kunci **contactID**.
- **Perhubungan *CustomerToAccount*** dicipta antara entiti *Pelanggan* dengan entiti *Akaun*. Entiti *Pelanggan* memperoleh medan kunci **Account_accountID** untuk mengaitkan dengan entiti *Akaun* medan kunci **accountID**.
- **Perhubungan *CustomerToWebAccount*** dicipta antara entiti *Pelanggan* dengan entiti *WebAccount*. Entiti *Pelanggan* memperoleh medan kekunci **WebAccount_webaccountID** untuk mengaitkan dengan entiti *WebAccount* medan kekunci **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Perhubungan yang diwarisi dan tidak boleh diedit

Semasa proses pengingesan data, sistem menyemak sumber data untuk perhubungan sedia ada. Jika tiada perhubungan wujud, sistem mencipta perhubungan secara automatik. Perhubungan ini juga digunakan dalam proses hiliran.

## <a name="create-a-custom-relationship"></a>Cipta perhubungan tersuai

Perhubungan terdiri daripada *entiti sumber* yang mengandungi kunci asing dan *entiti sasaran* yang dihalakan ke kunci asing entiti sumber. 

1. Pergi ke **Data** > **Perhubungan**.

2. Pilih **Perhubungan baharu**.

3. Dalam anak tetingkap **Perhubungan baharu**, berikan maklumat berikut:

   :::image type="content" source="media/relationship-add.png" alt-text="Anak tetingkap sisi perhubungan baharu dengan medan input kosong.":::

   - **Nama perhubungan**: Nama yang mencerminkan tujuan perhubungan. Contoh: CustomerToSupportCase.
   - **Description**: Description bagi perhubungan.
   - **Entiti sumber**: Entiti yang digunakan sebagai sumber dalam perhubungan. Contoh: SupportCase.
   - **Entiti sasaran**: Entiti yang digunakan sebagai sasaran dalam perhubungan. Contoh: Pelanggan.
   - **Kekardinalan sumber**: Tentukan kekardinalan entiti sumber. Kekardinalan menerangkan bilangan elemen yang mungkin dalam satu set. Ia sentiasa berkaitan dengan kekardinalan sasaran. Anda boleh memilih antara **Satu** dengan **Banyak**. Hanya perhubungan banyak-ke-satu dan satu-ke-satu disokong.  
     - Banyak kepada satu: Berbilang rekod sumber boleh berkaitan dengan satu rekod sasaran. Contoh: Berbilang kes sokongan daripada pelanggan tunggal.
     - Satu kepada satu: Rekod sumber tunggal berkaitan dengan satu rekod sasaran. Contoh: Satu ID kesetiaan untuk pelanggan tunggal.

     > [!NOTE]
     > Perhubungan banyak kepada banyak boleh dicipta menggunakan dua perhubungan banyak kepada satu dan entiti pemautan, yang menghubungkan entiti sumber dan entiti sasaran.

   - **Kekardinalan sasaran**: Pilih kekardinalan rekod entiti sasaran. 
   - **Medan kunci sumber**: Medan kunci asing dalam entiti sumber. Contoh: SupportCase boleh menggunakan CaseID sebagai medan kunci asing.
   - **Medan kunci sasaran**: Medan kunci entiti sasaran. Contoh Pelanggan boleh menggunakan medan kunci **CustomerID**.

4. Pilih **Simpan** untuk mencipta perhubungan tersuai.

## <a name="set-up-account-hierarchies"></a>Sediakan hierarki akaun

Persekitaran yang dikonfigurasikan untuk menggunakan akaun perniagaan sebagai khalayak sasaran utama boleh mengkonfigurasi hierarki akaun untuk akaun perniagaan yang berkaitan. Contohnya, syarikat yang mempunyai unit perniagaan yang berasingan. 

Organisasi mencipta hierarki akaun untuk menguruskan akaun yang lebih baik dan perhubungan mereka antara satu sama lain. Wawasan Pelanggan menyokong hierarki akaun ibu bapa-anak yang sudah wujud dalam data pelanggan yang ditelan. Sebagai contoh, akaun daripada Dynamics 365 Sales. Hierarki ini boleh dikonfigurasikan pada **halaman Perhubungan**.

1. Pergi ke **Data** > **Perhubungan**.
1. Pilih tab **Hierarki akaun** tab.
1. Pilih **Hierarki akaun baharu**. 
1. Dalam anak tetingkap **Hierarki akaun**, memberikan nama untuk hierarki. Sistem mencipta nama untuk entiti output. Anda boleh mengubah nama entiti nama output.
1. Pilih entiti yang mengandungi hierarki akaun anda. Ia biasanya dalam entiti yang sama yang mengandungi akaun.
1. Pilih **ID Akaun** dan **ID Induk Akaun** daripada entiti yang dipilih 
1. Pilih **Simpan** untuk menggunakan tetapan dan memuktamadkan hierarki akaun.

## <a name="view-relationships"></a>Lihat perhubungan

Halaman Perhubungan menyenaraikan semua perhubungan yang telah dicipta. Setiap baris mewakili perhubungan, yang juga termasuk butiran tentang entiti sumber, entiti sasaran dan kekardinalan. 

:::image type="content" source="media/relationships-list.png" alt-text="Senarai perhubungan dan pilihan dalam bar tindakan halaman Perhubungan.":::

Halaman ini menawarkan satu set pilihan untuk perhubungan sedia ada dan baharu: 
- **Perhubungan Baharu**: [Cipta perhubungan tersuai](#create-a-custom-relationship).
- **Penampak**: [Terokai penampak perhubungan](#explore-the-relationship-visualizer) untuk melihat gambar rajah rangkaian perhubungan yang sedia ada dan kekardinalan.
- **Tapis mengikut**: Pilih jenis perhubungan untuk ditunjukkan dalam senarai.
- **Cari perhubungan**: Gunakan carian berdasarkan teks pada sifat perhubungan.

### <a name="explore-the-relationship-visualizer"></a>Terokai penampak perhubungan

Penampak perhubungan menunjukkan gambar rajah rangkaian perhubungan yang sedia ada antara entiti yang berhubung dengan kekardinalan. Ia juga menggambarkan laluan perhubungan.

Untuk menyesuaikan pandangan, anda boleh mengubah kedudukan kotak dengan menyeret kotak pada kanvas.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Syot layar gambar rajah rangkaian penampak perhubungan dengan sambungan antara entiti yang berkaitan.":::

Pilihan yang tersedia: 
- **Eksport sebagai imej**: Simpan pandangan semasa sebagai fail imej.
- **Tukar kepada tataletak mendatar/menegak**: Tukar penjajaran entiti dan perhubungan.
- **Edit**: Kemas kini sifat perhubungan tersuai dalam anak tetingkap edit dan simpan perubahan.

## <a name="relationship-paths"></a>Laluan perhubungan

Laluan perhubungan menerangkan entiti yang disambungkan dengan perhubungan antara entiti sumber dan entiti sasaran. Ia digunakan apabila mencipta segmen atau ukuran yang termasuk entiti lain daripada entiti profil disatukan dan terdapat beberapa pilihan untuk mencapai entiti profil disatukan. 

Laluan perhubungan memberitahu sistem yang mana perhubungan untuk mengakses entiti profil bersepadu. Laluan perhubungan yang berbeza boleh menghasilkan keputusan yang berbeza.

Contohnya, entiti *eCommerce_eCommercePurchases* mempunyai perhubungan berikut kepada entiti *Pelanggan* profil disatukan:

- eCommerce_eCommercePurchases > Pelanggan
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Pelanggan
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Pelanggan 

Laluan perhubungan menentukan entiti yang anda boleh gunakan apabila mencipta peraturan untuk ukuran atau segmen. Memilih pilihan dengan laluan perhubungan terpanjang mungkin menghasilkan kurang hasil kerana rekod yang sepadan perlu menjadi sebahagian daripada semua entiti. Dalam contoh ini, pelanggan perlu membeli barang melalui e-dagang(eCommerce_eCommercePurchases), pada tempat jualan (POS_posPurchases) dan mengambil bahagian dalam program kesetiaan kami (loyaltyScheme_loyCustomers). Apabila memilih pilihan pertama, anda mungkin akan mendapat lebih banyak keputusan kerana pelanggan perlu wujud dalam satu entiti tambahan.

### <a name="direct-relationship"></a>Perhubungan langsung

Perhubungan dikelaskan sebagai **perhubungan langsung** apabila entiti sumber berkaitan dengan entiti sasaran dengan hanya satu perhubungan.

Sebagai contoh, jika entiti aktiviti yang dipanggil *eCommerce_eCommercePurchases* menyambung kepada entiti sasaran *eCommerce_eCommerceContacts* hanya melalui entiti *ContactId* merupakan perhubungan langsung.

:::image type="content" source="media/direct_Relationship.png" alt-text="Entiti sumber menyambung secara langsung kepada entiti sasaran.":::

#### <a name="multi-path-relationship"></a>Perhubungan berbilang laluan

**Perhubungan berbilang laluan** adalah jenis perhubungan langsung khas yang menyambungkan entiti sumber kepada lebih daripada satu entiti sasaran.

Sebagai contoh, jika entiti aktiviti yang dipanggil *eCommerce_eCommercePurchases* berkaitan dengan dua entiti, kedua-duanya *eCommerce_eCommerceContacts* dan *loyaltyScheme_loyCustomers* adalah perhubungan berbilang laluan.

:::image type="content" source="media/multi-path_relationship.png" alt-text="Entiti sumber menyambung secara langsung kepada lebih daripada satu entiti sasaran melalui perhubungan berbilang hop.":::

### <a name="indirect-relationship"></a>Perhubungan tidak langsung

Perhubungan dikelaskan sebagai **perhubungan tidak langsung** apabila entiti sumber berkaitan dengan satu atau lebih entiti tambahan sebelum mengaitkan dengan entiti sasaran.

#### <a name="multi-hop-relationship"></a>Perhubungan berbilang hop

*Perhubungan berbilang hop* adalah *perhubungan tidak langsung* yang membolehkan anda menyambungkan entiti sumber kepada entiti sasaran melalui satu atau lebih entiti perantara lain.

Sebagai contoh, jika entiti aktiviti yang dipanggil *eCommerce_eCommercePurchasesWest* menyambung ke entiti pertengahan yang dipanggil *eCommerce_eCommercePurchasesEast* dan kemudian menyambung ke entiti sasaran yang dipanggil *eCommerce_eCommerceContacts* adalah perhubungan berbilang hop.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="Entiti sumber menyambung secara terus kepada entiti sasaran dengan entiti pertengahan.":::

### <a name="multi-hop-multi-path-relationship"></a>Perhubungan berbilang hop, berbilang laluan

Perhubungan berbilang hop dan berbilang laluan boleh digunakan bersama-sama untuk mencipta **perhubungan berbilang hop, berbilang laluan**. Jenis khas ini menggabungkan fungsi perhubungan **berbilang hop** dan **berbilang laluan**. Ini membolehkan anda menyambung kepada lebih daripada satu entiti sasaran semasa menggunakan entiti pertengahan.

Sebagai contoh, jika entiti aktiviti dipanggil *eCommerce_eCommercePurchasesWest* menyambung ke entiti pertengahan dipanggil *eCommerce_eCommercePurchasesEast* dan kemudian menyambung ke dua entiti sasaran, kedua-duanya *eCommerce_eCommerceContacts* dan *loyaltyScheme_loyCustomers*, adalah perhubungan berbilang hop, berbilang laluan.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="Entiti sumber menyambung secara terus kepada satu entiti sasaran dan menyambung ke entiti sasaran lain melalui entiti pertengahan.":::

## <a name="manage-existing-relationships"></a>Urus perhubungan yang sedia ada 

Pada halaman Perhubungan, setiap perhubungan diwakili oleh baris. 

Pilih perhubungan dan pilih salah satu daripada pilihan berikut: 
 
- **Edit**: Kemas kini sifat perhubungan tersuai dalam anak tetingkap edit dan simpan perubahan.
- **Padam**: Padam perhubungan tersuai.
- **Lihat**: Lihat perhubungan yang dicipta sistem dan diwarisi. 

## <a name="next-step"></a>Langkah seterusnya

Sistem dan perhubungan tersuai digunakan untuk [mencipta segmen](segments.md) dan [ukuran](measures.md) berdasarkan sumber data berganda yang tidak lagi siloed.

[!INCLUDE [footer-include](includes/footer-banner.md)]
