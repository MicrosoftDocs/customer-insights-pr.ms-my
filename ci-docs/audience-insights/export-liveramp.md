---
title: LiveRamp penyambung
description: Ketahui cara mengkonfigurasikan sambungan dan eksport ke LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: f9a0a88fb58897e4d279c181f4cdb4f6c852da60
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618946"
---
# <a name="export-segments-to-liverampreg-preview"></a>Eksport segmen ke LiveRamp&reg; (pratonton)

Aktifkan data anda dalam LiveRamp untuk berhubung dengan lebih daripada 500 platform merentasi digital, sosial, dan TV. Bekerja dengan data anda dalam LiveRamp untuk mensasar, menahan, dan memperibadikan kempen iklan.

## <a name="prerequisites-for-a-connection"></a>Prasyarat untuk sambungan

- Anda memerlukan langganan LiveRamp untuk menggunakan penyambung ini.
- Untuk mendapatkan langganan, [hubungi LiveRamp](https://liveramp.com/contact/) secara terus. [Ketahui lanjut tentang Penyertaan LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Sediakan sambungan ke LiveRamp

1. Pergi ke **Pentadbir** > **Sambungan**.

1. Pilih **Tambah sambungan** dan pilih **LiveRamp** untuk mengkonfigurasikan sambungan.

1. Berikan sambungan anda nama yang dikenali dalam medan **Nama paparan**. Nama dan jenis sambungan menerangkan sambungan ini. Kami mengesyorkan agar anda memilih nama yang menerangkan tujuan dan sasaran sambungan.

1. Pilih individu yang boleh menggunakan sambungan ini. Jika anda tidak mengambil tindakan, lalai akan menjadi Pentadbir. Untuk maklumat lanjut, lihat [Benarkan penyumbang untuk menggunakan sambungan untuk eksport](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sediakan **Nama Pengguna** dan **Kata Laluan** untuk akaun LiveRamp Secure FTP (SFTP).
Kelayakan ini berkemungkinan berbeza daripada kelayakan Penyertaan LiveRamp anda.

1. Pilih **Sahkan** untuk menguji sambungan ke LiveRamp.

1. Selepas pengesahan berjaya, sediakan keizinan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.

1. Pilih **Simpan** untuk melengkapkan sambungan.

## <a name="configure-an-export"></a>Konfigurasikan eksport

Anda boleh mengkonfigurasikan eksport ini jika anda mempunyai akses ke sambungan jenis ini. Untuk maklumat lanjut, lihat [Keizinan yang diperlukan untuk mengkonfigurasikan eksport](export-destinations.md#set-up-a-new-export).

1. Pergi ke **Data** > **Eksport**.

1. Untuk mencipta eksport baharu, pilih **Tambah destinasi**.

1. Dalam medan **Sambungan untuk eksport**, pilih sambungan dari bahagian LiveRamp. Jika anda tidak nampak nama bahagian ini, tiada sambungan jenis ini tersedia untuk anda.

1. Dalam medan **Pilih pengecam kunci anda**, pilih **E-mel**,  **Nama dan alamat**, atau **Telefon** untuk menghantar ke LiveRamp untuk penyelesaian identiti.
   > [!div class="mx-imgBorder"]
   > ![Penyambung LiveRamp dengan atribut pemetaan.](media/export-liveramp-segments.png "Penyambung LiveRamp dengan atribut pemetaan")

1. Peta atribut yang sepadan daripada entiti *Pelanggan* anda untuk pengecam kunci yang dipilih.

1. Pilih **Tambah atribut** untuk memetakan lebih banyak atribut untuk dihantar ke LiveRamp.

   > [!TIP]
   > Menghantar lebih banyak atribut pengecam kunci ke LiveRamp mempunyai kemungkinan besar untuk anda mendapatkan kadar pemadanan yang tinggi.

1. Pilih segmen yang anda mahu eksport ke LiveRamp.

1. Pilih **Simpan**.

Menyimpan eksport tidak menjalankan eksport dengan serta-merta.

Eksport berjalan dengan setiap [segar semula yang dijadualkan](system.md#schedule-tab). Anda juga boleh [mengeksport data atas permintaan](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke LiveRamp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa LiveRamp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
