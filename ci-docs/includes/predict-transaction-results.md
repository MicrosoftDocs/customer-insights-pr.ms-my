---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: ms-MY
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611132"
---
- **Prestasi model latihan**: Gred A, B, atau C menunjukkan prestasi ramalan dan boleh membantu anda membuat keputusan untuk menggunakan hasil yang disimpan dalam entiti output.

  Gred ditentukan berdasarkan peraturan berikut:
  - **A** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah lebih besar daripada kadar garis dasar sekurang-kurangnya 10%.
  - **B** apabila model meramalkan dengan tepat sekurang-kurangnya 50% daripada jumlah ramalan dan apabila peratusan ramalan yang tepat untuk pelanggan yang telah memberikan pulangan adalah sehingga 10% lebih besar daripada garis dasar.
  - **C** apabila model dengan tepat meramalkan kurang daripada 50% daripada jumlah ramalan, atau apabila peratusan ramalan tepat untuk pelanggan yang tergelak kurang daripada garis dasar.
  - **Baseline** mengambil input tetingkap masa ramalan untuk model (contohnya, satu tahun), dan mencipta pecahan masa yang berbeza dengan membahagikannya dengan 2 sehingga mencapai satu bulan atau kurang. Ia menggunakan bahagian ini untuk mewujudkan satu peraturan perniagaan bagi pelanggan yang belum membeli dalam tempoh masa ini. Pelanggan ini dianggap sebagai yang memberi pulangan. Peraturan perniagaan berasaskan masa dengan keupayaan tertinggi untuk meramalkan siapa yang mungkin churn dipilih sebagai model asas.

- **Kecenderungan untuk pulangan (bilangan pelanggan)**: Kumpulan pelanggan berdasarkan risiko pulangan mereka yang diramalkan. Secara pilihan, [buat segmen pelanggan](../prediction-based-segment.md) dengan risiko churn yang tinggi. Segmen seperti ini dapat membantu memahami tempat penggalan anda yang sepatutnya bagi keahlian segmen.

- **Faktor paling mempengaruhi**: Terdapat banyak faktor yang diambil kira apabila mencipta ramalan anda. Setiap faktor mempunyai kepentingannya yang dikira untuk ramalan teragregat yang dicipta oleh model. Gunakan faktor ini untuk membantu mengesahkan hasil ramalan anda. Atau gunakan maklumat ini kemudian untuk [mencipta segmen](../prediction-based-segment.md) yang boleh membantu mempengaruhi risiko churn untuk pelanggan.