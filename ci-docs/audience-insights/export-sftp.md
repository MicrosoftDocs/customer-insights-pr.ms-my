---
title: Eksport data Customer Insights ke hos SFTP
description: Ketahui cara mengkonfigurasi sambungan ke hos SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643514"
---
# <a name="connector-for-sftp-preview"></a>Penyambung untuk SFTP (pratonton)

Gunakan data pelanggan anda dalam aplikasi pihak ketiga dengan mengeksportnya ke hos Protokol Pemindahan Fail Selamat (SFTP).

## <a name="prerequisites"></a>Prasyarat

- Ketersediaan hos SFTP dan kelayakan yang sepadan.

## <a name="connect-to-sftp"></a>Sambung ke SFTP

1. Pergi ke **Pentadbir** > **Destinasi Eksport**.

1. Di bawah **SFTP**, pilih **Sediakan**.

1. Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.

1. Menyediakan **Nama pengguna**, **Kata laluan** dan **Nama hos** untuk akaun SFTP anda. Contoh: Jika folder akar pelayan SFTP anda adalah /root/folder dan anda mahu data dieksport ke /root/folder/ci_export_destination_folder, hos tersebut sepatutnya menjadi sftp://<server_address>/ci_export_destination_folder".

1. Pilih **Sahkan** untuk menguji sambungan.

1. Selepas pengesahan berjaya, pilih jika anda mahu mengeksport data **Dizip** atau **Dinyahzip** dan pilih **pembatas medan** untuk fail yang dieksport.

1. Pilih **Saya bersetuju** untuk mengesahkan **Privasi dan pematuhan data**.

1. Pilih **Seterusnya** untuk memulakan konfigurasi eksport.

## <a name="configure-the-connection"></a>Konfigurasi sambungan

1. Pilih **atribut pelanggan** yang anda mahu eksport. Anda boleh eksport satu atau berbilang atribut.

1. Pilih **Seterusnya**.

1. Pilih segmen yang ingin anda eksport.

1. Pilih **Simpan**.

## <a name="export-the-data"></a>Mengeksport data

Anda boleh [eksport data atas permintaan](export-destinations.md). Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data melalui SFTP, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa destinasi eksport memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.
