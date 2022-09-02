---
title: Gunakan Customer Insights API
description: Gunakan API dan fahami pengehadan.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387351"
---
# <a name="work-with-customer-insights-apis"></a>Gunakan Customer Insights API

Dynamics 365 Customer Insights menyediakan API untuk membina aplikasi anda sendiri berdasarkan data anda dalam Customer Insights.

> [!IMPORTANT]
> Butiran API ini, disenaraikan pada [rujukan API Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Ia termasuk maklumat tambahan mengenai operasi, parameter dan respons.

Cuba API Wawasan Pelanggan, cipta Pendaftaran Aplikasi Azure dan mulakan dengan pustaka klien.

## <a name="get-started-trying-the-customer-insights-apis"></a>Mula mencuba Customer Insights API

Dayakan API Wawasan Pelanggan dan cubalah. Pentadbir Wawasan Pelanggan mesti mendayakan akses API kepada Wawasan Pelanggan. Sebaik sahaja akses didayakan, mana-mana pengguna boleh menggunakan API dengan kunci langganan.

1. [Daftar Masuk](https://home.ci.ai.dynamics.com) ke Customer Insights. Jika anda tidak mempunyai langganan lagi, [daftar untuk percubaan Customer Insights](https://aka.ms/tryci).

1. Pergi ke **Keselamatan** > **Pentadbir** dan pilih tab **API**.

1. Jika capaian API ke persekitaran belum disediakan, pilih **Dayakan**.

   Mendayakan API mencipta kunci langganan utama dan sekunder untuk tika anda yang akan digunakan dalam permintaan API. Untuk menjana semula kekunci, pilih **jana semula primer** atau **Jana semula sekunder** pada tab **API**.

1. Pilih [**Terokai API kami**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) untuk mencuba API.

1. Cari dan pilih operasi API dan pilih **Cuba.**

   :::image type="content" source="media/try-api.png" alt-text="Cara menguji API.":::

1. Dalam anak tetingkap sisi, tetapkan nilai dalam menu juntai bawah **Kebenaran** untuk **tersirat**. Pengepala `Authorization` akan ditambahkan dengan token pembawa. Kunci langganan anda diisi secara automatik.
  
1. Secara alternatif, tambah semua parameter pertanyaan yang perlu.

1. Tatal ke bahagian bawah tetingkap sisi dan pilih **Hantar**.

   Respons HTTP dipaparkan di bahagian bawah anak tetingkap.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Cipta pendaftaran aplikasi baharu dalam portal Azure

Cipta pendaftaran [aplikasi baru](/graph/auth-register-app-v2) untuk menggunakan API Wawasan Pelanggan dalam aplikasi Azure menggunakan keizinan diwakilkan.

1. Lengkapkan bahagian [Bermula](#get-started-trying-the-customer-insights-apis).

1. Daftar masuk ke [portal Azure](https://portal.azure.com) dengan akaun yang boleh mengakses data Customer Insights.

1. Cari dan kemudian pilih **Pendaftaran aplikasi**.

1. Pilih **Pendaftaran baharu**, berikan nama aplikasi dan pilih jenis akaun.

   Secara alternatif, tambah URL hala semula. http://localhost adalah mencukupi untuk membangunkan aplikasi pada komputer tempatan anda.

1. Pilih **Daftar**.

1. Pada pendaftaran Aplikasi baharu anda, pergi ke **Keizinan API**.

1. Pilih **Tambah keizinan** dan pilih **Dynamics 365 AI for Customer Insights** dalam anak tetingkap sisi.

1. Untuk **Jenis keizinan**, pilih **Keizinan yang ditugaskan** dan kemudian pilih keizinan **user_impersonation**.

1. Pilih **Tambah keizinan**.

1. Pilih **Berikan keizinan pentadbir untuk...** untuk melengkapkan pendaftaran aplikasi.

1. Untuk mengakses API tanpa log masuk pengguna, pergi ke [keizinan](#server-to-server-application-permissions) aplikasi Pelayan-ke-pelayan.

Anda boleh menggunakan ID Aplikasi/Klien untuk pendaftaran aplikasi ini dengan [Pustaka Pengesahan Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) untuk mendapatkan token pembawa untuk dihantar dengan permintaan anda kepada API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Untuk mendapatkan maklumat tentang penggunaan API dalam pustaka klien kami, lihat [Pustaka klien Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Keizinan aplikasi pelayan ke pelayan

Buat pendaftaran apl yang tidak memerlukan interaksi pengguna dan boleh dijalankan pada pelayan.

1. Pada pendaftaran Aplikasi anda dalam portal Azure, pergi ke **Keizinan API**.

1. Pilih **Tambah keizinan**.

1. Pilih tab **API organisasi saya menggunakan** dan pilih **Dynamics 365 AI untuk Customer Insights** daripada senarai.

1. Untuk **Jenis keizinan**, pilih **Keizinan aplikasi** dan kemudian pilih keizinan **CustomerInsights.Api.All**.

1. Pilih **Tambah keizinan**.

1. Kembali ke **Keizinan API** untuk pendaftaran aplikasi anda.

1. Pilih **Berikan keizinan pentadbir untuk...** untuk melengkapkan pendaftaran aplikasi.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Tambah nama pendaftaran aplikasi sebagai pengguna dalam Wawasan Pelanggan.

   1. Buka Wawasan Pelanggan, pergi ke **Keselamatan** > **Pentadbir** dan pilih **Tambah pengguna**.

   1. Cari nama pendaftaran aplikasi anda, pilih nama daripada hasil carian dan pilih **Simpan**.

## <a name="sample-queries"></a>Sampel pertanyaan

Untuk senarai pendek pertanyaan sampel OData untuk berfungsi dengan API, lihat [contoh](odata-examples.md) pertanyaan OData.

## <a name="customer-insights-client-libraries"></a>Pustaka klien Customer Insights

Mari bermula menggunakan pustaka klien yang tersedia untuk API Wawasan Pelanggan. Semua kod sumber pustaka dan aplikasi sampel boleh ditemui pada [halaman Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Gunakan pustaka klien C# daripada NuGet.org. Pada masa ini, pakej menyasarkan rangka kerja netstandard2.0 dan netcoreapp2.0. Untuk maklumat lanjut tentang NuGet pakej, lihat [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Tambah pustaka klien C# untuk projek C#

1. Dalam Visual Studio, buka **Pengurus Pakej NuGet** untuk projek anda.

1. Cari **Microsoft.Dynamics.CustomerInsights.Api**.

1. Pilih **Pasang** untuk menambah pakej ke projek.

   Secara alternatif, jalankan perintah ini dalam **Konsol Pengurus Pakej NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Gunakan pustaka klien C#

1. Gunakan [Pustaka Pengesahan Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) untuk memperoleh `AccessToken` menggunakan [pendaftaran aplikasi Azure](#create-a-new-app-registration-in-the-azure-portal) anda yang sedia ada.

1. Selepas berjaya mengesahkan dan memperoleh token, bina yang baharu atau gunakan yang sedia `HttpClient` ada dengan **set "Kebenaran"** DefaultRequestHeaders kepada **Bearer "token akses"** dan **Ocp-Apim-Subscription-Key** ditetapkan kepada [**kunci** langganan dari persekitaran](#get-started-trying-the-customer-insights-apis) Wawasan Pelanggan anda.   

   Tetapkan semula pengepala **Pengesahan** apabila sesuai. Contohnya, apabila token tamat tempoh.

1. Hantar `HttpClient` ini ke dalam pembinaan klien `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Buat panggilan dengan klien ke "kaedah lanjutan", contohnya, `GetAllInstancesAsync`. Jika akses kepada pendasar `Microsoft.Rest.HttpOperationResponse` lebih disukai, gunakan "kaedah mesej http", sebagai contoh,`GetAllInstancesWithHttpMessagesAsync`.

1. Tindak balas mungkin `object` menaip kerana kaedah boleh mengembalikan pelbagai jenis (contohnya, `IList<InstanceInfo>` dan `ApiErrorResult`). Untuk menyemak jenis pengembalian, gunakan objek dalam jenis respons yang ditentukan pada [halaman](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) butiran API untuk pengendalian tersebut.

   Jika maklumat lanjut mengenai permintaan diperlukan, gunakan **kaedah mesej http** untuk mengakses objek respons mentah.

### <a name="nodejs-package"></a>Pakej NodeJS

Gunakan pustaka klien NodeJS yang tersedia melalui NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pakej Python

Gunakan pustaka klien Python yang tersedia melalui PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
