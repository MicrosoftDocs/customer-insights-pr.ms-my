---
title: Menguruskan kuki dan persetujuan pengguna untuk menyimpan data pengguna dalam Dynamics 365 Customer Insights
description: Fahami cara kuki dan keizinan pengguna digunakan untuk mengenal pasti pelawat tapak web.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228996"
---
# <a name="manage-cookies-and-user-consent"></a>Urus kuki dan persetujuan pengguna

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights keupayaan cerapan penglibatan menggunakan kuki dan kekunci (`localStorage`) untuk mengenal pasti pelawat tapak web.

Kuki adalah fail kecil yang menyimpan bit maklumat tentang interaksi pengguna dengan tapak web. Kuki disimpan dalam pelayar web. Apabila pengguna melawat tapak web tempat pengguna menyimpan kuki, pelayar menghantar maklumat itu kepada pelayan mengembalikan maklumat yang unik untuk pengguna. Ini adalah teknologi yang membenarkan, contohnya, kart beli belah dalam talian menyimpan item yang dipilih di dalamnya walaupun pengguna menavigasi jauh daripada laman web.

## <a name="user-consent"></a>Keizinan pengguna

[Peraturan Perlindungan Data Umum (GDPR)](/dynamics365/get-started/gdpr/) ialah peraturan Kesatuan Eropah (EU) yang memberi mandat cara organisasi seharusnya menangani privasi dan keselamatan pengguna mereka. Kuki sering menyimpan atau mengumpul "data peribadi" seperti pengecam dalam talian yang dilindungi oleh GDPR. Jika perniagaan anda menggunakan dan/atau menjual ke subjek data EU, GDPR memberi kesan kepada anda. [Ketahui lebih lanjut tentang cara Microsoft boleh membantu anda mematuhi GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Untuk membenarkan cerapan penglibatan SDK menyimpan kuki atau maklumat sensitif yang lain, anda mesti menentukan sama ada pengguna anda telah mengizinkan. Ini berlaku pada pengawalan SDK dengan menetapkan medan `userConsent` dalam konfigurasi.

Jika anda menunjukkan bahawa tiada keizinan pengguna, SDK tidak akan menyimpan sebarang data dan tidak akan menghantar peristiwa yang boleh digunakan untuk menjejak tingkah laku pengguna. Sebarang data yang disimpan sebelum ini akan dipadam daripada pelayar.

Jika tiada nilai keizinan pengguna ditentukan, SDK akan mengandaikan bahawa pengguna telah mengizinkan. Ini bermaksud jika anda (sebagai pelanggan kami) tidak menentukan nilai untuk keizinan pengguna dalam SDK, data akan dikumpulkan. Walau bagaimanapun, jika anda menentukan bahawa nilai keizinan pengguna perlu menjadi "benar," data tidak akan dikumpulkan sekiranya pengguna menolak atau gagal memberikan persetujuan yang eksplisit.

Berikut adalah cebisan kod untuk memulakan web SDK dengan persetujuan pengguna:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Storan data pelawat dalam keupayaan cerapan penglibatan

### <a name="cookies"></a>Kuki

- _msei
    - Menyimpan ID pengguna tanpa nama. Kuki ini ditetapkan dalam domain pelanggan dan tamat tempoh dalam 365 hari.

### <a name="local-storage"></a>Storan setempat

Keupayaan cerapan penglibatan juga memanfaatkan kekunci (`localStorage`) untuk menjejak data yang tidak sensitif. Data ini disimpan sepenuhnya dalam pelayar itu sendiri tanpa sebarang trafik yang dihantar ke atau daripada pelayan anda.

- *EISession.Id*
    - Menyimpan maklumat tentang sesi pengguna yang berterusan seperti ID sesi apabila ia dimulakan dan apabila ia luput.
- *EISession.Previous*
    - Menyimpan URL bagi halaman yang dilawati sebelum ini dalam sesi semasa.

Kekunci dalam storan tempatan tidak tamat tempoh secara automatik dan mereka akan dapat tetapkan semula semasa sesi SDK seterusnya.

## <a name="deleting-cookies"></a>Memadam kuki

Pelanggan anda boleh memadam kuki secara manual dan kekunci storan setempat pada bila-bila masa melalui tetapan pelayar mereka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
