---
title: Urus persekitaran
description: Ketahui cara mengurus persekitaran Wawasan Pelanggan sedia ada sebagai pentadbir."
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 8b4a88bdb75c6e638a76c39d18647681ad4556d7
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304296"
---
# <a name="manage-environments"></a>Urus persekitaran

Pentadbir [mencipta](create-environment.md) dan menguruskan persekitaran. Mereka boleh mengubah beberapa tetapan dalam persekitaran sedia ada. Perniagaan, jenis, rantau, opsyen storan dan Dataverse seting ditetapkan selepas mencipta persekitaran. Jika anda ingin mengubah seting ini, [tetapkan semula persekitaran](#reset-an-existing-environment-preview) atau [cipta persekitaran baharu](create-environment.md).

## <a name="edit-an-existing-environment"></a>Edit persekitaran sedia ada

Edit butiran persekitaran sedia ada seperti nama atau seting persekitaran lalai.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih ikon **Edit**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ikon untuk mengedit seting persekitaran.":::

1. **Dalam anak tetingkap Edit persekitaran**, kemas kini seting persekitaran.

1. Pilih **Semak Semula dan selesai**, kemudian **Kemas Kini** untuk menggunakan perubahan.

## <a name="change-the-owner-of-an-environment"></a>Mengubah pemilik persekitaran

Beberapa pengguna boleh mempunyai keizinan pentadbir tetapi hanya seorang pengguna ialah pemilik persekitaran. Secara lalai, pentadbirlah yang mencipta persekitaran pada mulanya. Sebagai pentadbir persekitaran, anda boleh memperuntukkan pemilikan kepada pengguna lain dengan keizinan pentadbir.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih ikon **Edit**.

1. **Dalam anak tetingkap Edit persekitaran**, pergi ke **langkah Maklumat** asas.

1. **Dalam medan Ubah pemilik persekitaran**, pilih pemilik baru persekitaran.  

1. Pilih **Semak Semula dan selesai**, kemudian **Kemas Kini** untuk menggunakan perubahan.

## <a name="claim-ownership-of-an-environment"></a>Tuntut pemilikan persekitaran

Jika akaun pengguna pemilik dipadamkan atau digantung, persekitaran tidak akan mempunyai pemilik. Mana-mana pengguna pentadbir boleh menuntut pemilikan dan menjadi pemilik baharu. Pentadbir pemilik boleh terus memiliki persekitaran atau [menukar pemilikan kepada pentadbir](#change-the-owner-of-an-environment) lain.

Untuk menuntut pemilikan, pilih **butang Ambil pemilikan** yang ditunjukkan di bahagian atas setiap halaman dalam Wawasan Pelanggan apabila pemilik asal meninggalkan organisasi.

## <a name="reset-an-existing-environment-preview"></a>Mengeset semula persekitaran sedia ada (pratonton)

Sebagai pemilik persekitaran, tetapkan semula persekitaran kepada keadaan kosong jika anda ingin memadamkan semua konfigurasi dan mengalih keluar data yang ditelan.

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih persekitaran yang anda mahu tetapkan semula dan pilih elipsis menegak (&vellip;).

1. Pilih **Set Semula (pratonton)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Kawalan untuk menetapkan semula persekitaran.":::

1. Pilih sama ada anda mahu menetapkan semula keseluruhan persekitaran, segala-galanya kecuali sumber data, atau apa-apa sahaja yang dikonfigurasikan di atas profil pelanggan bersatu.

1. Untuk mengesahkan, masukkan nama persekitaran dan pilih **Set Semula**.

## <a name="delete-an-existing-environment"></a>Padam persekitaran sedia ada

Sebagai pemilik persekitaran, anda boleh memadamkannya.

> [!IMPORTANT]
> Memadamkan persekitaran tidak mengalih keluar sambungan ke Dataverse persekitaran. Jika anda bercadang untuk menyambungkan persekitaran yang sama Dataverse ke persekitaran Wawasan Pelanggan yang baru pada masa akan datang, anda mesti [mengalih keluar sambungan tersebut Dataverse ke alam sekitar](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Pilih pemilih **Persekitaran** dalam pengepala aplikasi.

1. Pilih persekitaran yang anda mahu padamkan dan pilih elipsis menegak (&vellip;). 

1. Pilih **Padam**.

   :::image type="content" source="media/delete-environment.png" alt-text="Kawalan untuk memadam persekitaran.":::

1. Untuk mengesahkan pemadaman, masukkan nama persekitaran dan pilih **Padam**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
