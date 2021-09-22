---
title: Bermula dengan keupayaan cerapan penglibatan
description: Gambaran keseluruhan sumber bantuan untuk bermula dengan cepat.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405369"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Bermula dengan keupayaan cerapan penglibatan Dynamics 365 Customer Insights (pratonton awam)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Keupayaan cerapan penglibatan membolehkan anda mengumpul dan mengukur tingkah laku pelanggan pada tapak web anda. Ia mengintegrasikan dengan keupayaan cerapan khalayak supaya anda dapat melihat analitis tingkah laku masa nyata beraneka bersama laporan profil pelanggan. Pautan dalam artikel ini membantu anda mengkonfigurasikan dan menyediakan persekitaran anda dengan cepat.

## <a name="step-1-review-prerequisites"></a>Langkah 1: Semak semula prasyarat

Pertama, anda mesti mempunyai akaun pengguna Microsoft Azure Active Directory yang aktif. Kemudian, baca artikel berikut sebelum menyediakan ruang kerja cerapan penglibatan.

- Semak dan bersetuju dengan [Terma Perkhidmatan](terms-of-service.md) dengan Microsoft.  
- Baca artikel [Urus kuki dan persetujuan pengguna](user-consent-storage.md). Selepas menyemak artikel ini, nilai sama ada anda perlu mengemas kini pemberitahuan persetujuan pengguna anda. Jika anda sebelum ini tidak mempunyai kuki "tidak penting", anda berkemungkinan perlu mengemas kini dasar tapak anda.
- Semak [glosari](glossary.md) untuk pengenalan ringkas kepada istilah dan konsep utama.

## <a name="step-2-explore-engagement-insights"></a>Langkah 2: Terokai cerapan penglibatan

Kali pertama anda melawati cerapan penglibatan, anda boleh mengkonfigurasikan tetapan, menyemak dasar dan menerokai produk.

1. Log masuk ke [portal keupayaan cerapan penglibatan](https://pi.dynamics.com) menggunakan akaun pengguna Microsoft Azure Active Directory anda. (Ia boleh jadi akaun sekolah atau kerja anda.)

1. Pilih rantau anda dan gunakan kotak semak untuk menunjukkan sama ada anda mahu memilih untuk menerima kemas kini dan menawarkan melalui e-mel.

1. Semak semula **Terma Penggunaan cerapan penglibatan (pratonton)** dan **Pernyataan Privasi** dan kemudian pilih **Teroka demo** untuk menerima mereka.

1. Terokai produk menggunakan set data sampel.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Langkah 3: Sediakan ruang kerja dan tambahkan kod pada tapak web anda

Ruang kerja ialah tempat anda boleh melihat aktiviti pengguna dalam masa nyata, dan menyimpan dan mengurus laporan. Tambahkan kod pada tapak web anda untuk mula mengumpul *peristiwa*, data aktiviti yang datang daripada pengguna.

1. [Cipta ruang kerja](create-workspace.md) dan tambah ahli.

1. [Tambahkan kod pada tapak web](instrument-website.md) atau [aplikasi mudah alih](developer-resources.md#capture-events-from-mobile-apps) anda untuk melihat aktiviti pengguna yang tiba ke dalam ruang kerja anda.

1. Lihat [laporan masa nyata](view-reports.md) yang menunjukkan pengguna aktif mengikut pelayar, peranti, sistem pengoperasian, lokasi dan bahasa. Anda juga boleh mencipta [laporan tersuai](custom-reports.md) untuk mencipta visualisasi anda sendiri.
    
## <a name="step-4-export-data-to-other-channels"></a>Langkah 4: Eksport data ke saluran lain

Anda boleh mencipta *peristiwa diperhalus* (pandangan maya) data analitis web anda. Kemudian tapis dan eksport data ke Azure Data Lake Storage. Anda boleh injes data yang dieksport sebagai sumber data. Untuk maklumat lanjut, lihat [Cipta pautan antara cerapan khalayak dan cerapan penglibatan](integrate-audience-insights-engagement-insights.md).

1. [Cipta peristiwa diperhalus](refined-events.md) untuk eksport.

1. [Eksport data](export-events.md) ke Data Lake Storage.

1. Ketahui cara [memadamkan dan mengeksport data peristiwa yang mengandungi maklumat peribadi](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Langkah 5: Kekal berhubung

Kami menghargai penyertaan dan rancangan anda yang aktif untuk mempertimbangkan semua maklum balas yang berkaitan dalam membangunkan keluaran akan datang. Kongsi maklum balas anda dan laporkan isu melalui salah satu saluran ini:
- [Komuniti](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Berikan maklum balas](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Minta sokongan](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
