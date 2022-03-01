---
title: Senario SDK web lanjutan
description: Senario lanjutan untuk mempertimbangkan masa untuk mengalatkan tapak web anda menggunakan SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036339"
---
# <a name="advanced-web-sdk-instrumentation"></a>Pengalatan SDK web lanjutan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Artikel ini membimbing anda melalui senario lanjutan untuk mempertimbangkan masa untuk [mengalatkan tapak web anda](instrument-website.md) dengan SDK keupayaan cerapan penglibatan Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Menetapkan butiran pengguna untuk peristiwa anda

SDK membolehkan anda mentakrifkan maklumat pengguna yang boleh dihantar dengan setiap peristiwa. Anda boleh menentukan butiran pengguna dalam sifat yang dipanggil `user` (data yang dijangka untuk sifat ini ialah objek `IUser`), serupa dengan `src`, `name` dan `cfg` dalam konfigurasi cebisan kod.

Objek `IUser` mengandungi sifat rentetan yang berikut:

- **localId**: ID tempatan pengguna.
- **authId**: ID pengguna yang disahkan.
- **authType**: Jenis pengesahan yang digunakan untuk mendapatkan ID pengguna yang disahkan.
- **name**: Nama pengguna.
- **email**: Alamat e-mel pengguna.
    
Contoh berikut menunjukkan cebisan kod menghantar maklumat pengguna. Sekiranya anda melihat Fungsi yang ditandakan dengan *, gantikannya dengan pelaksanaan memanggil nilai tersebut:  

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
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Anda juga boleh menentukan maklumat pengguna dengan memanggil API `setUser(user: IUser)` pada SDK. Telemetri yang dihantar selepas memanggil `setUser API` akan mengandungi maklumat pengguna.

## <a name="adding-custom-properties-for-each-event"></a>Menambah sifat tersuai untuk setiap acara

SDK membolehkan anda menentukan sifat tersuai yang boleh dihantar dengan setiap peristiwa. Anda boleh menentukan sifat tersuai sebagai objek yang mengandungi pasangan nilai utama (nilai boleh jadi jenis `string | number | boolean`). Objek boleh ditambah dalam sifat yang dipanggil `props`, serupa dengan `src`, `name` dan `cfg` dalam konfigurasi cebisan kod. 

Contoh berikut menunjukkan cebisan kod menghantar sifat tersuai:

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
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Anda juga boleh menentukan sifat tersuai secara individu dengan memanggil API `setProperty(name: string, value: string | number | boolean)` pada SDK.

## <a name="sending-custom-events"></a>Menghantar peristiwa tersuai

Anda boleh menggunakan SDK untuk menghantar peristiwa tersuai. Anda mesti menentukan nama untuk peristiwa dan sifat yang akan dihantar dengan peristiwa tersebut.

Contoh berikut menunjukkan cebisan kod menjejaki peristiwa tersuai: "NAME" ialah nilai dalam kunci `name` dalam konfigurasi cebisan. Ia juga nama pemboleh ubah dalam objek tetingkap iaitu tempat SDK dimuatkan.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]