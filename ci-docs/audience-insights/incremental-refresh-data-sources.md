---
title: Segar semula tokokan untuk sumber data berasaskan Power Query
description: Segar semula data baharu dan yang dikemas kini untuk sumber data besar berdasarkan Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: f614d701aeb06720a60b14549a7fe666f8fe0617
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900279"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Segar semula peningkatan untuk sumber data berasaskan Power Query

Artikel ini membincangkan cara mengkonfigurasikan segar semula tambahan untuk sumber data berdasarkan Power Query.

Segar semula peningkatan untuk sumber data memberikan kelebihan berikut:

- **Lebih cepat menyegar semula** - Hanya data yang telah diubah akan disegar semula. Sebagai contoh, anda mungkin menyegar semula hanya lima hari yang lalu daripada set data yang bersejarah.
- **Kebolehpercayaan dipertingkat** - Dengan menyegarkan semula yang lebih kecil, anda tidak perlu mengekalkan sambungan ke sistem sumber yang tidak menentu untuk jangka masa panjang, mengurangkan risiko isu sambungan.
- **Penggunaan sumber dikurangkan** - Menyegar semula hanya sebahagian daripada jumlah data anda yang membawa kepada penggunaan sumber pengkomputeran yang lebih cekap dan mengurangkan jejak alam.

## <a name="configure-incremental-refresh"></a>Konfigurasikan segar semula tokokan

Insights khalayak membenarkan segar semula tokokan untuk sumber data yang diimport melalui Power Query yang menyokong pengingesan tokokan. Sebagai contoh, pangkalan data SQL Azure dengan medan tarikh dan masa, yang menunjukkan apabila rekod data terakhir dikemas kini.

1. [Cipta sumber data baharu berdasarkan Power Query](connect-power-query.md).

1. Berikan **Nama** untuk sumber data.

1. Pilih sumber data yang menyokong segar semula tambahan, seperti [pangkalan data Azure SQL](/power-query/connectors/azuresqldatabase).

1. Pilih entiti atau jadual untuk dimasukkan.

1. Lengkapkan langkah-langkah transformasi dan pilih **Seterusnya**.

1. Dalam kotak dialog **Tetapkan segar semula tokokan**, pilih **Sediakan** untuk membuka **Tetapan segar semula tokokan**. Jika anda memilih **Langkau**, sumber data akan menyegar semula keseluruhan set data.
   > [!TIP]
   > Anda juga boleh menggunakan segar semula tokokan kemudian dengan mengedit sumber data sedia ada.

1. Pada **Tetapan segar semula tokokan**, anda akan mengkonfigurasi segar semula tokokan untuk semua entiti yang anda pilih semasa mencipta sumber data.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Konfigurasikan entiti dalam sumber data untuk segar semula tokokan.":::

1. Pilih entiti dan berikan butiran berikut:

   - **Takrifkan kunci utama**: Pilih kunci utama untuk entiti atau jadual.
   - **Takrifkan medan "terakhir dikemas kini"**": Medan ini hanya akan memaparkan atribut jenis tarikh atau masa. Pilih atribut yang menunjukkan apabila rekod terakhir dikemas kini. Ia akan digunakan untuk mengenal pasti rekod yang berada dalam lingkungan peningkatan segar semula jangka masa.
   - **Semak untuk setiap kemas kini**: Tentukan tempoh masa yang anda mahu untuk tempoh masa segar semula tokokan.

1. Pilih **Simpan** untuk melengkapkan penciptaan sumber data. Segar semula data awal akan menjadi segar semula sepenuhnya. Selepas itu, segar semula data tokokan berlaku seperti yang dikonfigurasikan dalam langkah sebelumnya.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
