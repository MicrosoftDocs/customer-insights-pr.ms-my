---
title: Gambaran keseluruhan segmen
description: Gambaran keseluruhan pada segmen dan cara mencipta dan mengurus segmen.
ms.date: 08/12/2022
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
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304806"
---
# <a name="segments-overview"></a>Gambaran keseluruhan segmen

Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku. Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.

Profil pelanggan atau kenalan yang sepadan dengan penapis definisi segmen dirujuk sebagai *ahli* segmen. Sesetengah [had perkhidmatan](/dynamics365/customer-insights/service-limits) diguna pakai.

## <a name="create-a-segment"></a>Cipta segmen

Pilih cara mencipta segmen berdasarkan khalayak sasaran anda.

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- Segmen kompleks dengan pembina segmen: [Bina sendiri](segment-builder.md)
- Segmen ringkas dengan satu operator: [Segmen pantas](segment-quick.md)
- Cara berkuasa AI untuk mencari pelanggan yang serupa: [Pelanggan serupa](find-similar-customer-segments.md)
- Cadangan berkuasa AI berdasarkan ukuran atau atribut: [Segmen yang dicadangkan berdasarkan langkah-langkah](suggested-segments.md)
- Cadangan berdasarkan pada aktiviti: [Segmen yang dicadangkan berdasarkan pada aktiviti pelanggan](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

Segmen akaun atau segmen kenalan (pratonton) dengan pembina segmen: [Bina sendiri](segment-builder.md)

> [!NOTE]
> Kebanyakan destinasi eksport memerlukan maklumat hubungan untuk tujuan Pemasaran. Oleh itu, buat segmen kenalan untuk digunakan untuk eksport tersebut.

---

## <a name="manage-existing-segments"></a>Mengurus bahagian sedia ada

Pergi ke **halaman Segmen untuk melihat segmen yang anda cipta, status dan keadaannya dan kali terakhir data disegar** semula. Anda boleh mengisih senarai segmen mengikut mana-mana lajur atau menggunakan kotak carian untuk mencari segmen yang anda ingin uruskan.

> [!TIP]
> Dalam persekitaran B-ke-B, **lajur Jenis** Khalayak mengenal pasti sama ada segmen berdasarkan akaun atau kenalan.

Pilih segmen untuk melihat tindakan yang tersedia.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmen yang dipilih dengan senarai juntai bawah pilihan dan pilihan yang tersedia." lightbox="media/segments-selected-segment.png":::

- [**Lihat**](#view-segment-details) butiran segmen, termasuk trend kiraan ahli dan pratonton ahli segmen.
- **Muat turun** senarai ahli sebagai fail .CSV.
- **Edit** segmen untuk mengubah sifatnya.
- **Cipta duplikasi** segmen. Anda boleh memilih untuk mengedit sifatnya dengan segera atau menyimpan pendua.
- [**Segar semula**](#refresh-segments) segmen untuk memasukkan data terkini.
- **Aktifkan** atau **Nyahaktifkan** segmen. Segmen tidak aktif tidak akan disegar semula semasa segar semula berjadual [dan](schedule-refresh.md) mempunyai Status **yang disenaraikan sebagai** Dilangkau **, menunjukkan bahawa segar** semula tidak dicuba. Segmen aktif disegar semula berdasarkan jenisnya: statik atau dinamik.
- **Buat statik** atau **Buat dinamik** jenis segmen. Segmen statik mesti disegar semula secara manual. Segmen dinamik disegar semula secara automatik semasa segar semula sistem.
- [**Cari pelanggan**](find-similar-customer-segments.md) yang serupa dari segmen ini.
- **Nama semula** segmen.
- **Tag** untuk [menguruskan tag](work-with-tags-columns.md#manage-tags) bagi segmen.
- [**Menguruskan eksport**](#export-segments) untuk melihat segmen berkaitan eksport dan menguruskannya. [Ketahui lebih lanjut tentang eksport.](export-destinations.md)
- **Padamkan** segmen.
- **Lajur** untuk [menyesuaikan lajur](work-with-tags-columns.md#customize-columns) yang dipaparkan.
- **Penapis** untuk [menapis pada tag](work-with-tags-columns.md#filter-on-tags).
- **Cari nama** untuk mencari mengikut nama segmen.

## <a name="view-segment-details"></a>Lihat butiran segmen

Pada halaman **Segmen**, pilih segmen untuk melihat sejarah pemprosesan dan ahli segmen.

Bahagian atas halaman termasuk graf trend yang menggambarkan perubahan dalam kiraan ahli. Tuding pada titik data untuk melihat kiraan ahli pada tarikh tertentu. Mengubah tempoh masa penggambaran.

:::image type="content" source="media/segment-time-range.png" alt-text="Julat masa segmen.":::

Bahagian bawah mengandungi senarai ahli bahagian.

> [!NOTE]
> Medan yang muncul dalam senarai adalah berasaskan pada atribut bagi entiti segmen anda.
>
> Senarai ialah pratonton bagi pemadanan ahli bahagian dan menunjukkan 100 rekod pertama bahagian anda supaya anda boleh segera menilainya dan menyemak semula definisinya jika perlu. Untuk melihat semua rekod yang sepadan, pilih **Lihat lagi** yang membuka [**halaman Entiti**](entities.md) atau [mengeksport segmen](export-destinations.md).

## <a name="refresh-segments"></a>Segar semula segmen

Segmen boleh disegar semula pada jadual automatik atau disegar semula secara manual atas permintaan. Untuk menyegar semula satu atau lebih segmen secara manual, pilihnya semula dan pilih **Segar Semula**.

Untuk [menjadualkan segar semula](schedule-refresh.md) automatik, pergi ke **Jadual** > **Sistem** > **Pentadbir**. Peraturan berikut dikenakan:

- Semua segmen dengan jenis **Dinamik** atau **Pengembangan** akan disegar semula secara automatik pada kadens yang ditetapkan. Setelah segar semula selesai, **Status** menunjukkan jika terdapat sebarang isu dalam menyegar semula segmen. Yang **Terakhir disegar semula** menunjukkan cap masa segar semula terakhir yang berjaya. Jika ralat berlaku, pilih ralat untuk melihat butiran tentang perkara yang berlaku.
- Segmen dengan jenis **Statik** *tidak* akan disegar semula secara automatik. Yang **Terakhir disegar semula** menunjukkan cap masa kali terakhir segmen statik dijalankan atau disegar semula secara manual.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Bahagian eksport

Eksport segmen ke aplikasi lain untuk terus menggunakan data. Mengeksport segmen daripada halaman segmen atau [halaman](export-destinations.md) eksport.

1. Pergi ke **halaman Segmen** dan pilih segmen yang ingin anda eksport.

1. Pilih **Urus eksport**. Halaman **Eksport (pratonton) untuk segmen** dibuka. Lihat semua eksport dikonfigurasikan yang dikumpulkan sama ada ia mengandungi segmen semasa atau tidak.

   1. Untuk menambah segmen yang dipilih kepada eksport, **Edit** eksport masing-masing untuk memilih segmen yang sepadan kemudian simpan. Dalam persekitaran untuk pelanggan individu, pilih eksport dalam senarai dan pilih **Tambah segmen** untuk mencapai hasil yang sama.

   1. Untuk mencipta eksport baharu dengan segmen yang dipilih, pilih **Tambah eksport**. Untuk mendapatkan maklumat lanjut tentang mencipta eksport, lihat [Sediakan eksport baharu](export-destinations.md#set-up-a-new-export).

1. Pilih **Kembali** untuk kembali ke halaman utama untuk segmen.

## <a name="track-usage-of-a-segment"></a>Menjejak penggunaan segmen

Jika anda menggunakan segmen dalam aplikasi yang berdasarkan organisasi yang sama Microsoft Dataverse yang berkaitan dengan Wawasan Pelanggan, anda boleh menjejaki penggunaan segmen. Untuk [segmen Wawasan Pelanggan yang digunakan dalam perjalanan pelanggan Pemasaran](/dynamics365/marketing/real-time-marketing-ci-profile) Dynamics 365, sistem ini memberitahu anda tentang penggunaan segmen tersebut.

Semasa mengedit segmen yang digunakan dalam persekitaran Wawasan Pelanggan, atau dalam perjalanan pelanggan dalam Pemasaran, sepanduk dalam [pembangun](segment-builder.md) segmen memberitahu anda tentang kebergantungan. Periksa butiran pergantungan terus dari sepanduk atau dengan **memilih Penggunaan** dalam pembina segmen.

Anak **tetingkap penggunaan** Segmen menunjukkan butiran tentang penggunaan segmen ini dalam Dataverse aplikasi berasaskan. Untuk segmen yang digunakan dalam perjalanan pelanggan, anda akan menemui pautan untuk memeriksa perjalanan dalam Pemasaran di mana segmen ini digunakan. Jika anda mempunyai keizinan untuk mengakses aplikasi Pemasaran, lihat butiran lanjut di sana.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Anak tetingkap sisi dengan butiran penggunaan segmen dalam pembina segmen.":::

Sistem ini memberitahu anda tentang penggunaan segmen yang dijejaki apabila anda cuba memadamkannya. Jika segmen yang akan anda padamkan digunakan dalam perjalanan pelanggan dalam Pemasaran, perjalanan itu akan berhenti untuk semua pengguna dalam segmen tersebut. Sekiranya perjalanan itu adalah sebahagian daripada kempen pemasaran, penghapusan akan mempengaruhi kempen itu sendiri. Walau bagaimanapun, anda masih boleh memadamkan segmen walaupun terdapat amaran.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Kotak dialog untuk mengesahkan pemadaman segmen apabila segmen digunakan dalam Dataverse aplikasi.":::

### <a name="supported-apps"></a>Aplikasi yang disokong

Penggunaan kini dijejaki dalam aplikasi berasaskan berikut Dataverse:

- [Perjalanan pelanggan dalam Pemasaran Dynamics 365](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
