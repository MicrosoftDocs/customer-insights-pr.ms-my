---
title: Urus kuki dan keizinan pengguna untuk menyimpan data pengguna
description: Fahami cara kuki dan keizinan pengguna digunakan untuk mengenal pasti pelawat tapak web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036749"
---
# <a name="manage-cookies-and-user-consent"></a>Urus kuki dan persetujuan pengguna

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Keupayaan cerapan penglibatan Dynamics 365 Customer Insights menggunakan kuki dan storan setempat (`localStorage`) untuk mengenal pasti pelawat tapak web.

Kuki adalah fail kecil yang menyimpan bit maklumat tentang interaksi pengguna dengan tapak web. Kuki disimpan dalam pelayar web. Apabila pengguna melawat tapak web tempat pengguna menyimpan kuki, pelayar menghantar maklumat itu kepada pelayan mengembalikan maklumat yang unik untuk pengguna. Ini adalah teknologi yang membenarkan, contohnya, kart beli belah dalam talian menyimpan item yang dipilih di dalamnya walaupun pengguna menavigasi jauh daripada laman web.

## <a name="user-consent"></a>Keizinan pengguna

[Peraturan Perlindungan Data Umum (GDPR)](/dynamics365/get-started/gdpr/) ialah peraturan Kesatuan Eropah (EU) yang memberi mandat cara organisasi seharusnya menangani privasi dan keselamatan pengguna mereka. Kuki sering menyimpan atau mengumpul "data peribadi" seperti pengecam dalam talian yang dilindungi oleh GDPR. Jika perniagaan anda menggunakan dan/atau menjual ke subjek data EU, GDPR memberi kesan kepada anda. [Ketahui lebih lanjut tentang cara Microsoft boleh membantu anda mematuhi GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Untuk membenarkan cerapan penglibatan SDK menyimpan kuki atau maklumat sensitif yang lain, anda mesti menentukan sama ada pengguna anda telah mengizinkan. Ini berlaku pada pengawalan SDK.

Jika anda menunjukkan bahawa tiada keizinan pengguna, SDK tidak akan menyimpan sebarang data dan tidak akan menghantar peristiwa yang boleh digunakan untuk menjejak tingkah laku pengguna. Sebarang data yang disimpan sebelum ini akan dipadam daripada pelayar.

Jika tiada nilai keizinan pengguna ditentukan, SDK akan mengandaikan bahawa pengguna telah mengizinkan. Ini bermaksud jika anda (sebagai pelanggan kami) tidak menentukan nilai untuk keizinan pengguna dalam SDK, data akan dikumpulkan. Walau bagaimanapun, jika anda menentukan bahawa nilai keizinan pengguna perlu menjadi "benar," data tidak akan dikumpulkan sekiranya pengguna menolak atau gagal memberikan persetujuan yang eksplisit.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Storan data pelawat dalam keupayaan cerapan penglibatan

### <a name="cookies"></a>Kuki

- _msei
    - Menyimpan ID pengguna tanpa nama. Kuki ini ditetapkan dalam domain pelanggan dan tamat tempoh dalam 365 hari.

### <a name="local-storage"></a>Storan setempat

Keupayaan cerapan penglibatan juga menggunakan storan setempat (`localStorage`) untuk menjejak data yang bukan sensitif. Data ini disimpan sepenuhnya dalam pelayar itu sendiri tanpa sebarang trafik yang dihantar ke atau daripada pelayan anda.

- *EISession.Id* 
    - Menyimpan maklumat tentang sesi pengguna yang berterusan seperti ID sesi apabila ia dimulakan dan apabila ia luput.
- *EISession.Previous*
    - Menyimpan URL bagi halaman yang dilawati sebelum ini dalam sesi semasa.
    
Kekunci dalam storan setempat tidak tamat tempoh secara automatik. Mereka akan menetapkan semula semasa sesi seterusnya oleh SDK.

## <a name="deleting-cookies"></a>Memadam kuki

Pelanggan anda boleh memadam kuki secara manual dan kekunci storan setempat pada bila-bila masa melalui tetapan pelayar mereka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]