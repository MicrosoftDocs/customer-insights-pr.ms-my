---
title: Memperkayakan profil pelanggan dengan data daripada Microsoft Office 365 (pratonton)
description: Gunakan data proprietari untuk Microsoft Office memperkayakan profil pelanggan anda dengan data penglibatan.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 75762afb70814c8a81c1574ee7ea1553a2048737
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055685"
---
# <a name="enrich-customer-profiles-with-data-from-microsoft-office-365-preview"></a>Memperkayakan profil pelanggan dengan data daripada Microsoft Office 365 (pratonton)

Gunakan data untuk Microsoft Office 365 memperkayakan profil akaun pelanggan anda dengan cerapan tentang penglibatan melalui Office 365 apl. Data penglibatan terdiri daripada e-mel dan aktiviti mesyuarat, yang diagregatkan pada tahap akaun. Sebagai contoh, bilangan e-mel dari akaun perniagaan atau bilangan mesyuarat dengan akaun. Tiada data tentang pengguna individu disediakan.

## <a name="supported-countries-or-regions"></a>Negara atau rantau yang disokong

Kami kini menyokong kawasan berikut: UK, Eropah, Amerika Utara.

## <a name="prerequisites"></a>Prasyarat

- Lesen awan aktif Office 365.
- [Profil pelanggan bersatu](customer-profiles.md) berdasarkan [akaun perniagaan](work-with-business-accounts.md).
- Organisasi yang [Microsoft Dataverse dilampirkan](create-environment.md#step-3-connect-to-microsoft-dataverse) dalam persekitaran Wawasan Pelanggan anda.
- [Keizinan](permissions.md#admin) pentadbir.
- Persetujuan daripada pentadbir penyewa anda Office 365 untuk menggunakan Office 365 data untuk menyediakan **Wawasan untuk Organisasi** dalam aplikasi Dynamics 365.

## <a name="configure-the-enrichment"></a>Konfigurasikan pengayaan

1. Pergi ke **Data** > **Pengayaan** dan pilih tab **Terokai**.

1. Pilih **Memperkayakan data** saya pada **jubin Penglibatan** Akaun.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Jubin penglibatan akaun.":::

1. Semak semula gambaran keseluruhan dan kemudian pilih **Berikut**.

1. Masukkan alamat e-mel daripada organisasi anda yang mana data Office akan diagregatkan. Hanya data dari alamat e-mel yang disenaraikan diproses untuk komunikasi yang berkaitan. Amalan terbaik adalah menggunakan kumpulan e-mel, sebagai contoh, *pasukan* Jualan AS, yang boleh anda uruskan Office 365. Bilangan alamat e-mel dalam kumpulan diselesaikan dan ditunjukkan. Jumlah alamat e-mel mestilah sekurang-kurangnya 2 dan tidak boleh melebihi 2,500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Alamat e-mel penglibatan akaun.":::

1. Semak dan berikan persetujuan anda untuk [Office 365 persetujuan](#office-365-tenant-administrator-consent) pentadbir penyewa dengan **memilih Saya bersetuju**.

1. Pilih **Seterusnya**.

1. **Pilih set** data Kenalan dan pilih profil yang anda ingin memperkayakan. Pilih **Seterusnya**.

1. Petakan medan alamat e-mel kenalan dan pilih **Berikut**.

1. **Berikan Nama** untuk pengayaan dan **entiti** Output.

1. Pilih **Simpan pengayaan** selepas menyemak pilihan anda.

1. Pilih **Tutup** untuk kembali ke **halaman Pengayaan**.

### <a name="office-365-tenant-administrator-consent"></a>Office 365 persetujuan pentadbir penyewa

Persetujuan daripada Office 365 pentadbir penyewa diperlukan untuk mengaktifkan pengayaan. E-mel dihantar kepada Office 365 pentadbir penyewa apabila pengayaan disimpan, yang meminta mereka menyemak dan bersetuju untuk membenarkan aplikasi Dynamics 365 menggunakan data perusahaan Office 365 anda untuk menyediakan **Wawasan untuk Organisasi**. Pentadbir Office 365 penyewa juga boleh bersetuju secara langsung dalam konsol pentadbir mereka Office 365, dengan **memilih Wawasan untuk Organisasi**.

## <a name="running-the-enrichment-for-the-first-time"></a>Menjalankan pengayaan buat kali pertama

Apabila pengayaan dimulakan buat kali pertama, selepas Office 365 pentadbir penyewa telah memberikan persetujuan, muat turun data dari Office 365 bermula. Proses ini mengambil sedikit masa. Larian pengayaan pertama akan dijadualkan berlaku dengan kelewatan enam jam. Anda boleh melihat bilangan hari yang diliputi oleh data pada halaman gambaran keseluruhan penglibatan akaun selepas pengayaan selesai. Dengan jumlah data yang besar, jalankan pengayaan sekali lagi selepas beberapa hari. Ia memastikan data lengkap untuk keseluruhan tempoh masa, iaitu satu tahun.

Bergantung pada saiz data Office anda, ia mungkin mengambil masa beberapa jam untuk menjalankan pengayaan untuk dilengkapkan.

Apabila anda menjalankan pengayaan, Microsoft akan memproses data dalam Office 365 sempadan pematuhan untuk mencipta cerapan teragregat, yang kemudiannya ditambahkan pada persekitaran Wawasan Pelanggan anda. Tiada data pada peringkat individu (contohnya, badan mana-mana jemputan e-mel atau kalendar) tersedia kepada pengguna Wawasan Pelanggan.

Pilih **Jalankan** untuk memulakan proses pengayaan.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Lihat hasil pengayaan

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Ini adalah *entiti Office*. *Office_UserEntity* mengandungi ID Active Directory untuk alamat e-mel yang dipilih semasa konfigurasi pengayaan.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Lihat data pengayaan pada kad pelanggan

Penglibatan akaun juga boleh dilihat pada kad pelanggan individu. Pergi ke **Pelanggan** dan pilih profil pelanggan. Dalam kad pelanggan, anda akan menemui skor penglibatan akaun, jumlah e-mel dan jumlah mesyuarat yang diagregatkan sepanjang tahun lalu. Anda juga menemui carta yang menunjukkan e-mel dan sejarah mesyuarat.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Kad pelanggan dengan data diperkaya.":::

## <a name="next-steps"></a>Langkah-langkah berikutnya

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Sebagai contoh, segmen yang mengandungi semua pelanggan yang mempunyai nilai lebih daripada 60 untuk *hari sejak e-mel* terakhir dan *hari sejak mesyuarat terakhir*. Segmen itu mengandungi akaun basi yang boleh anda cuba aktifkan semula.

[!INCLUDE [footer-include](includes/footer-banner.md)]
