---
title: LiveRamp penyambung
description: Ketahui cara untuk mengeksport data ke LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667195"
---
# <a name="liverampreg-connector-preview"></a>Penyambung LiveRamp&reg; (pratonton)

Aktifkan data anda dalam LiveRamp untuk menyambung dengan 500 platform merentasi ekosistem digital, sosial, dan TV. Bekerja dengan data anda dalam LiveRamp untuk mensasar, menahan, dan memperibadikan kempen iklan.

## <a name="prerequisites"></a>Prasyarat

- Anda memerlukan langganan LiveRamp untuk menggunakan penyambung ini.
- Untuk mendapatkan langganan, [hubungi LiveRamp](https://liveramp.com/contact/) secara terus. [Ketahui lanjut tentang Penyertaan LiveRamp](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Sambung ke LiveRamp

1. Dalam wawasan khalayak, pergi ke **Pentadbir** > **Export destinasi**.

1. Dalam jubin **LiveRamp**, pilih **Sediakan**.

1. Berikan destinasi anda nama yang dikenali dalam medan **Nama paparan**.

1. Sediakan **Nama Pengguna** dan **Kata Laluan** untuk akaun LiveRamp Secure FTP (SFTP).
Kelayakan ini berkemungkinan berbeza daripada kelayakan Penyertaan LiveRamp anda.

1. Pilih **Sahkan** untuk menguji sambungan ke LiveRamp.

1. Selepas pengesahan berjaya, sediakan keizinan anda untuk **Privasi dan pematuhan data** dengan memilih kotak semak **Saya setuju**.

1. Pilih **Seterusnya** untuk menyediakan penyambung LiveRamp.

## <a name="configure-the-connector"></a>Konfigurasi penyambung

1. Dalam medan **Pilih pengecam kunci anda**, pilih **E-mel**,  **Nama dan alamat**, atau **Telefon** untuk menghantar ke LiveRamp untuk penyelesaian identiti.

1. Petakan atribut yang sepadan daripada entiti pelanggan disatukan anda untuk pengecam kunci yang dipilih.

1. Pilih **Tambah atribut** untuk memetakan atribut tambahan untuk dihantar ke LiveRamp.

   > [!TIP]
   > Menghantar lebih banyak atribut pengecam kunci ke LiveRamp mempunyai kemungkinan besar untuk anda mendapatkan kadar pemadanan yang tinggi.

1. Pilih segmen yang anda mahu eksport ke LiveRamp.

1. Pilih **Simpan**.

> [!div class="mx-imgBorder"]
> ![Penyambung LiveRamp dengan atribut pemetaan](media/export-liveramp-segments.png "Penyambung LiveRamp dengan atribut pemetaan")

## <a name="export-the-data"></a>Mengeksport data

Eksport akan bermula sebentar lagi jika kesemua prasyarat untuk mengeksport telah lengkap. Eksport juga akan berjalan dengan setiap [segar semula dijadualkan](system.md#schedule-tab).
Sebaik sahaja eksport berjaya diselesaikan, anda boleh mendaftar masuk ke Penyertaan LiveRamp untuk mengaktifkan dan mengedarkan data anda.

## <a name="data-privacy-and-compliance"></a>Privasi data dan pematuhan

Apabila anda mendayakan Dynamics 365 Customer Insights untuk menghantar data ke LiveRamp, anda membenarkan pemindahan data di luar sempadan pematuhan untuk Dynamics 365 Customer Insights termasuk data sensitif berpotensi seperti Data Peribadi. Microsoft akan memindahkan data sedemikian mengikut arahan anda tetapi anda bertanggungjawab untuk memastikan bahawa LiveRamp memenuhi sebarang kewajipan privasi atau keselamatan yang anda mungkin miliki. Untuk maklumat lanjut, lihat [Kenyataan Privasi Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Pentadbir Dynamics 365 Customer Insights anda boleh mengalih keluar destinasi eksport ini pada bila-bila masa untuk menamatkan penggunaan kefungsian ini.