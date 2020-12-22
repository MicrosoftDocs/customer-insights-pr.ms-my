---
title: Segar semula tokokan untuk sumber data berasaskan Power Query
description: Segar semula data baharu dan yang dikemas kini untuk sumber data besar berdasarkan Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b7e834f5f2fd1328563139675d7f850008348734
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/03/2020
ms.locfileid: "4406469"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Segar semula peningkatan untuk sumber data berasaskan Power Query

Segar semula peningkatan untuk sumber data memberikan kelebihan berikut:

- **Lebih cepat menyegar semula** - Hanya data yang telah diubah akan disegar semula. Sebagai contoh, anda mungkin menyegar semula hanya lima hari yang lalu daripada set data yang bersejarah.
- **Kebolehpercayaan dipertingkat** - Dengan menyegarkan semula yang lebih kecil, anda tidak perlu mengekalkan sambungan ke sistem sumber yang tidak menentu untuk jangka masa panjang, mengurangkan risiko isu sambungan.
- **Penggunaan sumber dikurangkan** - Menyegar semula hanya sebahagian daripada jumlah data anda yang membawa kepada penggunaan sumber pengkomputeran yang lebih cekap dan mengurangkan jejak alam.

## <a name="configure-incremental-refresh"></a>Konfigurasikan segar semula tokokan

Insights khalayak membenarkan segar semula tokokan untuk sumber data yang diimport melalui Power Query yang menyokong pengingesan tokokan. Sebagai contoh, pangkalan data SQL Azure dengan medan tarikh dan masa, yang menunjukkan apabila rekod data terakhir dikemas kini.

1. [Cipta sumber data baharu berdasarkan Power Query](connect-power-query.md).

1. Berikan nama untuk sumber data.

1. Pilih sumber data yang menyokong segar semula tokokan, seperti pangkalan data SQL Azure.

1. Pilih entiti atau jadual untuk dimasukkan.

1. Lengkapkan langkah-langkah transformasi dan pilih **Seterusnya**.

1. Dalam kotak dialog **Tetapkan segar semula tokokan**, pilih **Sediakan** untuk membuka **Tetapan segar semula tokokan**. Jika anda memilih **Langkau**, sumber data akan menyegar semula keseluruhan set data.
   > [!TIP]
   > Anda juga boleh menggunakan segar semula tokokan kemudian dengan mengedit sumber data sedia ada.

1. Pada **Tetapan segar semula tokokan**, anda akan mengkonfigurasi segar semula tokokan untuk semua entiti yang anda pilih semasa mencipta sumber data.

   > [!div class="mx-imgBorder"]
   > ![Konfigurasikan entiti dalam sumber data untuk segar semula tokokan](media/incremental-refresh-settings.png "Konfigurasikan entiti dalam sumber data untuk segar semula tokokan")

1. Pilih entiti dan berikan butiran berikut:

   - **Takrifkan kunci utama**: Pilih kunci utama untuk entiti atau jadual.
   - **Takrifkan medan "terakhir dikemas kini"**": Medan ini hanya akan memaparkan atribut jenis tarikh atau masa. Pilih atribut yang menunjukkan apabila rekod terakhir dikemas kini. Ia akan digunakan untuk mengenal pasti rekod yang berada dalam lingkungan peningkatan segar semula jangka masa.
   - **Semak untuk setiap kemas kini**: Tentukan tempoh masa yang anda mahu untuk tempoh masa segar semula tokokan.

1. Pilih **Simpan** untuk melengkapkan penciptaan sumber data. Segar semula data awal akan menjadi segar semula sepenuhnya. Selepas itu, segar semula data tokokan berlaku seperti yang dikonfigurasikan dalam langkah sebelumnya.
