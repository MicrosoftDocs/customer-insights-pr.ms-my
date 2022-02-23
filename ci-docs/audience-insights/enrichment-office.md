---
title: Memperkayakan profil pelanggan dengan data daripada Microsoft Office 365
description: Gunakan data proprietari Microsoft Office untuk memperkayakan profil pelanggan anda dengan data penglibatan.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889781"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Memperkayakan profil pelanggan dengan data penglibatan (pratonton)

Gunakan data Microsoft Office 365 untuk memperkayakan profil akaun pelanggan anda dengan wawasan tentang penglibatan melalui Office 365 apl. Data penglibatan terdiri daripada e-mel dan aktiviti mesyuarat, yang diagregatkan pada peringkat akaun. Sebagai contoh, bilangan e-mel daripada akaun perniagaan atau bilangan mesyuarat dengan akaun. Tiada data tentang pengguna individu disediakan. 

Pengayaan ini boleh didapati di kawasan berikut: UK, Eropah, Amerika Utara.

## <a name="prerequisites"></a>Prasyarat

Untuk mengkonfigurasi pengayaan, prasyarat berikut mesti dipenuhi:

- Anda mempunyai lesen awan yang Office 365 aktif.
- Anda mempunyai [profil pelanggan bersatu berdasarkan akaun](customer-profiles.md)[perniagaan](work-with-business-accounts.md).
- Persekitaran Wawasan Pelanggan anda mesti mempunyai [Microsoft Dataverse organisasi yang](create-environment.md#step-3-connect-to-microsoft-dataverse) dilampirkan.
- Anda mempunyai [keizinan](permissions.md#administrator) pentadbir.
- Anda mempunyai atau boleh mendapatkan persetujuan daripada pentadbir penyewa anda Office 365 untuk menggunakan data untuk menyediakan Wawasan bagi Organisasi dalam aplikasi Office 365 **Dynamics** 365.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Dalam wawasan khalayak, pergi ke **Data** > **Pengayaan**.

1. Pergi ke **tab Discover dan pilih** **Memperkayakan data saya** pada jubin Penglibatan **Akaun**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Jubin penglibatan akaun.":::
   
1. Pilih **Berikut dalam langkah** **Ikhtisar** dan masukkan alamat e-mel daripada organisasi anda yang data Office akan diagregatkan. Hanya data daripada alamat e-mel yang disenaraikan akan diproses untuk komunikasi yang berkaitan. Amalan terbaik adalah menggunakan kumpulan e-mel, sebagai contoh, *pasukan Jualan AS, yang mudah diuruskan* Office 365. Bilangan alamat e-mel dalam kumpulan diselesaikan dan ditunjukkan. Jumlah alamat e-mel mestilah sekurang-kurangnya 2 dan tidak boleh melebihi 2,500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Alamat e-mel penglibatan akaun.":::

1. Semak semula pernyataan persetujuan, pilih **kotak semak Saya** bersetuju, dan pilih **Seterusnya**.

1. Pilih set data pelanggan dan pilih **Seterusnya**.

1. Petakan medan alamat e-mel kenalan dan pilih **Seterusnya**.

1. Semak konfigurasi pengayaan, berikan nama pengayaan dan pilih **Simpan pengayaan** untuk menjimatkan pengayaan.

## <a name="office-365-tenant-administrator-consent"></a>Office 365 persetujuan pentadbir penyewa

Persetujuan daripada Office 365 pentadbir penyewa diperlukan untuk mengaktifkan pengayaan. E-mel dihantar kepada Office 365 pentadbir penyewa apabila pengayaan disimpan, yang meminta mereka menyemak dan membenarkan aplikasi Dynamics 365 menggunakan data perusahaan anda Office 365 untuk memberikan Wawasan untuk **Organisasi**. Office 365 Pentadbir penyewa juga boleh membenarkan secara langsung dalam konsol pentadbir Office 365 mereka, dengan memilih Wawasan untuk **Organisasi**.

## <a name="running-the-enrichment-for-the-first-time"></a>Menjalankan pengayaan untuk pertama kalinya

Apabila pengayaan dimulakan buat kali pertama, selepas Office 365 pentadbir penyewa telah memberikan persetujuan, muat turun data Office 365 bermula. Proses ini mengambil sedikit masa. Larian pengayaan pertama akan dijadualkan berlaku dengan kelewatan enam jam. Anda boleh melihat bilangan hari data meliputi pada halaman gambaran keseluruhan penglibatan akaun selepas pengayaan selesai. Dengan jumlah data yang besar, jalankan pengayaan sekali lagi selepas beberapa hari. Ia memastikan data lengkap untuk keseluruhan tetingkap masa, iaitu satu tahun.

Untuk memulakan proses, pilih **Jalankan pada halaman Konfigurasi penglibatan** akaun. Di samping itu, anda boleh membiarkan sistem menjalankan pengayaan secara automatik sebagai sebahagian daripada [segar semula berjadual](system.md#schedule-tab). Secara lalai, pengayaan berjalan sekali seminggu.

Bergantung pada saiz data Office anda, ia mungkin mengambil masa beberapa jam untuk pengayaan dijalankan untuk dilengkapkan.

Apabila anda menjalankan pengayaan, Microsoft akan memproses data dalam Office 365 sempadan pematuhan untuk mencipta wawasan teragregat, yang kemudiannya ditambahkan pada persekitaran Wawasan Pelanggan anda. Tiada data pada peringkat individu (contohnya, isi mana-mana e-mel atau jemputan kalendar) tersedia kepada pengguna Wawasan Pelanggan. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Keputusan pengayaan

Selepas menjalankan proses pengayaan, pergi ke **Pengayaan Saya** untuk mengkaji semula hasil pengayaan. Anda akan menemui jumlah pelanggan yang diperkaya dan gambaran keseluruhan hasil pengayaan. Ia termasuk bilangan e-mel dan mesyuarat yang diproses, bilangan hari yang data telah diagregatkan, dan banyak lagi.

Anda juga akan menemui carta dengan bilangan pelanggan yang diperkaya dari masa ke masa dan pratonton data pengayaan.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Pratonton hasil selepas menjalankan proses pengayaan.":::

Semua data diagregatkan sehingga tahap akaun. Sistem mengira skor penglibatan, yang berkisar antara 0 hingga 100, untuk setiap akaun. Skor penglibatan menyediakan ukuran komposit penglibatan akaun merentas e-mel dan mesyuarat berbanding akaun anda yang lain. Senarai berikut mengandungi data agregat yang disediakan oleh pengayaan penglibatan akaun:



| Data                                                                              | Nama lajur                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Skor penglibatan                                                                  |  EngagementScore                         |
| Bilangan e-mel ke akaun                                                       |  NoOfEmails_ToAccount                    |
| Bilangan e-mel daripada akaun                                                     |  NoOfEmails_FromAccount                  | 
| Bilangan mesyuarat yang dimulakan oleh akaun                                           |  NoOfMeetings_FromAccount                | 
| Bilangan mesyuarat yang dimulakan oleh organisasi anda                                 |  NoOfMeetings_ToAccount                  | 
| Bilangan individu daripada organisasi anda dalam mesyuarat dengan akaun                  |  NoOfContactsInvolved_Meetings           | 
| Bilangan individu daripada organisasi anda dalam perbualan e-mel dengan akaun       |  NoOfContactsInvolved_Emails             | 
| Bilangan individu daripada akaun dalam mesyuarat dengan organisasi anda                  |  NoOfAccountContactsInvolved_Meetings    | 
| Bilangan individu daripada akaun dalam perbualan e-mel dengan organisasi anda       |  NoOfAccountContactsInvolved_Emails      | 
| Tarikh mula penglibatan (e-mel atau mesyuarat pertama dalam data)                        |  EngagementStartDate                     | 
| Hari sejak e-mel terakhir                                                             |  DaysSinceLastEmail                      | 
| Hari sejak mesyuarat terakhir                                                           |  DaysSinceLastMeeting                    | 
| Tempoh purata mesyuarat                                                      |  AverageDuration_Of_Meetings             | 
| Tempoh purata balasan e-mel daripada akaun                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Tarikh mula pengagregatan                                                            |  PengagregatanStartDate                    | 
| Tahap pengagregatan (tahun, bulan atau minggu)                                          |  PengagregatanLevel                        | 


Semak semula data diperkaya dengan memilih **Lihat lagi dalam seksyen** pratonton. Ia membuka *entiti* Office. Anda juga boleh mencari entiti yang disenaraikan dalam **kumpulan Pengayaan** dalam Entiti **Data** > **·**. Anda juga akan menemui *Office_UserEntity*, yang mengandungi ID Active Directory untuk alamat e-mel yang dipilih semasa konfigurasi pengayaan 

## <a name="see-enrichment-data-on-the-customer-card"></a>Lihat data pengayaan pada kad pelanggan

Penglibatan akaun juga boleh dilihat pada kad pelanggan individu. Pergi ke **Pelanggan** dan pilih profil pelanggan. Dalam kad pelanggan, anda akan menemui skor penglibatan akaun, jumlah e-mel dan jumlah mesyuarat yang dikumpulkan sepanjang tahun lepas. Anda juga menemui carta yang menunjukkan e-mel dan sejarah mesyuarat.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Cipta segmen dan langkah berdasarkan data yang diperkaya

Data yang diperkaya boleh digunakan untuk membuat segmen dan langkah-langkah seperti yang diperincikan di bawah. Sebagai contoh, segmen yang mengandungi semua pelanggan yang mempunyai nilai lebih daripada 60 *selama berhari-hari sejak e-mel* terakhir dan hari sejak mesyuarat *terakhir*. Segmen itu mengandungi akaun basi yang anda boleh cuba mengaktifkan semula. 

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
