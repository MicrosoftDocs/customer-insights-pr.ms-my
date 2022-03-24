---
title: Memperkayakan profil pelanggan dengan data dari Microsoft Office 365
description: Gunakan data proprietari untuk Microsoft Office memperkayakan profil pelanggan anda dengan data penglibatan.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 47239bd7f0c89742cf9c673bb2ebe4c41d853233
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376841"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Memperkayakan profil pelanggan dengan data penglibatan (pratonton)

Gunakan data untuk Microsoft Office 365 memperkayakan profil akaun pelanggan anda dengan cerapan tentang penglibatan melalui Office 365 apl. Data penglibatan terdiri daripada e-mel dan aktiviti mesyuarat, yang diagregatkan pada tahap akaun. Sebagai contoh, bilangan e-mel dari akaun perniagaan atau bilangan mesyuarat dengan akaun. Tiada data tentang pengguna individu disediakan. 

Pengayaan ini boleh didapati di kawasan berikut: UK, Eropah, Amerika Utara.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi pengayaan, prasyarat berikut mesti dipenuhi:

- Anda mempunyai lesen awan yang aktif Office 365.
- Anda mempunyai [profil pelanggan yang](customer-profiles.md) bersatu berdasarkan [akaun perniagaan](work-with-business-accounts.md).
- Persekitaran Wawasan Pelanggan anda mesti mempunyai organisasi yang [Microsoft Dataverse dilampirkan](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Anda mempunyai [keizinan pentadbir](permissions.md#admin).
- Anda telah, atau boleh mendapatkan, persetujuan daripada pentadbir penyewa anda Office 365 untuk menggunakan Office 365 data untuk menyediakan **Wawasan untuk Organisasi** dalam aplikasi Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan**.

1. Pergi ke **tab Discover** dan pilih **Memperkayakan data** saya pada **jubin Penglibatan** Akaun.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Jubin penglibatan akaun.":::
   
1. Pilih **Seterusnya** dalam **langkah Gambaran Keseluruhan** dan masukkan alamat e-mel daripada organisasi anda yang mana data Office akan diagregatkan. Hanya data dari alamat e-mel yang disenaraikan diproses untuk komunikasi yang berkaitan. Amalan terbaik ialah menggunakan kumpulan e-mel, sebagai contoh, *pasukan* Jualan AS, yang mudah diuruskan Office 365. Bilangan alamat e-mel dalam kumpulan diselesaikan dan ditunjukkan. Jumlah alamat e-mel mestilah sekurang-kurangnya 2 dan tidak boleh melebihi 2,500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Alamat e-mel penglibatan akaun.":::

1. Semak semula pernyataan persetujuan, pilih kotak **semak Saya bersetuju**, dan pilih **Seterusnya**.

1. Pilih set data pelanggan dan pilih **Seterusnya**.

1. Petakan medan alamat e-mel kenalan dan pilih **Berikut**.

1. Semak konfigurasi pengayaan, berikan nama pengayaan dan pilih **Simpan pengayaan** untuk menyimpan pengayaan.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 persetujuan pentadbir penyewa

Persetujuan daripada Office 365 pentadbir penyewa diperlukan untuk mengaktifkan pengayaan. E-mel dihantar kepada Office 365 pentadbir penyewa apabila pengayaan disimpan, yang meminta mereka menyemak dan bersetuju untuk membenarkan aplikasi Dynamics 365 menggunakan data perusahaan Office 365 anda untuk menyediakan **Wawasan untuk Organisasi**. Pentadbir Office 365 penyewa juga boleh bersetuju secara langsung dalam konsol pentadbir mereka Office 365, dengan **memilih Wawasan untuk Organisasi**.

## <a name="running-the-enrichment-for-the-first-time"></a>Menjalankan pengayaan buat kali pertama

Apabila pengayaan dimulakan buat kali pertama, selepas Office 365 pentadbir penyewa telah memberikan persetujuan, muat turun data dari Office 365 bermula. Proses ini mengambil sedikit masa. Larian pengayaan pertama akan dijadualkan berlaku dengan kelewatan enam jam. Anda boleh melihat bilangan hari yang diliputi oleh data pada halaman gambaran keseluruhan penglibatan akaun selepas pengayaan selesai. Dengan jumlah data yang besar, jalankan pengayaan sekali lagi selepas beberapa hari. Ia memastikan data lengkap untuk keseluruhan tetingkap masa, iaitu satu tahun.

Untuk memulakan proses, pilih **Jalankan** pada halaman Konfigurasi penglibatan Akaun. Selain itu, anda boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada segar semula [berjadual](system.md#schedule-tab). Secara lalai, pengayaan berjalan sekali seminggu.

Bergantung pada saiz data Office anda, ia mungkin mengambil masa beberapa jam untuk menjalankan pengayaan untuk dilengkapkan.

Apabila anda menjalankan pengayaan, Microsoft akan memproses data dalam Office 365 sempadan pematuhan untuk mencipta cerapan teragregat, yang kemudiannya ditambahkan pada persekitaran Wawasan Pelanggan anda. Tiada data pada peringkat individu (contohnya, badan mana-mana jemputan e-mel atau kalendar) tersedia kepada pengguna Wawasan Pelanggan. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas menjalankan proses pengayaan, pergi ke **pengayaan saya** untuk menyemak hasil pengayaan. Anda akan menemui jumlah pelanggan yang diperkaya dan gambaran keseluruhan hasil pengayaan. Ia termasuk bilangan e-mel dan mesyuarat yang diproses, bilangan hari yang mana data telah diagregatkan dan banyak lagi.

Anda juga akan menemui carta dengan bilangan pelanggan yang diperkaya dari masa ke masa dan pratonton data pengayaan.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pratonton hasil selepas menjalankan proses pengayaan.":::

Semua data diagregatkan sehingga tahap akaun. Sistem ini mengira skor penglibatan, yang berkisar antara 0 hingga 100, untuk setiap akaun. Skor penglibatan menyediakan ukuran komposit penglibatan akaun merentas e-mel dan mesyuarat berbanding akaun anda yang lain. Senarai berikut mengandungi data teragregat yang disediakan oleh pengayaan penglibatan akaun:



| Data                                                                              | Nama lajur                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skor penglibatan                                                                  |  EngagementScore                         |
| Bilangan e-mel ke akaun                                                       |  NoOfEmails_ToAccount                    |
| Bilangan e-mel daripada akaun                                                     |  NoOfEmails_FromAccount                  | 
| Bilangan mesyuarat yang dimulakan mengikut akaun                                           |  NoOfMeetings_FromAccount                | 
| Bilangan mesyuarat yang dimulakan oleh organisasi anda                                 |  NoOfMeetings_ToAccount                  | 
| Bilangan individu daripada organisasi anda dalam mesyuarat dengan akaun                  |  NoOfContactsInvolved_Meetings           | 
| Bilangan individu daripada organisasi anda dalam perbualan e-mel dengan akaun       |  NoOfContactsInvolved_Emails             | 
| Bilangan individu daripada akaun dalam mesyuarat dengan organisasi anda                  |  NoOfAccountContactsInvolved_Meetings    | 
| Bilangan individu daripada akaun dalam perbualan e-mel dengan organisasi anda       |  NoOfAccountContactsInvolved_Emails      | 
| Tarikh mula penglibatan (e-mel pertama atau mesyuarat dalam data)                        |  EngagementStartDate                     | 
| Hari sejak e-mel terakhir                                                             |  DaysSinceLastEmail                      | 
| Hari sejak mesyuarat terakhir                                                           |  DaysSinceLastMeeting                    | 
| Tempoh purata mesyuarat                                                      |  AverageDuration_Of_Meetings             | 
| Tempoh purata balasan e-mel daripada akaun                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Tarikh mula pengagregatan                                                            |  PengagregatanStartDate                    | 
| Aras pengagregatan (tahun, bulan atau minggu)                                          |  AggregationLevel                        | 


Semak semula data yang diperkaya dengan **memilih Lihat lebih lanjut** dalam seksyen pratonton. Ia membuka *entiti Office*. Anda juga boleh mencari entiti yang disenaraikan dalam **kumpulan Pengayaan** dalam **DataEntities** > **·**. Anda juga akan menemui *Office_UserEntity*, yang mengandungi ID Active Directory untuk alamat e-mel yang dipilih semasa konfigurasi pengayaan 

## <a name="see-enrichment-data-on-the-customer-card"></a>Lihat data pengayaan pada kad pelanggan

Penglibatan akaun juga boleh dilihat pada kad pelanggan individu. Pergi ke **Pelanggan** dan pilih profil pelanggan. Dalam kad pelanggan, anda akan menemui skor penglibatan akaun, jumlah e-mel dan jumlah mesyuarat yang diagregatkan sepanjang tahun lalu. Anda juga menemui carta yang menunjukkan e-mel dan sejarah mesyuarat.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Buat segmen dan langkah berdasarkan data yang diperkaya

Data yang diperkaya boleh digunakan untuk membuat segmen dan langkah-langkah seperti yang diperincikan di bawah. Sebagai contoh, segmen yang mengandungi semua pelanggan yang mempunyai nilai lebih daripada 60 untuk *hari sejak e-mel* terakhir dan *hari sejak mesyuarat* terakhir. Segmen itu mengandungi akaun basi yang boleh anda cuba aktifkan semula. 

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
