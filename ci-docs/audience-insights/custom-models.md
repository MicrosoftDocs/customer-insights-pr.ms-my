---
title: Model pembelajaran mesin tersuai | Dokumen Microsoft
description: Kerja dengan model tersuai daripada Azure Machine Learning dalam Dynamics 365 Customer Insights.
ms.date: 12/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 460b68e1e65b3033af0a03d1bcc27e718c79d7aa
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355097"
---
# <a name="custom-machine-learning-models"></a>Model pembelajaran mesin tersuai

> [!NOTE]
> Sokongan untuk Pembelajaran Mesin Studio (klasik) akan berakhir pada 31 Ogos 2024. Kami mengesyorkan agar anda beralih ke [Azure Pembelajaran Mesin](/azure/machine-learning/overview-what-is-azure-machine-learning) pada tarikh tersebut.
>
> Mulai 1 Disember 2021, anda tidak akan dapat mencipta sumber studio Pembelajaran Mesin (klasik) baru. Melalui 31 Ogos 2024, anda boleh terus menggunakan sumber Pembelajaran Mesin Studio (klasik) yang sedia ada. Untuk maklumat lanjut, lihat [Berhijrah ke Azure Pembelajaran Mesin](/azure/machine-learning/migrate-overview).


**Kecerdasan** > **Model tersuai** membolehkan anda mengurus aliran kerja berasaskan model Pembelajaran Mesin Azure. Aliran kerja membantu anda memilih data yang anda mahukan untuk menjana wawasan dan memetakan keputusan kepada data pelanggan disatukan anda. Untuk maklumat lanjut tentang membina model ML tersuai, lihat [Gunakan model berasaskan Pembelajaran Mesin Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>AI Yang Bertanggungjawab

Ramalan menawarkan keupayaan untuk mencipta pengalaman pelanggan yang lebih baik, meningkatkan keupayaan perniagaan dan strim hasil. Kami amat mengesyorkan agar anda mengimbangkan nilai ramalan anda terhadap kesan yang telah diberikan dan bias yang mungkin diperkenalkan dengan cara yang beretika. Ketahui lebih lanjut tentang cara Microsoft [menangani AI Yang Bertanggungjawab](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Anda juga boleh mengetahui tentang [teknik dan proses untuk pembelajaran mesin yang bertanggungjawab](/azure/machine-learning/concept-responsible-ml) khusus kepada Pembelajaran Mesin Azure.

## <a name="prerequisites"></a>Prasyarat

- Ciri ini menyokong perkhidmatan web yang diterbitkan melalui [talian paip kumpulan Azure Pembelajaran Mesin](/azure/machine-learning/concept-ml-pipelines).

- Anda memerlukan akaun storan Azure Data Lake Gen2 yang berkaitan dengan tika Azure Studio anda untuk menggunakan ciri ini. Untuk mendapatkan maklumat lanjut, lihat [Cipta akaun storan Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Untuk ruang kerja Pembelajaran Mesin Azure dengan talian paip, anda memerlukan keizinan Pemilik atau Pentadbir Akses Pengguna untuk Ruang Kerja Pembelajaran Mesin Azure.

   > [!NOTE]
   > Data dipindahkan antara tika Customer Insights anda dengan perkhidmatan web Azure atau talian paip yang dipilih dalam aliran kerja. Apabila anda memindahkan data kepada perkhidmatan Azure, sila pastikan perkhidmatan dikonfigurasikan untuk memproses data mengikut cara dan lokasi yang diperlukan untuk mematuhi apa-apa keperluan undang-undang atau peraturan bagi data tersebut untuk organisasi anda.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

## <a name="add-a-new-workflow"></a>Tambah aliran kerja baharu

1. Pergi ke **Kecerdasan** > **Model tersuai** dan pilih **Aliran kerja baharu**.

1. Berikan model tersuai anda nama yang mudah dikenali dalam medan **Nama**.

   > [!div class="mx-imgBorder"]
   > ![Syot layar anak tetingkap aliran kerja Baharu.](media/new-workflowv2.png "Petikan skrin anak tetingkap aliran kerja Baharu")

1. Pilih organisasi yang mengandungi perkhidmatan web dalam **Penyewa yang mengandungi perkhidmatan web anda**.

1. Jika langganan Pembelajaran Mesin Azure berada dalam penyewa yang berbeza daripada Customer Insights, pilih **Daftar masuk** dengan kelayakan anda untuk organisasi yang dipilih.

1. Pilih **Ruang kerja** yang berkaitan dengan perkhidmatan web anda. 

1. Pilih saluran paip Azure Pembelajaran Mesin dalam **perkhidmatan Web yang mengandungi juntai bawah model** anda. Kemudian pilih **Seterusnya**.    
   Ketahui lebih lanjut tentang [menerbitkan talian paip dalam Pembelajaran Mesin Azure menggunakan pereka bentuk](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) atau [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Talian paip anda mesti diterbitkan di bawah [titik tamat talian paip](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Untuk setiap **Input perkhidmatan web**, pilih **Entiti** yang berpadanan daripada wawasan khalayak dan pilih **Seterusnya**.
   > [!NOTE]
   > Aliran kerja model tersuai akan menggunakan heuristik untuk memetakan medan input perkhidmatan web kepada atribut entiti berdasarkan nama dan jenis data medan. Anda akan melihat ralat jika medan perkhidmatan web tidak dapat dipetakan kepada entiti.

   > [!div class="mx-imgBorder"]
   > ![Konfigurasikan aliran kerja.](media/intelligence-screen2-updated.png "Konfigurasikan aliran kerja")

1. Dalam langkah **Parameter Output Model**, tetapkan ciri berikut:
      1. Masukkan output **Nama entiti** yang anda mahu hasil output talian paip mengalir masuk.
      1. Pilih **Nama parameter storan data output** bagi talian paip kelompok daripada juntai bawah.
      1. Pilih **Nama parameter Laluan Output** bagi talian paip kelompok daripada juntai bawah.

      > [!div class="mx-imgBorder"]
      > ![Anak tetingkap Parameter Output Model.](media/intelligence-screen3-outputparameters.png "Anak tetingkap Parameter Output Model")

1. Pilih atribut sepadan daripada senarai juntai bawah **ID Pelanggan dalam hasil** yang mengenal pasti pelanggan dan pilih **Simpan**.

   > [!div class="mx-imgBorder"]
   > ![Kaitkan hasil dengan anak tetingkap data Pelanggan.](media/intelligence-screen4-relatetocustomer.png "Kaitkan hasil dengan anak tetingkap data Pelanggan")

1. Anda akan melihat skrin **Aliran Kerja Disimpan** dengan butiran tentang aliran kerja tersebut.    
   Jika anda mengkonfigurasi aliran kerja untuk talian paip Pembelajaran Mesin Azure, wawasan khalayak akan dilampirkan ke ruang kerja yang mengandungi talian paip. Wawasan khalayak akan mendapat peranan **Penyumbang** pada ruang kerja Azure.

1. Pilih **Selesai**.

1. Anda kini boleh menjalankan aliran kerja daripada halaman **Model Tersuai**.

## <a name="edit-a-workflow"></a>Edit satu aliran kerja

1. Pada halaman **Model Tersuai**, pilih elipsis menegak dalam lajur **Tindakan** di sebelah aliran kerja yang anda cipta sebelum ini dan pilih **Edit**.

1. Anda boleh mengemas kini nama aliran kerja anda yang dikenali dalam medan **Nama paparan** tetapi anda tidak boleh mengubah perkhidmatan web atau talian paip yang dikonfigurasi. Pilih **Seterusnya**.

1. Untuk setiap **Input perkhidmatan web**, anda boleh mengemas kini **Entiti** yang berpadanan daripada wawasan khalayak. Kemudian pilih **Seterusnya**.

1. Dalam langkah **Parameter Output Model**, tetapkan ciri berikut:
      1. Masukkan output **Nama entiti** yang anda mahu hasil output talian paip mengalir masuk.
      1. Pilih **Nama parameter storan data output** untuk talian paip ujian anda.
      1. Pilih **Nama parameter Laluan Output** untuk talian paip ujian anda.

1. Pilih atribut sepadan daripada senarai juntai bawah **ID Pelanggan dalam hasil** yang mengenal pasti pelanggan dan pilih **Simpan**.
   Pilih atribut daripada output inferens dengan nilai yang serupa dengan lajur ID Pelanggan bagi entiti Pelanggan. Jika tidak mempunyai lajur sedemikian dalam set data anda, pilih atribut yang mengenal pasti baris secara unik.

## <a name="run-a-workflow"></a>Jalankan aliran kerja

1. Pada halaman **Model Tersuai**, pilih elipsis menegak dalam lajur **Tindakan** di sebelah aliran kerja yang anda cipta sebelum ini.

1. Pilih **Jalankan**.

Aliran kerja anda juga berjalan secara automatik dengan setiap muat semula berjadual. Ketahui lebih lanjut tentang [menyediakan menyegarkan semula berjadual](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Padam satu aliran kerja

1. Pada halaman **Model Tersuai**, pilih elipsis menegak dalam lajur **Tindakan** di sebelah aliran kerja yang anda cipta sebelum ini.

1. Pilih **Padam** dan sahkan pemadaman anda.

Aliran kerja anda akan dipadamkan. [Entiti](entities.md) yang telah dicipta apabila anda mencipta aliran kerja berlanjutan dan boleh dilihat daripada halaman **Entiti**.

## <a name="results"></a>Keputusan

Hasil daripada aliran kerja disimpan dalam entiti yang dikonfigurasikan semasa fasa Parameter Output Model. Anda boleh mengakses data ini daripada [halaman entiti](entities.md) atau dengan [akses API](apis.md).

### <a name="api-access"></a>Akses API

Untuk pertanyaan OData khusus untuk mendapatkan data daripada entiti model tersuai, gunakan format berikut:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Gantikan `<your instance id>` dengan ID persekitaran Customer Insights anda, yang anda dapati dalam bar alamat pelayar anda semasa mengakses Customer Insights.

1. Gantikan `<custom model output entity>` dengan nama entiti yang anda berikan semasa langkah Parameter Output Model konfigurasi model tersuai.

1. Gantikan `<guid value>` dengan ID Pelanggan yang anda mahu mengakses rekod. Anda biasanya boleh mencari ID ini pada [halaman profil pelanggan](customer-profiles.md) dalam medan CustomerID.

## <a name="frequently-asked-questions"></a>Soalan Lazim

- Mengapakah saya tidak dapat melihat talian paip saya apabila menyediakan aliran kerja model tersuai?    
  Isu ini sering disebabkan oleh isu konfigurasi dalam talian paip. Pastikan [parameter input dikonfigurasikan](azure-machine-learning-experiments.md#dataset-configuration) dan [parameter laluan dan storan data output](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) juga dikonfigurasikan.

- Apakah makna ralat "Tidak dapat menyimpan aliran kerja kecerdasan"?    
  Pengguna biasanya melihat mesej ralat ini jika mereka tidak mempunyai kelayakan Pentadbir Akses Pengguna atau Pemilik di ruang kerja. Pengguna memerlukan keizinan yang lebih tinggi untuk mendayakan Customer Insights untuk memproses aliran kerja sebagai perkhidmatan dan bukannya menggunakan kelayakan pengguna untuk menjalankan aliran kerja yang seterusnya.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
