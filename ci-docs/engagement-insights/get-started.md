---
title: Bermula dengan keupayaan cerapan penglibatan
description: Gambaran keseluruhan sumber bantuan untuk bermula dengan cepat.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 3505c15c4319c8cc8823bcd89d3b8adc944a87dd
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623688"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Bermula dengan keupayaan cerapan penglibatan Dynamics 365 Customer Insights (pratonton awam)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Keupayaan cerapan penglibatan membolehkan anda mengumpul dan mengukur tingkah laku pelanggan pada tapak web anda. Ia mengintegrasikan dengan keupayaan cerapan khalayak supaya anda dapat melihat analitis tingkah laku masa nyata beraneka bersama laporan profil pelanggan. Pautan dalam artikel ini membantu anda mengkonfigurasikan dan menyediakan persekitaran anda dengan cepat.

## <a name="step-1-review-prerequisites"></a>Langkah 1: Semak semula prasyarat

Pertama, anda mesti mempunyai akaun pengguna Microsoft Azure Active Directory (AAD) yang aktif. Kemudian, baca artikel berikut sebelum menyediakan ruang kerja cerapan penglibatan.

- Semak dan setuju dengan [Syarat perkhidmatan](terms-of-service.md) dengan Microsoft.  
- Baca artikel [Urus kuki dan persetujuan pengguna](user-consent-storage.md). Selepas itu, nilaikan sama ada anda perlu mengemas kini pemberitahuan persetujuan pengguna anda. Jika anda sebelum ini tidak mempunyai kuki "tidak penting", anda berkemungkinan perlu mengemas kini dasar tapak anda.
- Semak [glosari](glossary.md) untuk pengenalan ringkas kepada istilah dan konsep utama.

## <a name="step-2-explore-engagement-insights"></a>Langkah 2: Terokai cerapan penglibatan

Kali pertama anda melawati cerapan penglibatan, anda boleh mengkonfigurasikan tetapan, menyemak dasar dan menerokai keupayaan.

1. Log masuk [portal keupayaan cerapan penglibatan](https://home.ci.ai.dynamics.com/app/engagement-insights) menggunakan akaun pengguna AAD Microsoft (sekolah atau kerja) anda.

1. Pilih rantau anda dan tandakan kotak jika anda mahu memilih untuk menerima kemas kini e-mel dan tawaran.

1. Semak cerapan penglibatan (pratonton) **Syarat penggunaan** dan **Pernyataan privasi**, kemudian pilih **Terokai demo** untuk menerima tetapan ini.

1. Terokai produk menggunakan set data sampel.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Langkah 3: Sediakan ruang kerja dan cipta laporan

Ruang kerja ialah tempat anda boleh melihat aktiviti pengguna dalam masa nyata, serta menyimpan dan mengurus laporan. Tambahkan kod pada tapak web anda untuk mula mengumpul *peristiwa*, data aktiviti yang datang daripada pengguna.

1. [Cipta ruang kerja](create-workspace.md) dan tambah ahli.

1. Tambah kod ke [tapak web](instrument-website.md) anda atau [aplikasi mudah alih](developer-resources.md#capture-events-from-mobile-apps) untuk melihat aktiviti pengguna tiba ke dalam ruang kerja anda.

1. Lihat [laporan masa nyata](view-reports.md) yang menunjukkan pengguna aktif mengikut pelayar, peranti, sistem pengendalian, lokasi dan bahasa. Anda juga boleh mencipta [laporan tersuai](custom-reports.md) untuk mencipta visualisasi anda sendiri.

1. Cipta [dimensi](dimensions.md) untuk mengisih pelawat oleh pengguna baharu dan kembali, [metrik](metrics.md) untuk membantu lebih memahami tingkah laku pengguna lebih baik dan [segmen](segments.md) untuk mengenal pasti subset pelawat berdasarkan pada ciri atau interaksi tapak web.
    
## <a name="step-4-export-data-to-other-channels"></a>Langkah 4: Eksport data ke saluran lain

Anda boleh mencipta *peristiwa diperhalus* (pandangan maya) data analitis web anda. Kemudian tapis dan eksport data ke Azure Data Lake Storage. Anda boleh injes data yang dieksport sebagai sumber data.

1. [Cipta peristiwa diperhalus](refined-events.md) untuk eksport.

1. [Eksport data](export-events.md) ke Azure Data Lake Storage.

1. [Cipta pautan antara cerapan khalayak dan cerapan penglibatan](integrate-audience-insights-engagement-insights.md) untuk berkongsi data antara dua keupayaan.

1. [Mengenali peristiwa web daripada pengguna yang disahkan sebelum ini](unknown-to-known.md) dengan ciri **tidak diketahui kepada diketahui**.

1. Ketahui cara [memadamkan dan mengeksport data peristiwa yang mengandungi maklumat peribadi](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Langkah 5: Cipta dan urus laporan corong

Laporan corong mengumpul maklumat tentang langkah-langkah yang berlaku semasa perjalanan pelanggan melalui tapak web atau aplikasi mudah alih anda. Selain daripada mencipta laporan profil luar kotak dan laporan tersuai, anda boleh mencipta laporan corong untuk mengenal pasti laluan pelanggan anda ambil sebelum mereka membuat pembelian. 

1. [Cipta laporan corong](funnel-reports.md) untuk memberitahu keputusan dan mengenal pasti kawasan untuk pengoptimuman dan peningkatan proses.

1. Cipta laporan corong rentas saluran, sebaik sahaja anda telah instrumenkan aplikasi mudah alih anda dengan penglibatan cerapan [SDK Android](get-started-android.md) atau [SDK iOS](get-started-ios.md).

1. Gunakan [corong cerapan](funnel-reports.md#funnel-insights) untuk mendapatkan cerapan lebih mendalam ke dalam tingkah laku pelanggan tentang langkah dalam laporan corong.
 
## <a name="step-6-stay-connected"></a>Langkah 6: Kekal berhubung

Kami menghargai penyertaan aktif anda, dan mempertimbangkan semua maklum balas yang berkaitan dalam membangunkan keluaran pada masa akan datang. Kongsi maklum balas anda dan laporkan isu melalui salah satu saluran ini:
- [Komuniti](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Berikan maklum balas](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Minta sokongan](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
