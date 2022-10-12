---
title: Model pembelajaran mesin tersuai | Dokumen Microsoft
description: Kerja dengan model tersuai daripada Azure Machine Learning dalam Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609757"
---
# <a name="custom-machine-learning-models"></a>Model pembelajaran mesin tersuai

> [!NOTE]
> Sokongan untuk studio Pembelajaran Mesin (klasik) akan berakhir pada 31 Ogos 2024. Kami mengesyorkan anda beralih kepada [Azure Pembelajaran Mesin](/azure/machine-learning/overview-what-is-azure-machine-learning) pada tarikh tersebut.
>
> Bermula 1 Disember 2021, anda tidak akan dapat mencipta sumber studio Pembelajaran Mesin (klasik) baharu. Sehingga 31 Ogos 2024, anda boleh terus menggunakan sumber studio Pembelajaran Mesin (klasik) sedia ada. Untuk maklumat lanjut, lihat [Migrasi ke Azure Pembelajaran Mesin](/azure/machine-learning/migrate-overview).

Model tersuai membolehkan anda menguruskan aliran kerja berdasarkan model Azure Pembelajaran Mesin. Aliran kerja membantu anda memilih data yang anda mahukan untuk menjana wawasan dan memetakan keputusan kepada data pelanggan disatukan anda. Untuk maklumat lanjut tentang membina model ML tersuai, lihat [Gunakan model berasaskan Pembelajaran Mesin Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Prasyarat

- Perkhidmatan web yang diterbitkan melalui [Azure Pembelajaran Mesin saluran paip kelompok](/azure/machine-learning/concept-ml-pipelines).
- Saluran paip mesti diterbitkan di bawah [titik akhir saluran paip](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Akaun [storan](/azure/storage/blobs/data-lake-storage-quickstart-create-account) Azure Data Lake Gen2 yang dikaitkan dengan tika Azure Studio anda.
- Untuk Azure Pembelajaran Mesin ruang kerja dengan saluran paip, keizinan Pemilik atau Pentadbir Capaian Pengguna kepada Azure Pembelajaran Mesin Workspace.

  > [!NOTE]
  > Data dipindahkan antara tika Customer Insights anda dengan perkhidmatan web Azure atau talian paip yang dipilih dalam aliran kerja. Apabila anda memindahkan data kepada perkhidmatan Azure, sila pastikan perkhidmatan dikonfigurasikan untuk memproses data mengikut cara dan lokasi yang diperlukan untuk mematuhi apa-apa keperluan undang-undang atau peraturan bagi data tersebut untuk organisasi anda.

## <a name="add-a-new-workflow"></a>Tambah aliran kerja baharu

1. Pergi ke **Kecerdasan** > **Model tersuai** dan pilih **Aliran kerja baharu**.

1. Berikan Nama yang **dikenali**.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Syot layar anak tetingkap aliran kerja Baharu.":::

1. Pilih organisasi yang mengandungi perkhidmatan web dalam **Penyewa yang mengandungi perkhidmatan web anda**.

1. Jika langganan Pembelajaran Mesin Azure berada dalam penyewa yang berbeza daripada Customer Insights, pilih **Daftar masuk** dengan kelayakan anda untuk organisasi yang dipilih.

1. Pilih **Ruang kerja** yang berkaitan dengan perkhidmatan web anda.

1. Pilih saluran paip Azure Pembelajaran Mesin dalam **perkhidmatan Web yang mengandungi juntai bawah model** anda. Kemudian pilih **Seterusnya**.
   Ketahui lebih lanjut tentang [menerbitkan talian paip dalam Pembelajaran Mesin Azure menggunakan pereka bentuk](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Untuk setiap **input Perkhidmatan web** pilih **Entiti** pemadanan daripada Customer Insights. Kemudian pilih **Seterusnya**.
   > [!NOTE]
   > Aliran kerja model tersuai akan menggunakan heuristik untuk memetakan medan input perkhidmatan web kepada atribut entiti berdasarkan nama dan jenis data medan. Anda akan melihat ralat jika medan perkhidmatan web tidak dapat dipetakan kepada entiti.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Konfigurasikan aliran kerja.":::

1. Untuk **Parameter** Output Model, setkan sifat berikut:
   - **Nama entiti** untuk hasil output saluran paip
   - **Nama parameter** output storan data bagi saluran paip kelompok anda
   - **Nama** parameter Laluan Output bagi saluran paip kelompok anda

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Anak tetingkap Parameter Output Model.":::

1. Pilih atribut yang sepadan daripada **ID Pelanggan dalam hasil** yang mengenal pasti pelanggan dan pilih **Simpan**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Kaitkan hasil dengan anak tetingkap data Pelanggan.":::

   Skrin **Disimpan** Aliran Kerja memaparkan butiran tentang aliran kerja. Jika anda mengkonfigurasikan aliran kerja untuk saluran paip Azure Pembelajaran Mesin, Wawasan Pelanggan melekat pada ruang kerja yang mengandungi saluran paip. Wawasan Pelanggan akan mendapat **peranan Penyumbang** pada ruang kerja Azure.

1. Pilih **Selesai**. Halaman **Model** Tersuai dipaparkan.

1. Pilih elipsis menegak (&vellip;) untuk aliran kerja dan pilih **Jalankan**. Aliran kerja anda juga berjalan secara automatik dengan setiap [segar semula](schedule-refresh.md) berjadual.

## <a name="manage-an-existing-workflow"></a>Menguruskan aliran kerja sedia ada

Pergi ke **model** > **Tersuai Kecerdasan** untuk melihat aliran kerja yang anda cipta.

Pilih aliran kerja untuk melihat tindakan yang tersedia.

- **Mengedit** aliran kerja
- **Menjalankan** aliran kerja
- [**Memadamkan**](#delete-a-workflow) aliran kerja

### <a name="edit-a-workflow"></a>Edit satu aliran kerja

1. Pergi ke **Model** > **Tersuai Perisikan**.

1. Di sebelah aliran kerja yang ingin dikemas kini, pilih elipsis menegak (&vellip;) dan pilih **Edit**.

1. Ubah **Nama** paparan jika perlu dan pilih **Berikut**.

1. Untuk setiap **input** perkhidmatan Web, kemas kini Entiti **yang** sepadan daripada Wawasan Pelanggan, jika perlu. Kemudian pilih **Seterusnya**.

1. Untuk **Parameter** Output Model, ubah mana-mana yang berikut:
   - **Nama entiti** untuk hasil output saluran paip
   - **Nama parameter** output storan data bagi saluran paip kelompok anda
   - **Nama** parameter Laluan Output bagi saluran paip kelompok anda

1. Tukar atribut yang sepadan daripada **ID Pelanggan dalam hasil** untuk mengenal pasti pelanggan. Pilih atribut daripada output inferens dengan nilai yang serupa dengan lajur ID Pelanggan bagi entiti Pelanggan. Jika anda tidak mempunyai lajur sedemikian dalam set data anda, pilih atribut yang mengenal pasti baris secara unik.

1. Pilih **Simpan**

### <a name="delete-a-workflow"></a>Padam satu aliran kerja

1. Pergi ke **Model** > **Tersuai Perisikan**.

1. Di sebelah aliran kerja yang ingin dipadamkan, pilih elipsis menegak (&vellip;) dan pilih **Padam**.

1. Sahkan pemadaman anda.

Aliran kerja anda akan dipadamkan. Entiti [yang](entities.md) dicipta apabila anda mencipta aliran kerja berterusan dan boleh dilihat daripada **halaman Entiti** > **Data**.

## <a name="view-the-results"></a>Lihat keputusan

Hasil daripada aliran kerja disimpan dalam nama entiti yang ditakrifkan untuk **Parameter** Output Model. Akses data ini daripada [**halaman** > **Entiti** Data](entities.md) atau dengan [akses](apis.md) API.

### <a name="api-access"></a>Akses API

Untuk pertanyaan OData khusus untuk mendapatkan data daripada entiti model tersuai, gunakan format berikut:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Gantikan `<your instance id>` dengan ID persekitaran Wawasan Pelanggan anda, yang dipaparkan dalam bar alamat pelayar anda semasa mengakses Wawasan Pelanggan.

1. Gantikan `<custom model output entity>` dengan nama entiti yang anda berikan untuk **Parameter** Output Model.

1. Gantikan `<guid value>` dengan ID Pelanggan pelanggan yang ingin anda akses. ID ini dipaparkan pada [halaman](customer-profiles.md) profil pelanggan dalam medan Id Pelanggan.

## <a name="frequently-asked-questions"></a>Soalan Lazim

- Mengapakah saya tidak dapat melihat talian paip saya apabila menyediakan aliran kerja model tersuai?
  Isu ini sering disebabkan oleh isu konfigurasi dalam talian paip. Pastikan [parameter input dikonfigurasikan](azure-machine-learning-experiments.md#dataset-configuration) dan [parameter laluan dan storan data output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) juga dikonfigurasikan.

- Apakah makna ralat "Tidak dapat menyimpan aliran kerja kecerdasan"? 
  Pengguna biasanya melihat mesej ralat ini jika mereka tidak mempunyai kelayakan Pentadbir Akses Pengguna atau Pemilik di ruang kerja. Pengguna memerlukan keizinan yang lebih tinggi untuk mendayakan Customer Insights untuk memproses aliran kerja sebagai perkhidmatan dan bukannya menggunakan kelayakan pengguna untuk menjalankan aliran kerja yang seterusnya.

- Adakah endpoint peribadi / pautan peribadi untuk aliran kerja model tersuai saya disokong?
  Wawasan Pelanggan pada masa ini tidak menyokong titik akhir peribadi untuk model tersuai di luar kotak, tetapi penyelesaian manual tersedia. Sila hubungi sokongan untuk maklumat lanjut.

## <a name="responsible-ai"></a>AI Yang Bertanggungjawab

Ramalan menawarkan keupayaan untuk mencipta pengalaman pelanggan yang lebih baik, meningkatkan keupayaan perniagaan dan strim hasil. Kami amat mengesyorkan agar anda mengimbangkan nilai ramalan anda terhadap kesan yang telah diberikan dan bias yang mungkin diperkenalkan dengan cara yang beretika. Ketahui lebih lanjut tentang cara Microsoft [menangani AI Yang Bertanggungjawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Anda juga boleh mengetahui tentang [teknik dan proses untuk pembelajaran mesin yang bertanggungjawab](/azure/machine-learning/concept-responsible-ml) khusus kepada Pembelajaran Mesin Azure.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
