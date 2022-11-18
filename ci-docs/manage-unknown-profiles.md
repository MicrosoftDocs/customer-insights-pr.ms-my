---
title: Urus profil yang tidak diketahui dengan Wawasan Pelanggan
description: Bekerja dengan profil pelanggan yang tidak diketahui yang dicipta dan diuruskan dalam Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776832"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Urus profil yang tidak diketahui dengan Wawasan Pelanggan

Pengguna internet sering tidak dikenali atau tanpa nama dalam talian. Malah pelanggan yang paling setia mungkin kelihatan "tidak diketahui" jika mereka tidak log masuk merentas peranti yang berbeza. Bagi kebanyakan jenama, pengguna yang dikenali atau disahkan adalah minoriti walaupun jangkaan pelanggan yang semakin meningkat mengenai pemperibadian. Dengan masa depan kuki pihak ketiga yang berkenaan, menguruskan pilihan pengguna berdasarkan data pihak pertama, adalah penting untuk mencapai pengalaman yang diperibadikan.

Pemperibadian yang tidak dapat dilupakan bergantung pada seberapa baik anda mengetahui pelanggan anda dan Wawasan Pelanggan membantu anda melakukannya dengan menjejaki semua pelanggan anda.  Anda tidak perlu mengehadkan atau menghentikan penggunaan data yang dikumpul pada permulaan perjalanan pelanggan. Wawasan Pelanggan membolehkan anda membawa data anda sendiri untuk membuat profil pelanggan untuk pengguna yang tidak dikenali. Anda kemudian boleh menggunakan profil itu untuk tindakan selanjutnya, walaupun kehilangan maklumat hubungan. Import data pihak pertama dari sumber seperti web, mudah alih, atau sistem CRM ke dalam Wawasan Pelanggan untuk memperkayakan profil pelanggan secara berterusan. Semasa anda menyatukan lebih banyak interaksi, [menjadikan pelanggan yang *tidak diketahui* menjadi pelanggan yang *dikenali*](unknown-to-known.md).

## <a name="sample-scenario"></a>Senario Sampel

Anggap pengguna menggunakan peranti mudah alih mereka untuk melayari laman web e-dagang anda. Laman web ini memberikan pelawat "mobile_guest123" sebagai pengecam unik dan anda mula mengumpul aktiviti tingkah laku berdasarkan aktiviti dalam talian mereka. Sebagai contoh, halaman mana yang mereka lawati, berapa banyak masa yang mereka habiskan pada halaman tersebut, atau pautan mana yang mereka klik. Anda tidak tahu nama atau alamat e-mel mereka, tetapi data ini dapat membantu memberikan cerapan yang bermakna kepada jenama tentang pengguna khusus ini. Sebaliknya, anda boleh meletakkan cerapan tersebut untuk berfungsi pada kali seterusnya pengguna melawat laman web ini. Wawasan Pelanggan Pertanyaan untuk "mobile_guest123" untuk mendapatkan semula senarai segmen pengguna, seperti "organik", "pelanggan pra-pesanan mudah alih", "pelanggan bernilai tinggi", dan lain-lain, atau mendapatkan profil untuk mencipta pengalaman web yang diperibadikan. Anda juga boleh mengeksport data ke mana-mana sistem pengaktifan untuk melakukan perkara yang sama.

## <a name="prerequisites"></a>Prasyarat

- Menelan data pihak pertama ke dalam Wawasan Pelanggan
- Setiap entiti mempunyai ID unik yang disetkan sebagai kunci primer
- Setiap entiti dengan kunci utama untuk pemperibadian disatukan
- Sistem pengurusan kandungan laman web anda boleh menggunakan API (untuk pemperibadian web berdasarkan komunikasi langsung dengan Wawasan Pelanggan)

Jadual berikut menunjukkan contoh ringkas bagaimana peristiwa web bernilai tinggi boleh ditangkap.

|EventID|EventTimeStamp|UserID|PrimaryKey|Nama Acara|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|ABC123|CookieID1|Pandangan produk|
|2|09-18-2022 10:05:00|ABC123|CookieID1|Pandangan produk|
|3|09-18-2022 10:10:00|ABC123|CookieID1|Tambah ke kart|
|4|09-21-2022 09:05:00|ABC123|CookieID1|Pandangan produk|

## <a name="data-ingestion"></a>Pengingesan data

Untuk maklumat lanjut tentang opsyen tersedia untuk pengingesan data, lihat [Gambaran keseluruhan sumber data](data-sources.md).

## <a name="data-unification"></a>Penyatuan data

Untuk maklumat lanjut tentang menyatukan profil pelanggan, lihat [Gambaran keseluruhan](data-unification.md) penyatuan data.

## <a name="get-insights"></a>Dapatkan wawasan

[Memperkayakan](enrichment-hub.md) data anda, [membina ukuran](measures.md) dan mencipta [segmen](segments.md) untuk pengaktifan selanjutnya.

Sebagai contoh, anda boleh membuat segmen pengguna tidak dikenali yang melayari halaman produk yang sama tetapi tidak pernah menyelesaikan pembayaran.

## <a name="activation"></a>Pengaktifan

Dengan data anda dalam Wawasan Pelanggan dan cerapan anda bersedia untuk berfungsi, anda boleh menggunakan Wawasan Pelanggan untuk pemperibadian:

1. [Gunakan API](apis.md) OData untuk mendapatkan semula keahlian segmen atau profil pelanggan Untuk lebih banyak contoh, lihat [Contoh pertanyaan OData untuk API](odata-examples.md) Wawasan Pelanggan.

1. [Eksport](export-destinations.md) data anda ke sistem pengaktifan anda.

Contoh: Pengguna yang tidak dikenali melawat tapak web beberapa kali dan melawat halaman produk untuk pelbagai model kasut kulit. Dengan data yang terdapat dalam Wawasan Pelanggan, anda boleh memasukkan pengguna yang tidak dikenali dalam segmen orang yang berminat dengan kasut kulit. Gunakan segmen ini untuk memaklumkan laman web anda membina pemperibadian untuk pelawat yang kembali. Pada lawatan seterusnya, laman web ini mengenali pengguna yang tidak dikenali dan boleh menawarkan mereka kupon 10% pada kasut kulit.

[!INCLUDE [footer-include](includes/footer-banner.md)]
