---
title: Segmen dalam wawasan khalayak
description: Gambaran keseluruhan pada segmen dan cara mencipta dan mengurus segmen.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 740d293b21f43b50201f23fcba109318823ef3af
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 01/15/2022
ms.locfileid: "7978070"
---
# <a name="segments-overview"></a>Gambaran keseluruhan segmen

Segmen membolehkan anda mengumpulkan pelanggan berdasarkan atribut demografi, transaksi atau tingkah laku. Anda boleh menggunakan segmen untuk kempen promosi sasaran, aktiviti jualan dan tindakan sokongan pelanggan untuk mencapai matlamat perniagaan anda.

Profil pelanggan yang sepadan dengan penapis bagi definisi segmen dirujuk sebagai *ahli* segmen. Sesetengah [had perkhidmatan](service-limits.md) diguna pakai.

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

Pergi ke halaman **Segmen** untuk anda melihat semua segmen yang disimpan dan mengurus segmen.

Setiap segmen diwakili oleh baris yang menyertakan maklumat tambahan tentang segmen.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmen yang dipilih dengan senarai juntai bawah pilihan dan pilihan yang tersedia.":::

Tindakan yang berikut tersedia apabila anda memilih segmen:

- **Lihat** butiran segmen, termasuk trend kiraan ahli pratonton ahli segmen.
- **Edit** segmen untuk mengubah sifatnya.
- **Cipta duplikasi** segmen. Anda boleh memilih untuk mengedit sifat dengan serta-merta atau hanya menyimpan duplikasi.
- **Segar semula** segmen untuk memasukkan data terkini.
- **Aktifkan** atau **Nyahaktifkan** segmen. Segmen mempunyai dua keadaan yang mungkin - aktif atau tidak aktif. Keadaan ini berguna apabila mengedit segmen. Untuk segmen tidak aktif, takrifan segmen wujud tetapi ia tidak mengandungi sebarang pelanggan lagi. Apabila anda mengaktifkan segmen, keadaannya berubah daripada 'tidak aktif' kepada 'aktif" dan ia mula mencari pelanggan yang sepadan dengan takrifan segmen. Jika [segar semula berjadual](system.md#schedule-tab) dikonfigurasikan, segmen yang tidak aktif mempunyai **Status** yang disenaraikan sebagai **Dilangkau**, menunjukkan bahawa segar semula tidak pernah dicuba. Apabila segmen yang tidak aktif diaktifkan, ia akan menyegar semula dan akan disertakan dalam segar semula berjadual.
  Secara alternatif, anda boleh menggunakan kefungsian **Jadual kemudian** dalam juntai bawah **Aktifkan/Nyahaktifkan** untuk menetapkan tarikh dan masa pada masa depan untuk pengaktifan dan penyahaktifan segmen tertentu.
- **Nama semula** segmen.
- **Muat turun** senarai ahli sebagai fail .CSV.
- **Urus eksport** untuk melihat segmen berkaitan eksport dan uruskan eksport tersebut. [Ketahui lebih lanjut tentang eksport.](export-destinations.md)
- **Padamkan** segmen.

## <a name="refresh-segments"></a>Segar semula segmen

Anda boleh memuatkan semula semua segmen serentak dengan memilih **Muat semula semua** pada halaman **Segmen** atau anda boleh memuatkan semula satu atau berbilang segmen apabila anda memilihnya dan memilih **Muat semula** daripada pilihan. Sebagai alternatif, anda boleh mengkonfigurasi segar semula pada **Pentadbir** > **Sistem** > **Jadual**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Bahagian eksport

Anda boleh mengeksport segmen daripada halaman segmen atau [halaman eksport](export-destinations.md). 

1. Pergi ke halaman **Bahagian**.

1. Pilih **Tunjukkan lagi [...]** untuk segmen yang ingin anda eksport.

1. Pilih **Urus eksport** daripada senarai juntai bawah tindakan.

1. Halaman **Eksport (pratonton) untuk segmen** dibuka. Anda boleh melihat semua eksport yang dikonfigurasikan dikumpulkan oleh sama ada ia mengandungi segmen semasa atau tidak.

   1. Untuk menambah segmen yang dipilih kepada eksport, **Edit** eksport masing-masing untuk memilih segmen yang sepadan kemudian simpan. Dalam persekitaran untuk pelanggan individu anda boleh memilih eksport dalam senarai dan pilih **Tambah segmen** untuk mencapai hasil yang sama.

   1. Untuk mencipta eksport baharu dengan segmen yang dipilih, pilih **Tambah eksport**. Untuk mendapatkan maklumat lanjut tentang mencipta eksport, lihat [Sediakan eksport baharu](export-destinations.md#set-up-a-new-export).

1. Pilih **Kembali** untuk kembali ke halaman utama untuk segmen.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
