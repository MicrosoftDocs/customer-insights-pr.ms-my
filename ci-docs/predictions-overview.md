---
title: Gambaran keseluruhan ramalan
description: Senario dan pilihan ramalan dilindungi oleh aplikasi Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610201"
---
# <a name="predictions-overview"></a>Gambaran keseluruhan ramalan

Dynamics 365 Customer Insights dilengkapi dengan pelbagai pilihan yang memanfaatkan AI dan pembelajaran mesin untuk meramalkan data.

## <a name="out-of-box-models"></a>Model luar kotak

Cara paling mudah untuk bermula dengan meramalkan data adalah model yang ditakrif lebih awal, sering dirujuk sebagai model luar kotak. Mereka hanya memerlukan data dan struktur tertentu untuk menjana cerapan dengan cepat. Model berikut boleh didapati:

# <a name="individual-consumers-b-to-c"></a>[Pengguna individu (niaga-ke-pengguna)](#tab/b2c)

- [Nilai sepanjang hayat pelanggan](predict-customer-lifetime-value.md): Meramalkan potensi hasil pelanggan dalam keseluruhan interaksi dengan perniagaan.
- [Pengesyoran produk](predict-product-recommendation.md): Mencadangkan set pengesyoran produk ramalan berdasarkan tingkah laku pembelian dan pelanggan dengan corak pembelian yang sama.
- [Pulangan langganan](predict-subscription-churn.md): Meramalkan sama ada pelanggan berisiko untuk tidak menggunakan lagi produk atau perkhidmatan langganan syarikat anda.
- [Churn](predict-transactional-churn.md) transaksi: Meramalkan jika pelanggan individu tidak lagi akan membeli produk atau perkhidmatan anda dalam jangka masa tertentu.
- [Analisis sentimen](sentiment-analysis.md): Menganalisis sentimen maklum balas pelanggan dan mengenal pasti aspek perniagaan yang sering disebutkan.

# <a name="business-accounts-b-to-b"></a>[Akaun perniagaan (niaga-ke-niaga)](#tab/b2b)

- [Churn](predict-transactional-churn.md) transaksi: Meramalkan jika akaun pelanggan tidak lagi akan membeli produk atau perkhidmatan anda dalam jangka masa tertentu.

---

> [!TIP]
> Kami mengesyorkan agar anda sentiasa menyegarkan semula model luar kotak dengan data yang dikemas kini untuk memastikan ia memaklumkan kes penggunaan perniagaan anda dengan tepat. Data disegar semula secara ad hoc apabila sistem menelan sumber data baharu atau dikemas kini. Walau bagaimanapun, model hanya akan diselaraskan semula dalam kes ini dan terus menggunakan data latihan sedia ada.
>
> **Konfigurasikan jadual** Kemas Kini dengan mengesetkan jadual latihan semula model semasa konfigurasi. Model ini akan melatih semula dan menyusun semula jadual ini, yang boleh anda ubah pada bila-bila masa.

## <a name="azure-machine-learning-integration"></a>Penyepaduan Pembelajaran Mesin Azure

Jika sesebuah organisasi sudah menggunakan senario pembelajaran mesin berdasarkan eksperimen Pembelajaran Mesin Azure, ciri model tersuai dalam Customer Insights membantu untuk menyambungkan titik. Cipta aliran kerja yang membantu anda memilih data yang ingin anda janakan cerapan dan petakan hasil kepada profil pelanggan anda yang disatukan. Untuk mendapatkan maklumat lanjut, lihat [Model pembelajaran mesin tersuai](custom-models.md).

## <a name="manage-existing-predictions"></a>Urus ramalan sedia ada

Pergi ke **halaman Ramalan** > **Perisikan**. Pada tab **Ramalan** saya, lihat ramalan yang anda cipta, jenis ramalan, nama entiti output, status, kali terakhir ramalan diedit dan kali terakhir data disegar semula. Anda boleh mengisih senarai ramalan mengikut sebarang lajur.

Pilih ramalan untuk melihat tindakan yang tersedia.

:::image type="content" source="media/predictions.png" alt-text="Halaman ramalan saya.":::

- **Edit** ramalan untuk mengubah sifatnya.
- [**Menyegar semula**](#refresh-a-prediction) ramalan untuk memasukkan data terkini.
- **Lihat** butiran ramalan.
- [**Laporan**](#view-the-input-data-usability-report) kebolehgunaan data input untuk melihat ralat, amaran dan cadangan.
- **Padamkan** ramalan.

### <a name="refresh-a-prediction"></a>Segar semula ramalan

Ramalan boleh disegar semula pada jadual automatik atau disegar semula secara manual atas permintaan. Untuk menyegar semula semua ramalan secara manual, pilih **Segar Semula semua**. Untuk menyegar semula ramalan secara manual, pilih dan pilih **Segar Semula**. Untuk [menjadualkan segar semula](schedule-refresh.md) automatik, pergi ke **Jadual** > **Sistem** > **Pentadbir**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Lihat laporan kebolehgunaan data input

Laporan kebolehgunaan data input menyediakan pandangan ralat disatukan dan amaran bahawa ramalan luar kotak anda mungkin menjana. Ia juga memberikan cadangan tentang cara meningkatkan prestasi model.

Laporan tersedia selepas model selesai proses latihan. Ia dicipta untuk setiap model secara berasingan, tidak kira sama ada ia berjaya menamatkan latihan dengan jayanya atau tidak.

Pada tab **Ramalan** saya, pilih ramalan dan pilih **Input laporan** kebolehgunaan data. Atau daripada pandangan butiran ramalan, pilih **Masukkan laporan** kebolehgunaan data.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Contoh laporan kebolehgunaan data input yang menunjukkan jadual dengan ralat, amaran dan pengesyoran.":::

Laporan ini merangkumi:

- **Nama:** Nama deskriptif ralat, amaran atau cadangan.
- **Langkah:** Fasa model, kereta api atau skor, maklumat merujuk kepada.
- **Negeri:** Keterukan maklumat (ralat, amaran, cadangan).
- **Nama lajur:** Lajur dalam entiti yang perlu diubah suai untuk meningkatkan prestasi model.
- **Nama entiti:** Nama entiti yang perlu diubah suai untuk meningkatkan prestasi model.
- **Butiran:** Butiran tentang ralat, amaran atau cadangan.

[!INCLUDE [footer-include](includes/footer-banner.md)]
