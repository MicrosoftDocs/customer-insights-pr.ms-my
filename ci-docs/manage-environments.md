---
title: Cara - Menguruskan persekitaran
description: Ketahui cara menguruskan persekitaran Wawasan Pelanggan sedia ada sebagai pentadbir."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833503"
---
# <a name="how-to-manage-environments"></a>Cara: Menguruskan persekitaran

Pentadbir [mencipta](create-environment.md) dan mengurus persekitaran. Mereka boleh menukar beberapa tetapan dalam persekitaran sedia ada. Perniagaan, jenis, rantau, pilihan storan dan Dataverse tetapan ditetapkan selepas mencipta persekitaran. Jika anda ingin mengubah seting ini, tetapkan semula persekitaran atau cipta persekitaran baru.

## <a name="edit-an-existing-environment"></a>Edit persekitaran sedia ada

Anda boleh mengedit beberapa butiran persekitaran sedia ada.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih ikon **Edit**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon untuk mengedit seting persekitaran.":::

1. Dalam kotak **Edit persekitaran**, anda boleh mengemas kini tetapan persekitaran.

Untuk bermula dengan persekitaran yang segar, lihat [Mencipta persekitaran baharu](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Tukar pemilik persekitaran

Beberapa pengguna boleh mempunyai keizinan pentadbir tetapi hanya satu pengguna adalah pemilik persekitaran. Secara lalai, pentadbir yang mencipta persekitaran pada mulanya. Sebagai pentadbir persekitaran, anda boleh memperuntukkan pemilikan kepada pengguna lain dengan keizinan pentadbir.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih ikon **Edit**.

1. **Dalam kotak Edit persekitaran**, pergi ke **langkah Maklumat** asas.

1. **Dalam medan Tukar pemilik persekitaran**, pilih pemilik baru persekitaran.  

1. Pilih **Semak semula dan selesaikan**, kemudian **Kemas kini** untuk menggunakan perubahan.

## <a name="claim-ownership-of-an-environment"></a>Menuntut pemilikan persekitaran

Jika akaun pengguna pemilik dipadamkan atau digantung, persekitaran tidak akan mempunyai pemilik. Setiap pengguna pentadbir boleh menuntut pemilikan dan menjadi pemilik baru. Mereka boleh terus memiliki persekitaran atau [menukar pemilikan kepada pentadbir](#change-the-owner-of-an-environment) lain.

Untuk menuntut pemilikan, pilih **butang Ambil pemilikan** yang ditunjukkan di bahagian atas setiap halaman dalam Wawasan Pelanggan apabila pemilik asal meninggalkan organisasi.

## <a name="reset-an-existing-environment-preview"></a>Tetapkan semula persekitaran sedia ada (Pratonton)

Sebagai pemilik persekitaran, anda boleh menetapkan semula persekitaran kepada keadaan kosong jika anda ingin memadamkan semua konfigurasi dan mengalih keluar data yang ditelan.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih persekitaran yang anda mahu tetapkan semula dan pilih elipsis menegak (&vellip;).

1. Pilih pilihan **Tetap semula**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kawal untuk menetapkan semula persekitaran.":::

1. Pilih sama ada anda mahu menetapkan semula keseluruhan persekitaran, segala-galanya kecuali sumber data, atau apa-apa yang dikonfigurasikan di atas profil pelanggan bersatu.

1. Untuk mengesahkan, masukkan nama persekitaran dan pilih **Tetapkan Semula**.

## <a name="delete-an-existing-environment"></a>Padam persekitaran sedia ada

Sebagai pemilik persekitaran, anda boleh memadamkan persekitaran yang anda tadbir.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih persekitaran yang anda mahu tetapkan semula dan pilih elipsis menegak (&vellip;). 

1. Pilih pilihan **Padam**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kawal untuk memadam persekitaran.":::

1. Untuk mengesahkan pemadaman, masukkan nama persekitaran dan pilih **Padam**.

> [!IMPORTANT]
> Memadam persekitaran tidak mengalih keluar sambungan ke Dataverse persekitaran. Jika anda merancang untuk menyambungkan persekitaran yang sama Dataverse ke persekitaran Wawasan Pelanggan baharu pada masa hadapan, anda mesti mengalih keluar sambungan tersebut Ketahui cara mengalih [keluar sambungan sedia ada ke Dataverse persekitaran](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
