---
title: Memperkayakan profil pelanggan dengan data identiti daripada LiveRamp (pratonton)
description: Memperkayakan profil pelanggan dengan data LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196359"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Memperkayakan profil pelanggan dengan data identiti daripada LiveRamp (pratonton)

LiveRamp menyediakan resolusi identiti luar talian yang menentukan dan penyatuan data pelanggan. Anda boleh memetakan pengecam peribadi dalam data pelanggan anda ke graf identiti AbiliTec dan menerima ID AbiliTec. Anda kemudian boleh menggunakan ID ini untuk penyatuan data pelanggan anda dengan lebih baik.

## <a name="supported-countriesregions"></a>Negara/rantau yang disokong

Kami kini menyokong memperkayakan profil pelanggan dengan data LiveRamp di Amerika Syarikat sahaja.

## <a name="prerequisites"></a>Prasyarat

- Langganan LiveRamp yang aktif. Untuk mendapatkan langganan, hubungi pasukan akaun LiveRamp anda atau untuk [dynamics@liveramp.com](mailto:dynamics@liveramp.com) maklumat lanjut.

- Langganan AbiliTec yang aktif dengan ID klien dan rahsia untuk mengakses API. Untuk maklumat lanjut, lihat [Hab Pembangun API AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Sambungan LiveRamp [dikonfigurasikan](connections.md) [oleh](#configure-the-connection-for-liveramp) pentadbir.

## <a name="configure-the-connection-for-liveramp"></a>Konfigurasikan sambungan untuk LiveRamp

Anda mesti menjadi [pentadbir](permissions.md#admin) dalam Wawasan Pelanggan dan mempunyai ID dan rahsia klien LiveRamp yang aktif.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan, atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Anak tetingkap konfigurasi untuk menyediakan sambungan ke perkhidmatan LiveRamp AbiliTec.":::

1. Masukkan nama untuk sambungan dan ID klien LiveRamp yang sah dan rahsia.

1. Semak dan berikan persetujuan anda untuk [privasi dan pematuhan Data](#data-privacy-and-compliance) dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke LiveRamp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights, termasuk data yang berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data tersebut mengikut arahan anda, tetapi anda bertanggungjawab untuk memastikan bahawa LiveRamp memenuhi sebarang kewajipan privasi atau keselamatan yang mungkin anda miliki. Untuk maklumat lanjut, semak [Kenyataan](https://go.microsoft.com/fwlink/?linkid=396732) Privasi Microsoft. Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **Identiti** daripada jubin LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Jubin identiti dalam halaman gambaran keseluruhan pengayaan.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Pilih sambungan. Hubungi pentadbir jika tiada sambungan tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan dengan data identiti dari LiveRamp. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk memadankan data identiti daripada LiveRamp. Sekurang-kurangnya satu daripada medan **Nama dan alamat**, **E-mel** atau **Telefon** diperlukan. Untuk ketepatan padanan yang lebih tinggi, tambah medan lain. Pilih **Seterusnya**.

1. Petakan medan anda ke data pengenalan daripada LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Pilihan pemetaan data untuk pengayaan LiveRamp.":::

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Berikan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Bilangan pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap medan yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

Bina di atas data pelanggan anda yang diperkaya. Gunakan ID AbiliTec untuk menyatukan profil pelanggan ke dalam pandangan berasaskan individu.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
