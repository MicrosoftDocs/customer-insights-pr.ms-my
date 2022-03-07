---
title: Cipta pautan antara cerapan khalayak dan cerapan penglibatan
description: Cipta pautan aktif antara cerapan khalayak dan cerapan penglibatan untuk mendayakan perkongsian dwiarah data.
ms.date: 09/08/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56adc206d83bc6e34a55f11383393b5ac66da531
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229883"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Cipta pautan antara cerapan khalayak dan cerapan penglibatan

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Integrasi antara cerapan penglibatan dan cerapan khalayak pautan persekitaran daripada kedua-dua keupayaan dan mendayakan data untuk dikongsi secara dwiarah antara mereka.

Gunakan profil dan segmen disatukan daripada cerapan khalayak untuk lebih banyak pilihan analisis dalam cerapan penglibatan. Eksport peristiwa yang mempunyai nilai perniagaan yang tinggi daripada cerapan penglibatan. Gunakan peristiwa ini untuk menambahkan data kepada profil disatukan dalam cerapan khalayak.

## <a name="prerequisites"></a>Prasyarat

- Profil cerapan khalayak mesti disimpan dalam akaun Azure Data Lake Storage yang anda miliki atau dalam [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash;data lake yang diuruskan. 
- Persekitaran cerapan khalayak anda harus mempunyai persekitaran Dataverse yang berkaitan. Dan jika persekitaran tersebut juga menggunakan Dataverse untuk storan data, pastikan anda menyemak pilihan **Dayakan perkongsian data** dalam cerapan khalayak. Untuk mendapatkan maklumat lanjut, lihat [Cipta dan konfigurasikan persekitaran dalam cerapan khalayak](../audience-insights/create-environment.md).
- Anda memerlukan keizinan pentadbir untuk kedua-dua cerapan penglibatan dan persekitaran cerapan khalayak.
- Persekitaran yang dipautkan mestilah dalam rantau geografi yang sama.

> [!NOTE]
> - Jika langganan cerapan khalayak anda ialah percubaan yang menggunakan cerapan khalayak Data Lake yang diuruskan secara dalaman, hubungi [pirequest@microsoft.com](mailto:pirequest@microsoft.com) untuk mendapatkan bantuan. 
> - Jika persekitaran cerapan khalayak anda menggunakan Azure Data Lake Storage anda sendiri untuk menyimpan data, anda perlu menambah cerapan penglibatan prinsipal perkhidmatan Azure ke akaun storan anda. Untuk mendapatkan butiran, pergi ke [Sambungkan kepada akaun Azure Data Lake Storage dengan prinsipal perkhidmatan Azure untuk cerapan khalayak](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Cipta pautan persekitaran

Anda boleh mencipta pautan persekitaran dengan mengemas kini tetapan **Pentadbir** > **Persekitaran** dalam cerapan penglibatan.

**Untuk mewujudkan pautan aktif antara cerapan khalayak dan cerapan penglibatan**

1. Pada halaman **Pentadbir persekitaran** pilih tab **Persekitaran pautan**.

    :::image type="content" source="media/integrate1.png" alt-text="Sediakan persekitaran.":::

1. Pilih **Sediakan persekitaran** dalam sudut kiri atas atau di bawah skrin.

     :::image type="content" source="media/integrate2.png" alt-text="Pilih persekitaran cerapan khalayak.":::

1. Pilih persekitaran cerapan khalayak dan kemudian pilih ***Seterusnya** untuk menyelesaikan. Sekarang anda boleh memilih ciri pilihan untuk persekitaran yang dipautkan.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Dayakan cerapan khalayak segmen dan profil atribut disatukan

Selepas memautkan persekitaran, anda boleh memilih ciri pilihan untuk persekitaran yang dipautkan. Ciri ini mendayakan segmen dan atribut profil disatukan daripada cerapan khalayak untuk analisis interaktif pada data pelanggan.

> [!IMPORTANT]
> Untuk segmen cerapan khalayak untuk muncul dalam cerapan penglibatan, anda mesti [jalankan proses gabungan dan hiliran](../audience-insights/merge-entities.md) terlebih dahulu. Proses hiliran adalah penting kerana ia menjana jadual unik yang menyediakan segmen cerapan khalayak untuk dikongsi dengan cerapan penglibatan. (Jika sistem segar semula dijadualkan, ia akan secara automatik memasukkan proses hiliran.)

**Untuk menganalisis data web dalam cerapan penglibatan**

1. Pada halaman **Pentadbir persekitaran**, hidupkan togol **Kongsi data daripada cerapan khalayak dengan cerapan penglibatan** dan kemudian pilih **Seterusnya**.

    :::image type="content" source="media/integrate4.png" alt-text="Pilih ciri.":::

1. Pilih atribut profil disatukan yang akan menjadi dimensi dalam cerapan penglibatan. (Tidak semua atribut adalah dimensi yang berguna. Sebagai contoh, anda mungkin tidak memerlukan **Nama pertama** atau **Nama akhir** sebagai atribut untuk analisis peristiwa tapak web anda.)

    :::image type="content" source="media/integrate5.png" alt-text="Uruskan dimensi.":::

   >[!NOTE]
   > Semua atribut profil cerapan khalayak yang mewakili pengecam (seperti **ID** dan **ID alternatif**) ditapis keluar daripada atribut tersedia dan menjadi dimensi dalam cerapan penglibatan.

1. Apabila anda sudah selesai memilih atribut, pilih **Seterusnya**.
1. Tambah pengguna yang boleh melihat dimensi dan segmen profil cerapan khalayak dalam cerapan penglibatan.

    :::image type="content" source="media/integrate6.png" alt-text="Uruskan capaian kepada data pelanggan.":::

   > [!IMPORTANT]
   > Jika anda tidak secara eksplisit menambah pengguna dalam langkah ini, data akan disembunyikan daripada pengguna dalam cerapan penglibatan.
   > Untuk segmen cerapan khalayak untuk muncul dalam cerapan penglibatan, anda mesti [jalankan proses gabungan dan hiliran](../audience-insights/merge-entities.md) terlebih dahulu. Proses hiliran adalah penting kerana ia menjana jadual unik yang menyediakan segmen cerapan khalayak untuk dikongsi dengan cerapan penglibatan. (Jika sistem segar semula dijadualkan, ia akan secara automatik memasukkan proses hiliran.)

1. Semak pilihan anda dan kemudian pilih **Tamat**.

    :::image type="content" source="media/integrate7.png" alt-text="Semak tetapan data pelanggan.":::

## <a name="export-refined-events-to-audience-insights"></a>Eksport peristiwa diperhalus kepada cerapan khalayak

Selepas anda mencipta pautan antara persekitaran, anda boleh mengeksport peristiwa diperhalusi daripada cerapan penglibatan kepada cerapan khalayak dan injes mereka sebagai sumber data baharu. 

Untuk mendapatkan maklumat lanjut, pergi ke [Sepadukan data web daripada cerapan penglibatan dengan cerapan khalayak](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
