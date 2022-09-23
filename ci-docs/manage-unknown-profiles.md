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
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556407"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Urus profil yang tidak diketahui dengan Wawasan Pelanggan

Pengguna Internet sering tidak dikenali dan tanpa nama dalam talian. Sekiranya mereka tidak log masuk kerana mereka menggunakan peranti atau saluran yang berbeza, itu bahkan berlaku untuk pelanggan yang paling setia. Dengan kuki pihak ketiga mungkin akan hilang tidak lama lagi, menguruskan pilihan pengguna berdasarkan data pihak pertama adalah penting untuk mencapai pengalaman peribadi yang berbeza. Bagi kebanyakan jenama, pengguna yang dikenali atau disahkan adalah minoriti walaupun jangkaan pelanggan yang semakin meningkat mengenai pemperibadian. Sangat bagus bagi perniagaan untuk mengetahui siapa pelanggan mereka, berdasarkan data yang boleh dipercayai, terperinci, dan bersatu.

Pemperibadian yang tidak dapat dilupakan bergantung pada kekayaan dan kesempurnaan data pelanggan anda dan Wawasan Pelanggan membantu anda mencapai matlamat ini. Anda tidak perlu mengehadkan atau menghentikan penggunaan data yang dikumpul pada permulaan perjalanan pelanggan. Wawasan Pelanggan membolehkan anda membawa data anda sendiri untuk membuat profil pelanggan untuk pengguna yang tidak dikenali. Anda kemudian boleh menggunakan profil tersebut untuk tindakan selanjutnya, walaupun terdapat maklumat hubungan yang hilang. Import data pihak pertama dari sumber seperti web, mudah alih, atau sistem CRM ke dalam Wawasan Pelanggan untuk memperkayakan profil pelanggan secara berterusan. Semasa anda menyatukan lebih banyak interaksi, [ubah pelanggan yang *tidak diketahui* menjadi pelanggan yang *dikenali*](unknown-to-known.md).

## <a name="sample-scenario"></a>Senario Sampel

E-dagang adalah saluran yang paling pesat berkembang sejak sedekad yang lalu. Anggap pengguna menggunakan peranti mudah alih mereka untuk melayari laman web e-dagang anda. Laman web memberikan "mobile_guest123" pelawat sebagai pengecam unik dan anda mula mengumpul aktiviti tingkah laku berdasarkan aktiviti dalam talian mereka. Sebagai contoh, halaman mana yang mereka lawati, berapa banyak masa yang mereka habiskan pada halaman tersebut, atau pautan mana yang mereka klik. Anda tidak tahu nama atau alamat e-mel mereka, tetapi data ini dapat membantu memberikan pandangan bermakna kepada jenama tentang pengguna khusus ini. Sebaliknya, anda boleh meletakkan wawasan tersebut untuk berfungsi pada kali seterusnya pengguna melawat laman web ini. Pertanyaan Wawasan Pelanggan untuk "mobile_guest123" untuk mendapatkan semula senarai segmen pengguna, seperti "organik", "pelanggan pra-pesanan mudah alih", "pelanggan bernilai tinggi", dan lain-lain, atau mengambil profil untuk mencipta pengalaman web yang diperibadikan. Anda juga boleh mengeksport data ke mana-mana sistem pengaktifan untuk melakukan perkara yang sama.

## <a name="prerequisites"></a>Prasyarat

- Menelan data pihak pertama ke dalam Wawasan Pelanggan
- Setiap entiti mempunyai ID unik yang ditetapkan sebagai kunci primer
- Setiap entiti yang mempunyai kunci utama untuk pemperibadian disatukan
- Sistem pengurusan kandungan laman web anda mampu menggunakan API (untuk pemperibadian web berdasarkan komunikasi langsung dengan Wawasan Pelanggan)

Jadual berikut menunjukkan contoh ringkas bagaimana peristiwa web bernilai tinggi boleh ditangkap.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Pandangan produk|
|2|09-18-2022 10:05:00|abc123|CookieID1|Pandangan produk|
|3|09-18-2022 10:10:00|abc123|CookieID1|Tambah ke kart|
|4|09-21-2022 09:05:00|abc123|CookieID1|Pandangan produk|

## <a name="data-ingestion"></a>Pengingesan data

Untuk maklumat lanjut tentang opsyen yang tersedia untuk pengingesan data, lihat [Gambaran keseluruhan sumber data](data-sources.md).

## <a name="data-unification"></a>Penyatuan data

Untuk maklumat lanjut tentang menyatukan profil pelanggan, lihat [Gambaran keseluruhan penyatuan data](data-unification.md).

## <a name="get-insights"></a>Dapatkan wawasan

[Memperkayakan](enrichment-hub.md) data anda, membina [ukuran](measures.md) dan mencipta [segmen](segments.md) untuk pengaktifan selanjutnya.

Sebagai contoh, anda boleh membuat segmen pengguna tidak diketahui yang melayari halaman produk yang sama tetapi tidak pernah menyelesaikan pembayaran.

## <a name="activation"></a>Pengaktifan

Dengan data anda dalam Wawasan Pelanggan dan wawasan anda sedia untuk berfungsi, anda boleh menggunakan Wawasan Pelanggan untuk pemperibadian:

1. [Gunakan API](apis.md) OData untuk mendapatkan semula keahlian segmen atau profil pelanggan Untuk lebih banyak contoh, lihat [contoh pertanyaan OData untuk API Wawasan Pelanggan](odata-examples.md).

1. [Eksport](export-destinations.md) data anda ke sistem pengaktifan anda.

Contoh: Pengguna yang tidak dikenali melawat laman web beberapa kali dan melawat halaman produk untuk pelbagai model kasut kulit. Dengan data yang tersedia dalam Wawasan Pelanggan, anda boleh memasukkan pengguna yang tidak diketahui dalam segmen orang yang berminat dengan kasut kulit. Gunakan segmen ini untuk memaklumkan laman web anda membina pemperibadian untuk pelawat yang kembali. Pada lawatan seterusnya, laman web ini mengenali pengguna yang tidak dikenali dan boleh menawarkan kupon 10% pada kasut kulit.

[!INCLUDE [footer-include](includes/footer-banner.md)]
