---
title: Gunakan persetujuan pelanggan
description: Hormati keutamaan persetujuan pelanggan anda dalam Wawasan Pelanggan dengan mengimport data persetujuan.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188059"
---
# <a name="use-customer-consent"></a>Gunakan persetujuan pelanggan

Peraturan perlindungan data dan privasi memberikan individu hak untuk mentadbir cara organisasi menggunakan data peribadi mereka. Contoh peraturan tersebut ialah Peraturan Perlindungan Data Umum di Kesatuan Eropah atau Akta Privasi Pengguna California di Amerika Syarikat. Peraturan ini membolehkan orang ramai memilih untuk tidak mengumpulkan data peribadi mereka, diproses oleh atau dikongsi dengan pihak ketiga.  

Pelanggan boleh memilih untuk menarik balik atau menahan persetujuan mereka untuk bentuk hubungan tertentu. Mereka juga mungkin meminta anda menarik mereka daripada pengumpulan, penyimpanan, penggunaan atau penjualan data peribadi mereka. Adalah penting organisasi anda menghormati semua pilihan persetujuan dan privasi pelanggan.  

Dynamics 365 Customer Insights membantu anda menghormati permintaan pelanggan anda dengan mengimport dan menyimpan pilihan mereka sebagai sebahagian daripada profil pelanggan yang bersatu.

Jika data persetujuan disimpan secara berasingan daripada profil pelanggan anda, [tambahkan data persetujuan anda sebagai sumber data baharu](#import-and-unify-consent-data). Sumber data yang mengandungi data persetujuan ditambahkan pada proses penyatuan data. Penyatuan data persetujuan dan profil pelanggan yang berjaya kemudian membawa kepada profil pelanggan bersatu yang mengandungi maklumat persetujuan. Untuk profil pelanggan yang sudah mengandungi maklumat persetujuan, pergi terus ke [bahagian gunakan data](#use-consent-data) persetujuan.

## <a name="prerequisites"></a>Prasyarat

Maklumat berikut mesti tersedia dalam data sumber anda untuk menyatukan data persetujuan dengan profil pelanggan lain:

- Kekunci alternatif untuk memetakan maklumat persetujuan kepada profil pengguna dalam Wawasan Pelanggan. Sebagai contoh, alamat e-mel atau nombor telefon.
- Nilai persetujuan untuk menentukan status persetujuan pelanggan.

Pertimbangkan untuk menambah maklumat pilihan *berikut*:

- Kunci utama untuk mengemas kini status persetujuan jika pelanggan meminta perubahan.
- Jenis persetujuan, jika terdapat lebih daripada satu cara untuk memproses maklumat pelanggan.
- Tarikh persetujuan atau sebarang jenis data lain yang berkaitan dengan senario persetujuan anda.

Jadual contoh pangkalan data persetujuan mudah dengan berbilang opsyen persetujuan:

|ID Persetujuan (kekunci utama)   |Emel (kekunci alternatif)  |Pilihan persetujuan  |Nilai persetujuan  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Newsletter       |  Salah       |
|2    |  holly@contoso.com       |  Kemas kini produk       |  Benar       |
|3    |  frank@contoso.com       |  Newsletter       | Benar        |
|4    |  frank@contoso.com       |  Kemas kini produk       |  Salah       |

## <a name="import-and-unify-consent-data"></a>Mengimport dan menyatukan data persetujuan

Import data persetujuan dengan cara yang sama seperti anda menelan sumber data lain ke Wawasan Pelanggan. Untuk maklumat lanjut tentang sumber data yang disokong dan cara mengimportnya, lihat [Gambaran keseluruhan sumber data](data-sources.md).

Untuk maklumat lanjut tentang menyatukan sumber data anda, lihat [Gambaran keseluruhan penyatuan data](data-unification.md).

## <a name="use-consent-data"></a>Gunakan data persetujuan

Setelah data persetujuan anda adalah sebahagian daripada profil pelanggan bersatu anda, anda boleh menggunakannya dalam Wawasan Pelanggan. Sebagai contoh, buat segmen dengan peraturan untuk memastikan bahawa anda menghormati pilihan privasi dan perlindungan data pelanggan anda. Peraturan yang menyokong keutamaan persetujuan digunakan untuk mengecualikan pengguna daripada segmen berdasarkan atribut profil. Tambah peraturan pada segmen yang mengecualikan profil pelanggan yang tidak memberikan persetujuan untuk dihubungi.

Merujuk kepada jadual sampel di atas, segmen boleh mengandungi peraturan ini:`Consent option=Newsletter & Consent value=True`. Konfigurasi ini menghasilkan segmen yang menghormati keutamaan kenalan untuk menghantar surat berita.

Untuk maklumat lanjut tentang membina segmen, lihat [Mencipta segmen](segment-builder.md).

Setelah segmen dibuat, anda boleh menggunakan salah satu daripada banyak [pilihan](export-destinations.md) eksport untuk menggunakan segmen dalam aplikasi lain.

## <a name="ensure-updated-consent-status"></a>Pastikan status persetujuan yang dikemas kini

Penting untuk memastikan status persetujuan untuk pelanggan anda dikemas kini. Segar semula berjadual dalam Wawasan Pelanggan sentiasa mengimport keadaan terkini sumber data anda. Maklumat ini kemudiannya diproses melalui penyatuan data dan menghasilkan profil pelanggan yang dikemas kini. Profil yang dikemas kini ini kemudiannya digunakan untuk menyegar semula segmen untuk memastikan anda bekerja dengan maklumat yang paling terkini.

Dengan kata lain, pastikan data sumber yang diimport ke Wawasan Pelanggan sentiasa mempunyai maklumat terkini.

Untuk maklumat lanjut, lihat [Menyegar semula segmen secara manual](segments.md#refresh-segments) atau [mengkonfigurasikan segar semula](system.md#schedule-tab) berjadual.

[!INCLUDE [footer-include](includes/footer-banner.md)]
