---
title: BSCMAKE 錯誤 BK1503
ms.date: 11/04/2016
f1_keywords:
- BK1503
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
ms.openlocfilehash: 2c8ca005922c3c94b557e2f1052e8811099d9948
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555770"
---
# <a name="bscmake-error-bk1503"></a>BSCMAKE 錯誤 BK1503

無法寫入檔案 'filename' [: 原因]

BSCMAKE 結合成單一的瀏覽器資料庫在編譯期間產生的.sbr 檔案。 如果產生的瀏覽器資料庫超過 64 MB，或是輸入 (.sbr) 檔案數目超過 4092，就會發出此錯誤。

如果問題因為多個 4092.sbr 檔，您必須減少輸入的檔案數目。 從 Visual Studio 中，這可透過[/FR](../../build/reference/fr-fr-create-dot-sbr-file.md)您整個專案，然後重新檢查檔案的方式為基礎。

如果問題因為.bsc 檔案大於 64 MB，減少做為輸入的.sbr 檔數目會減少產生的.bsc 檔的大小。 此外，瀏覽資訊的數量可能會減少 / e m （排除巨集擴充符號）、 /El （排除區域變數） 和 /Es （排除系統檔案）。

## <a name="see-also"></a>另請參閱

[BSCMAKE 選項](../../build/reference/bscmake-options.md)