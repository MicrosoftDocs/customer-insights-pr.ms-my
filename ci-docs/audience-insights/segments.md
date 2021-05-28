---
title: Segmen dalam wawasan khalayak
description: Gambaran keseluruhan pada segmen dan cara mencipta dan mengurus segmen.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a7fa6515bd6e79dedfb21aa0f0b8e24b873a6771
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034023"
---
# <a name="segments-overview"></a>Gambaran keseluruhan segmen

Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku. Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.

Profil pelanggan yang sepadan dengan penapis bagi definisi segmen dirujuk sebagai *ahli* segmen. Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.

## <a name="create-a-new-segment"></a>Cipta bahagian baharu

Terdapat berbilang cara untuk mencipta segmen baharu: 

- Segmen kompleks dengan pembina segmen: [Segmen kosong](segment-builder.md#create-a-new-segment)
- Segmen ringkas dengan satu operator: [Segmen pantas](segment-builder.md#quick-segments)
- Cara dikuasai AI untuk mencari pelanggan yang serupa: [Pelanggan Serupa](find-similar-customer-segments.md)
- Cadangan dikuasai AI berdasarkan pada ukuran atau atribut: [Segmen yang dicadangkan untuk meningkatkan ukuran](suggested-segments.md)
- Cadangan berdasarkan pada aktiviti: [Segmen yang dicadangkan berdasarkan pada aktiviti pelanggan](suggested-segments-activity.md)

## <a name="get-insights-on-existing-segments"></a>Dapatkan wawasan pada segmen sedia ada

Terokai maklumat tambahan sekitar segmen sedia ada dengan [Wawasan segmen](segment-insights.md). Ketahui apa yang membezakan dua segmen atau apa persamaan mereka.

## <a name="find-similar-customers"></a>Cari pelanggan serupa

Cari pelanggan yang serupa dengan ahli bagi segmen yang dipilih dengan bantuan kecerdasan buatan. Untuk maklumat lanjut, lihat [pelanggan serupa](find-similar-customer-segments.md).

## <a name="manage-existing-segments"></a>Mengurus bahagian sedia ada

Pergi ke halaman **Segmen** untuk anda melihat semua segmen yang disimpan dan mengurus segmen.

Setiap segmen diwakili oleh baris yang menyertakan maklumat tambahan tentang segmen.

> [!div class="mx-imgBorder"]
> ![Pilihan untuk menguruskan segmen sedia ada](media/segments-selected-segment.png "Pilihan untuk menguruskan segmen sedia ada")

Tindakan yang berikut tersedia apabila anda memilih segmen:

- **Lihat** butiran segmen, termasuk trend kiraan ahli pratonton ahli segmen.
- **Edit** segmen untuk mengubah sifatnya.
- **Cipta duplikasi** segmen. Anda boleh memilih untuk mengedit sifat dengan serta-merta atau hanya menyimpan duplikasi.
- **Segar semula** segmen untuk memasukkan data terkini.
- **Aktifkan** atau **Nyahaktifkan** segmen. Segmen mempunyai dua keadaan yang mungkin - aktif atau tidak aktif. Keadaan ini berguna apabila mengedit segmen. Untuk segmen tidak aktif, takrifan segmen wujud tetapi ia tidak mengandungi sebarang pelanggan lagi. Apabila anda mengaktifkan segmen, keadaannya berubah daripada 'tidak aktif' kepada 'aktif" dan ia mula mencari pelanggan yang sepadan dengan takrifan segmen. Jika [segar semula berjadual](system.md#schedule-tab) dikonfigurasikan, segmen yang tidak aktif mempunyai **Status** yang disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak pernah dicuba. Apabila segmen yang tidak aktif diaktifkan, ia akan menyegar semula dan akan disertakan dalam segar semula berjadual.
  Secara alternatif, anda boleh menggunakan kefungsian **Jadual kemudian** dalam juntai bawah **Aktifkan/Nyahaktifkan** untuk menetapkan tarikh dan masa pada masa depan untuk pengaktifan dan penyahaktifan segmen tertentu.
- **Nama semula** segmen.
- **Muat turun** senarai ahli sebagai fail .CSV.
- Pilihan **Tambahkan pada** menghantar senarai ID Pelanggan dalam segmen untuk pemprosesan dalam aplikasi lain.
- **Padamkan** segmen.

## <a name="refresh-segments"></a>Segar semula segmen

Anda boleh memuatkan semula semua segmen serentak dengan memilih **Muat semula semua** pada halaman **Segmen** atau anda boleh memuatkan semula satu atau berbilang segmen apabila anda memilihnya dan memilih **Muat semula** daripada pilihan. Sebagai alternatif, anda boleh mengkonfigurasi segar semula pada **Pentadbir** > **Sistem** > **Jadual**.

> [!TIP]
> Terdapat [enam jenis status](system.md#status-types) untuk tugas/proses. Selain itu, kebanyakan proses [bergantung pada proses hilir lain](system.md#refresh-policies). Anda boleh memilih status proses untuk melihat butiran mengenai kemajuan keseluruhan kerja. Selepas memilih **Lihat butiran** untuk salah satu tugas kerja, anda mencari maklumat tambahan: memproses masa, tarikh pemprosesan terakhir dan semua ralat dan amaran yang berkaitan dengan tugas.

## <a name="view-processing-history-and-segment-members"></a>Lihat sejarah pemprosesan dan ahli bahagian

anda boleh melihat penyatuan data tentang bahagian dengan menyemak semula butirannya.

Pada halaman **Bahagian**, pilih bahagian yang anda mahu semak semula.

Bahagian atas halaman termasuk graf trend yang menggambarkan perubahan dalam kiraan ahli. Tuding pada titik data untuk melihat kiraan ahli pada tarikh tertentu.

Anda boleh mengemas kini tempoh masa bagi visualisasi.

> [!div class="mx-imgBorder"]
> ![Julat masa bahagian](media/segment-time-range.png "Julat masa bahagian")

Bahagian bawah mengandungi senarai ahli bahagian.

> [!NOTE]
> Medan yang muncul dalam senarai adalah berasaskan pada atribut bagi entiti segmen anda.
>
>Senarai ialah pratonton bagi pemadanan ahli bahagian dan menunjukkan 100 rekod pertama bahagian anda supaya anda boleh segera menilainya dan menyemak semula definisinya jika perlu. Untuk melihat semua rekod yang sepadan, anda perlu [mengeksport bahagian](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
