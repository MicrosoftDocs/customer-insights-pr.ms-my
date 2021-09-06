---
title: Hubungan antara entiti dan laluan entiti
description: Cipta dan urus hubungan antara entiti daripada berbilang sumber data.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 1853fcd8db2918a0b4a19fa0934e2f0ddbcf6d093c85fdf2068a13f954035dec
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035242"
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

1. Dalam wawasan khalayak, pergi ke **Data** > **Hubungan**.

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

### <a name="relationship-path"></a>Laluan perhubungan

Laluan perhubungan menerangkan entiti yang disambungkan dengan perhubungan antara entiti sumber dan entiti sasaran. Ia digunakan apabila mencipta segmen atau ukuran yang termasuk entiti lain daripada entiti profil disatukan dan terdapat beberapa pilihan untuk mencapai entiti profil disatukan.

Laluan perhubungan ini memberitahu sistem yang perhubungan untuk mengakses entiti profil disatukan. Laluan perhubungan yang berbeza boleh menghasilkan keputusan yang berbeza.

Contohnya, entiti *eCommerce_eCommercePurchases* mempunyai perhubungan berikut kepada entiti *Pelanggan* profil disatukan:

- eCommerce_eCommercePurchases > Pelanggan
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Pelanggan
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Pelanggan 

Laluan perhubungan menentukan entiti yang boleh anda gunakan apabila mencipta peraturan untuk ukuran atau segmen. Memilih pilihan dengan laluan perhubungan terpanjang mungkin menghasilkan kurang hasil kerana rekod yang sepadan perlu menjadi sebahagian daripada semua entiti. Dalam contoh ini, pelanggan perlu membeli barang melalui e-dagang(eCommerce_eCommercePurchases), pada tempat jualan (POS_posPurchases) dan mengambil bahagian dalam program kesetiaan kami (loyaltyScheme_loyCustomers). Apabila memilih pilihan pertama, anda mungkin akan mendapat lebih banyak keputusan kerana pelanggan perlu wujud dalam satu entiti tambahan.

## <a name="manage-existing-relationships"></a>Urus perhubungan yang sedia ada 

Pada halaman Perhubungan, setiap perhubungan diwakili oleh baris. 

Pilih perhubungan dan pilih salah satu daripada pilihan berikut: 
 
- **Edit**: Kemas kini sifat perhubungan tersuai dalam anak tetingkap edit dan simpan perubahan.
- **Padam**: Padam perhubungan tersuai.
- **Lihat**: Lihat perhubungan yang dicipta sistem dan diwarisi. 

## <a name="next-step"></a>Langkah seterusnya

Sistem dan perhubungan tersuai digunakan untuk [mencipta segmen](segments.md) dan [ukuran](measures.md) berdasarkan sumber data berganda yang tidak lagi siloed.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
