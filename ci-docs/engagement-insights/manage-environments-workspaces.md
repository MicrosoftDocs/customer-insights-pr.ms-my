---
title: Urus ruang kerja dan persekitaran
description: Cara mencipta, menamakan semula dan memadam ruang kerja dan persekitaran.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 09cb3ddf0f8b4507b7eae6668ea3dad08cfcea29
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673808"
---
# <a name="manage-environments-and-workspaces"></a>Urus persekitaran dan ruang kerja

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Gambaran keseluruhan

Topik ini membincangkan cara untuk menguruskan ruang kerja dan persekitaran sebaik sahaja mereka sudah dicipta. 

- *Ruang kerja* ialah ruang untuk menyimpan dan mengurus peristiwa dan laporan. Ia merupakan tempat anda boleh melihat aktiviti pengguna dalam masa nyata. Apabila anda mencipta ruang kerja, anda memilih jenis data untuk dihantar ke ruang kerja. Pada masa ini, data web dan aplikasi mudah alih disokong. Untuk maklumat lanjut, lihat [Mencipta ruang kerja baru dan menambah ahli](create-workspace.md).

- *Persekitaran* ialah ruang tempat anda menguruskan ruang kerja dan sambungan anda. Untuk mendapatkan maklumat lanjut, lihat [Cipta persekitaran baharu](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Urus ruang kerja sedia ada

Anda boleh mengekalkan berbilang ruang kerja secara serentak dalam persekitaran. [Peranan](user-roles.md) anda menentukan cara anda bekerja dalam ruang kerja itu. 

 - Anda mestilah pentadbir persekitaran atau pentadbir ruang kerja untuk menguruskan ruang kerja.
 - Sebagai pentadbir ruang kerja, anda boleh menamakan semula ruang kerja sedia ada atau memadamkan ruang kerja tersebut. 

:::image type="content" source="media/workspace-edit.png" alt-text="Pusat pentadbir ruang kerja.":::

### <a name="edit-a-workspace-name"></a>Edit nama ruang kerja

1. Pergi ke **Pentadbir** > **Ruang Kerja** dan pilih **Tetapan**.

1. Dalam kotak **Nama ruang kerja**, masukkan nama baharu.

1. Pilih **Simpan** untuk menggunakan perubahan anda.

### <a name="delete-a-workspace"></a>Padamkan ruang kerja

Memadam ruang kerja secara kekal mengalih keluar semua kandungan, data, seting dan keizinannya secara kekal. Tindakan ini tidak boleh dibuat asal.

1. Pergi ke **Pentadbir** > **Ruang Kerja** dan pilih **Tetapan**.

1. Pilih **Padam ruang kerja**. 

1. Dalam dialog **Padam ruang kerja**, masukkan **SAHKAN PEMADAMAN** dalam semua caps. 

1. Pilih **Padam** untuk memadamkan ruang kerja secara kekal.

### <a name="manage-workspace-members"></a>Urus ahli ruang kerja

1. Pergi ke **Pentadbir** > **Ruang Kerja** dan pilih **Ahli**.

1. Pilih **Tambah ahli** untuk memberikan akses dan [menugaskan peranan](user-roles.md). Pada masa ini, hanya **Pentadbir ruang kerja** tersedia.

1. Pilih **Tambah ahli** untuk menambahkan mereka pada ruang kerja anda.

## <a name="manage-an-existing-environment"></a>Urus persekitaran sedia ada

Sebagai pentadbir persekitaran, anda boleh mencapai persekitaran daripada anak tetingkap navigasi kiri. Anda boleh mengkonfigurasikan tetapan persekitaran, pentadbir persekitaran lain dan ruang kerja. Pilih tab untuk beralih antara kawasan berbeza dalam pusat pentadbir.

:::image type="content" source="media/environment-edit.png" alt-text="Pusat pentadbiran persekitaran.":::

### <a name="edit-an-environment-name"></a>Mengedit nama persekitaran

1. Pergi ke **Pentadbir** > **Persekitaran** dan pilih **Tetapan**.

1. Kemas kini **Nama persekitaran** dan pilih **Simpan** untuk menggunakan perubahan anda.

### <a name="delete-an-environment"></a>Padamkan persekitaran

Pentadbir persekitaran boleh memadamkan persekitaran. Sebelum anda boleh memadamkan persekitaran, anda mesti mengalih keluar semua ruang kerja di bawahnya.

1. Pergi ke **Pentadbir** > **Persekitaran** dan pilih **Tetapan**.

1. Pilih **Padamkan persekitaran**. 

1. Dalam dialog **Padam ruang kerja**, masukkan **SAHKAN PEMADAMAN** dalam semua caps. 

1. Pilih **Padamkan** untuk memadamkan persekitaran secara kekal.

### <a name="manage-environment-members"></a>Urus ahli persekitaran

1. Pergi ke **Pentadbir** > **Persekitaran** dan pilih **Ahli**.

1. Pilih **Tambah ahli** untuk mengemas kini ahli dan [menugaskan peranan](user-roles.md). Pada masa ini, hanya **Pentadbir persekitaran** tersedia.

1. Pilih **Tambah ahli** untuk menambahkan mereka pada persekitaran anda.

## <a name="manage-connections"></a>Urus sambungan

Mewujudkan sambungan kepada cerapan khalayak membolehkan anda melihat laporan dalam cerapan penglibatan berdasarkan profil pelanggan disatukan. 

Untuk maklumat lanjut, lihat [Cipta pautan antara cerapan khalayak dan cerapan penglibatan](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Urus data peribadi

Untuk melindungi data peribadi pelanggan anda, anda boleh memadamkan atau mengeksport data boleh dikenal pasti pengguna akhir.

Untuk mendapatkan maklumat lanjut, lihat [Padam dan eksport data peristiwa yang mengandungi maklumat peribadi](../dsr-rights-requests.md#deleting-and-exporting-event-data-containing-end-user-identifiable-information).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
