---
title: Kenal pasti peristiwa web daripada pelawat yang disahkan sebelumnya dengan tidak diketahui untuk diketahui
description: Ciri tidak diketahui untuk diketahui membolehkan anda mengaitkan peristiwa di laman web dengan pelawat yang disahkan sebelumnya.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036794"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Kenal pasti peristiwa web daripada pelawat yang disahkan sebelumnya

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ciri **tidak diketahui untuk diketahui** dalam keupayaan cerapan penglibatan membolehkan perkaitan peristiwa di laman web dengan pelawat yang disahkan sebelumnya. Jika ciri itu dinyahdayakan, pelawat yang disahkan semasa lawatan lebih awal dan kemudian pergi tidak dikenal pasti jika mereka tidak mengesahkan semula apabila kembali. 

Sebagai contoh, seseorang melawat laman web minggu lepas, mendaftar masuk ke akaun pengguna mereka di laman web dan menyemak lalu katalog produk. Orang itu kembali pada minggu berikutnya untuk menyemak lalu lebih banyak produk tanpa mendaftar masuk ke akaun mereka. Pemilik tapak yang menggunakan ciri **tidak diketahui untuk diketahui** akan tahu bahawa orang yang sama telah kembali dan perkara yang mereka telah lakukan di laman web. Ini membolehkan pelaporan dan analisis aktiviti laman web yang lebih tepat.

## <a name="enable-unknown-to-known"></a>Dayakan tidak diketahui untuk diketahui

Anda mestilah seorang [pentadbir ruang kerja](user-roles.md) untuk mendayakan ciri ini. 

1. Dalam cerapan penglibatan, pergi ke **Pentadbir** > **Ruang Kerja**. 
2. Pilih tab **Tetapan**.
3. Dalam bahagian **Tidak diketahui untuk diketahui**, tetapkan togol kepada **Didayakan**.

![Dayakan tidak diketahui untuk diketahui](media/U2Ktoggle.png "Dayakan tidak diketahui untuk diketahui")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Menambah kod JavaScript pada cebisan penjejakan laman web anda

Sebuah laman boleh menangkap **authId pengguna** dengan sampel JavaScript berikut menggunakan [SDK web cerapan penglibatan](advanced-SDK-implementation.md). Untuk membolehkan ciri **tidak diketahui untuk diketahui** berfungsi, anda perlu menangkap authId *dan* mendayakan userMapping:Benar dalam cebisan JavaScript seperti dalam sampel di bawah.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
