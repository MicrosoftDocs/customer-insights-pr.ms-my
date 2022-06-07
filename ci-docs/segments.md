---
title: Segmen dalam Wawasan Pelanggan
description: Gambaran keseluruhan pada segmen dan cara mencipta dan mengurus segmen.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800753"
---
# <a name="segments-overview"></a>Gambaran keseluruhan segmen

Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku. Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.

Profil pelanggan yang sepadan dengan penapis bagi definisi segmen dirujuk sebagai *ahli* segmen. Sesetengah [had perkhidmatan](/dynamics365/customer-insights/service-limits) diguna pakai.

## <a name="create-a-new-segment"></a>Cipta bahagian baharu

Terdapat berbilang cara untuk mencipta segmen baharu: 

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- Segmen kompleks dengan pembina segmen: [Bina yang sendiri](segment-builder.md#create-a-new-segment) 
- Segmen ringkas dengan satu operator: [Segmen pantas](segment-builder.md#quick-segments) 
- Cara dikuasai AI untuk mencari pelanggan yang serupa: [Pelanggan Serupa](find-similar-customer-segments.md) 
- Cadangan dikuasai AI berdasarkan pada ukuran atau atribut: [Segmen yang dicadangkan untuk meningkatkan ukuran](suggested-segments.md) 
- Cadangan berdasarkan pada aktiviti: [Segmen yang dicadangkan berdasarkan pada aktiviti pelanggan](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- Segmen kompleks dengan pembina segmen: [Bina yang sendiri](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Mengurus bahagian sedia ada

Pergi ke **halaman Segmen** untuk melihat semua segmen anda yang disimpan dan menguruskannya.

Setiap segmen diwakili oleh baris yang menyertakan maklumat tambahan tentang segmen.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmen yang dipilih dengan senarai juntai bawah pilihan dan pilihan yang tersedia." lightbox="media/segments-selected-segment.png":::

Tindakan berikut tersedia apabila anda memilih segmen:

- **Lihat** butiran segmen, termasuk trend kiraan ahli pratonton ahli segmen.
- **Muat turun** senarai ahli sebagai fail .CSV.
- **Edit** segmen untuk mengubah sifatnya.
- **Cipta duplikasi** segmen. Anda boleh memilih untuk mengedit sifatnya dengan segera atau menyimpan pendua.
- **Segar semula** segmen untuk memasukkan data terkini.
- **Aktifkan** atau **Nyahaktifkan** segmen. Untuk segmen tidak aktif, takrifan segmen wujud tetapi ia tidak mengandungi sebarang pelanggan lagi. Segmen aktif mencari pelanggan yang sepadan dengan definisi segmen. Jika [segar semula berjadual](system.md#schedule-tab) dikonfigurasikan, segmen yang tidak aktif mempunyai **Status** yang disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak pernah dicuba. Apabila segmen yang tidak aktif diaktifkan, ia akan menyegar semula dan akan disertakan dalam segar semula berjadual.
  Secara alternatif, anda boleh menggunakan kefungsian **Jadual kemudian** dalam juntai bawah **Aktifkan/Nyahaktifkan** untuk menetapkan tarikh dan masa pada masa depan untuk pengaktifan dan penyahaktifan segmen tertentu.
- **[Cari pelanggan](find-similar-customer-segments.md)** yang serupa dari segmen ini.
- **Nama semula** segmen.
- **Tag** untuk [menguruskan tag](work-with-tags-columns.md#manage-tags) untuk segmen.
- **Muat turun** senarai ahli sebagai fail .CSV.
- **Urus eksport** untuk melihat segmen berkaitan eksport dan uruskan eksport tersebut. [Ketahui lebih lanjut tentang eksport.](export-destinations.md)
- **Padamkan** segmen.
- **Lajur** untuk [menyesuaikan lajur](work-with-tags-columns.md#customize-columns) yang dipaparkan.
- **Tapis** untuk [menapis pada tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk dicari mengikut nama segmen.

## <a name="refresh-segments"></a>Segar semula segmen

Anda boleh memuatkan semula semua segmen serentak dengan memilih **Muat semula semua** pada halaman **Segmen** atau anda boleh memuatkan semula satu atau berbilang segmen apabila anda memilihnya dan memilih **Muat semula** daripada pilihan. Sebagai alternatif, anda boleh mengkonfigurasi segar semula pada **Pentadbir** > **Sistem** > **Jadual**. Apabila segar semula berulang dikonfigurasikan, peraturan berikut digunakan:

- Semua segmen dengan jenis **Dinamik** atau **Pengembangan** akan disegarkan semula secara automatik pada irama yang ditetapkan. Setelah segar semula selesai, **Status** menunjukkan jika terdapat sebarang isu dalam menyegar semula segmen. Yang **terakhir disegarkan** menunjukkan cap masa bagi segar semula terakhir yang berjaya. Jika ralat berlaku, pilih ralat untuk melihat butiran tentang apa yang berlaku.
- Segmen dengan jenis **Statik** *tidak* akan disegar semula secara automatik. Terakhir **disegarkan** semula menunjukkan cap masa kali terakhir segmen statik dijalankan atau disegar semula secara manual.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Bahagian eksport

Anda boleh mengeksport segmen daripada halaman segmen atau [halaman eksport](export-destinations.md). 

1. Pergi ke halaman **Bahagian**.

1. Pilih elipsis menegak (&vellip;) untuk segmen yang anda ingin eksport.

1. Pilih **Urus eksport** daripada senarai juntai bawah tindakan.

1. Halaman **Eksport (pratonton) untuk segmen** dibuka. Anda boleh melihat semua eksport yang dikonfigurasikan dikumpulkan oleh sama ada ia mengandungi segmen semasa atau tidak.

   1. Untuk menambah segmen yang dipilih kepada eksport, **Edit** eksport masing-masing untuk memilih segmen yang sepadan kemudian simpan. Dalam persekitaran untuk pelanggan individu, anda boleh memilih eksport dalam senarai dan pilih **Tambah segmen** untuk mencapai hasil yang sama.

   1. Untuk mencipta eksport baharu dengan segmen yang dipilih, pilih **Tambah eksport**. Untuk mendapatkan maklumat lanjut tentang mencipta eksport, lihat [Sediakan eksport baharu](export-destinations.md#set-up-a-new-export).

1. Pilih **Kembali** untuk kembali ke halaman utama untuk segmen.

## <a name="track-usage-of-a-segment"></a>Jejaki penggunaan segmen

Jika anda menggunakan segmen dalam aplikasi, yang berdasarkan organisasi yang sama Microsoft Dataverse yang berkaitan dengan Wawasan Pelanggan, anda boleh menjejaki penggunaan segmen. Untuk [segmen Wawasan Pelanggan yang digunakan dalam perjalanan pelanggan Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), sistem memberitahu anda tentang penggunaan segmen tersebut.

Apabila mengedit segmen yang digunakan dalam persekitaran Wawasan Pelanggan atau dalam perjalanan pelanggan dalam Pemasaran, sepanduk dalam [pembangun](segment-builder.md) segmen memberitahu anda tentang kebergantungan. Anda boleh memeriksa butiran pergantungan terus dari sepanduk atau dengan **memilih Penggunaan** dalam pembangun segmen.

Anak **tetingkap penggunaan** Segmen menunjukkan butiran tentang penggunaan segmen ini dalam Dataverse aplikasi berasaskan. Untuk segmen yang digunakan dalam perjalanan pelanggan, anda akan menemui pautan untuk memeriksa perjalanan dalam Pemasaran di mana segmen ini digunakan. Sekiranya anda mempunyai kebenaran untuk mengakses aplikasi Pemasaran, anda boleh mengakses lebih banyak maklumat di sana.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Anak tetingkap sisi dengan butiran penggunaan segmen dalam pembina segmen.":::

Sistem ini memberitahu anda tentang penggunaan segmen yang dijejaki apabila anda cuba memadamkannya. Jika segmen yang akan anda padamkan digunakan dalam perjalanan pelanggan dalam Pemasaran, perjalanan tersebut akan berhenti untuk semua pengguna dalam segmen tersebut. Sekiranya perjalanan itu adalah sebahagian daripada kempen pemasaran, penghapusan akan mempengaruhi kempen tersebut sendiri. Walau bagaimanapun, anda masih boleh memadamkan segmen walaupun amaran.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Kotak dialog untuk mengesahkan penghapusan segmen apabila segmen digunakan dalam Dataverse aplikasi.":::

### <a name="supported-apps"></a>Aplikasi yang disokong

Penggunaan sedang dijejaki dalam aplikasi berasaskan berikut Dataverse:

- [Perjalanan pelanggan dalam Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Lihat sejarah pemprosesan dan ahli bahagian

anda boleh melihat penyatuan data tentang bahagian dengan menyemak semula butirannya.

Pada halaman **Bahagian**, pilih bahagian yang anda mahu semak semula.

Bahagian atas halaman termasuk graf trend yang menggambarkan perubahan dalam kiraan ahli. Tuding pada titik data untuk melihat kiraan ahli pada tarikh tertentu.

Anda boleh mengemas kini tempoh masa bagi visualisasi.

> [!div class="mx-imgBorder"]
> ![Julat masa segmen.](media/segment-time-range.png "Julat masa bahagian")

Bahagian bawah mengandungi senarai ahli bahagian.

> [!NOTE]
> Medan yang muncul dalam senarai adalah berasaskan pada atribut bagi entiti segmen anda.
>
>Senarai ialah pratonton bagi pemadanan ahli bahagian dan menunjukkan 100 rekod pertama bahagian anda supaya anda boleh segera menilainya dan menyemak semula definisinya jika perlu. Untuk melihat semua rekod yang sepadan, anda perlu [mengeksport bahagian](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
