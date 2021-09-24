---
title: Mari bermula dengan SDK iOS
description: Ketahui cara memeribadikan dan menjalankan SDK iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494241"
---
# <a name="get-started-with-the-ios-sdk"></a>Mari bermula dengan SDK iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Tutorial ini membimbing anda melalui proses memodelkan aplikasi iOS anda dengan SDK cerapan penglibatan Dynamics 365 Customer Insights. Anda akan mula melihat peristiwa dalam portal anda dalam masa lima minit atau lebih awal.

## <a name="configuration-options"></a>Pilihan konfigurasi

Pilihan konfigurasi berikut boleh dihantar ke SDK melalui fail `EIConfig.plist` yang disediakan:

- **ingestionKey**: Kunci pengingesan digunakan untuk menghantar peristiwa pada projek anda.
- **autocollectAction**: Nilai Boolean untuk mendayakan atau menyahdayakan autopengalatan peristiwa tindakan.
- **autocollectAction**: Nilai Boolean untuk mendayakan atau menyahdayakan autopengalatan peristiwa tindakan.
- **endpointUrl**: URL titik tamat yang peristiwa akan diarahkan.

## <a name="prerequisites"></a>Prasyarat

- Xcode versi 9+
- iOS versi 8.2+
- Kunci pengingesan (lihat arahan di bawah untuk memperoleh)

## <a name="integrate-the-sdk-into-your-application"></a>Mengintegrasikan SDK ke dalam aplikasi anda

Mulakan proses dengan memilih ruang kerja untuk bekerja, memilih platform iOS mudah alih, dan memuat turun SDK .

- Gunakan penukar ruang kerja dalam anak tetingkap navigasi kiri untuk memilih ruang kerja anda.

- Jika anda tidak mempunyai ruang kerja yang sedia ada, pilih **Ruang Kerja Baharu** dan ikut langkah untuk mencipta [ruang kerja baharu](create-workspace.md).

- Selepas anda mencipta ruang kerja, pergi ke **Pentadbir** > **Ruang Kerja** dan kemudian pilih **Panduan pemasangan**.

## <a name="configure-the-sdk"></a>Konfigurasikan SDK

Setelah anda memuat turun SDK, anda boleh beker dengannya dalam Xcode untuk mendayakan dan menentukan peristiwa. Terdapat dua cara untuk berbuat demikian

### <a name="option-1-using-cocoapods-recommended"></a>Pilihan 1: Menggunakan CocoaPods (disyorkan)
CocoaPods ialah pengurus pergantungan untuk projek Swift dan Objective-C Cocoa. Penggunaannya menjadikan integrasi SDK cerapan penglibatan untuk iOS lebih mudah. CocoaPods juga membolehkan anda menaik taraf kepada versi terkini SDK cerapan penglibatan. Berikut ialah cara menggunakan CocoaPods untuk mengintegrasikan SDK cerapan penglibatan SDK ke dalam projek Xcode anda. 

1. Pasang CocoaPods. 

1. Cipta fail baharu yang dipanggil Podfile dalam direktori akar projek anda dan tambahkan pernyataan yang berikut padanya.Gantikan YOUR_TARGET_PROJECT_NAME dengan nama projek Xcode anda. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
Konfigurasi pod di atas mengandungi kedua-dua versi nyahpepijat dan keluaran SDK. Pilih yang terbaik untuk projek anda.

1. Pasang pod dengan melaksanakan perintah berikut: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Pilihan 2: Menggunakan pautan muat turun

1. Muat turun [cerapan penglibatan SDK iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip), and letakkan fail `EIObjC.xcframework` dalam folder `Frameworks`.

1. Jika folder `Frameworks` tidak wujud, cipta satu dalam folder projek.

## <a name="enable-auto-instrumentation"></a>Dayakan autopengalatan
 
Anda boleh mendayakan autopengalatan tanpa pengekodan. Apabila projek berjalan, ia akan menjejaki peristiwa `view` dan `action` secara automatik menggunakan kunci pengingesan yang dikonfigurasikan. 

1. Kemas kini dan sertakan fail `EIConfig.plist` yang disediakan dalam folder direktori projek anda untuk medan berikut:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YA
    - autocollectAction = YA

2. Kemudian tambahkan fail `EIConfig.plist` pada projek anda dalam Xcode. 



Untuk menyahdayakan autopengalatan, kemas kini medan berikut dalam fail `EIConfig.plist` yang disertakan dalam folder direktori projek anda. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Melaksanakan peristiwa tersuai

1. Buka projek anda dalam Xcode, dan navigasi ke tetapan **Umum**. 
1. Tambahkan projek `EIObjC.xcframework` pada projek di bawah bahagian 'Rangka Kerja, Pustaka dan Kandungan Terbenam'.

1. Import fail pengepala rangka kerja dalam AppDelegate.m dengan cebisan berikut:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Memulakan cerapan penglibatan SDK daripada aplikasi: didFinishLaunchingWithOptions.
1. Salin cebisan XML daripada **Panduan pemasangan**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Jejak peristiwa:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Tetapkan butiran pengguna untuk peristiwa anda

SDK membolehkan anda mentakrifkan maklumat pengguna yang boleh dihantar dengan setiap peristiwa. Anda boleh menentukan maklumat pengguna dengan memanggil API `setUser:(nonnull EIUser *)user` pada SDK.

Menentukan butiran pengguna pada tahap `Analytics` bermakna bahawa semua telemetri akan mempunyai maklumat ini. Walau bagaimanapun, jika anda menentukan tahap peristiwa dengan memanggil API `setUser:(nonnull EIUser *)user` pada objek EIEvent, hanya peristiwa tertentu itu akan mengandungi maklumat.

Kelas data `EIUser` mengandungi sifat NSString berikut:

- **localId**: ID tempatan pengguna.
- **authId**: ID pengguna yang disahkan.
- **authType**: Jenis pengesahan yang digunakan untuk mendapatkan ID pengguna yang disahkan.
- **name**: Nama pengguna.
- **email**: Alamat e-mel pengguna.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
