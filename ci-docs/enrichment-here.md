---
title: Memperkayakan profil pelanggan dengan TEKNOLOGI SINI (pratonton)
description: Maklumat umum tentang pengayaan pihak ketiga HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052062"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Memperkayakan profil pelanggan dengan TEKNOLOGI SINI (pratonton)

HERE Technologies adalah syarikat platform lokasi yang menyediakan data dan perkhidmatan yang mengutamakan lokasi. PERKHIDMATAN pengayaan data TEKNOLOGI DI SINI meningkatkan ketepatan maklumat lokasi mengenai pelanggan anda. Ia menyediakan normalisasi alamat, pengekstrakan latitud dan longitud, dan banyak lagi.

## <a name="prerequisites"></a>Prasyarat

- Langganan TEKNOLOGI SINI yang aktif. Untuk mendapatkan langganan, [daftar di sini](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) atau [hubungi SINI Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) secara langsung. [Ketahui lebih lanjut tentang Pengayaan Lokasi HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Sambungan [DI](connections.md) SINI dikonfigurasikan [oleh](#configure-the-connection-for-here-technologies) pentadbir.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigurasikan sambungan untuk HERE Technologies

Anda mesti menjadi [pentadbir](permissions.md#admin) dalam Wawasan Pelanggan dan mempunyai kekunci API TEKNOLOGI SINI yang aktif.

1. Pilih **Tambah sambungan** apabila mengkonfigurasi pengayaan, atau pergi ke **Sambungan** > **Pentadbir** dan pilih **Sediakan** pada jubin Teknologi SINI.

1. Masukkan nama untuk sambungan dan kekunci API TEKNOLOGI SINI yang sah.

1. Semak dan berikan persetujuan anda untuk [privasi dan pematuhan Data](#data-privacy-and-compliance) dengan memilih **Saya bersetuju**.

1. Pilih **Sahkan** untuk mengesahkan konfigurasi dan kemudian pilih **Simpan**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Halaman konfigurasi sambungan HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke HERE Technologies, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data berpotensi sensitif seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa HERE Technologies memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar pengayaan ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya di **Lokasi** dari jubin Teknologi DI SINI.

   :::image type="content" source="media/HERE-tile.png" alt-text="Jubin HERE Technologies.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Pilih sambungan. Hubungi pentadbir jika tidak tersedia.

1. Pilih **Seterusnya**.

1. **Pilih set** data Pelanggan dan pilih profil atau segmen yang ingin anda memperkayakan dengan data dari SINI Technologies. Entiti *Pelanggan* memperkayakan semua profil pelanggan anda sedangkan segmen hanya memperkayakan profil pelanggan yang terkandung dalam segmen tersebut.

1. Tentukan jenis medan daripada profil bersatu anda untuk digunakan untuk pemadanan: alamat utama dan/atau sekunder. Anda boleh menentukan pemetaan medan untuk kedua-dua alamat dan memperkayakan profil untuk kedua-dua alamat secara berasingan. Sebagai contoh, untuk alamat rumah dan alamat perniagaan. Pilih **Seterusnya**.

1. Petakan medan anda ke data dari TEKNOLOGI SINI. Medan **Jalan 1** dan **Poskod** diperlukan untuk alamat utama dan/atau sekunder yang dipilih. Untuk ketepatan padanan yang lebih tinggi, tambah lebih banyak medan.

1. Pilih **Seterusnya** untuk melengkapkan pemetaan medan.

1. **Berikan Nama** untuk pengayaan dan **nama** entiti Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Jalankan** untuk memulakan proses pengayaan atau hampir untuk kembali ke **halaman Pengayaan**.

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

**Bilangan pelanggan yang diperkaya oleh lapangan** menyediakan gerudi ke dalam liputan setiap medan yang diperkaya.

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
