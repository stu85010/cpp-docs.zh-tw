---
title: A.1 平行執行簡單迴圈
ms.date: 11/04/2016
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
ms.openlocfilehash: 5bd9a9c8b1d226c67f7e9031a547e551fae3407b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558934"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1 平行執行簡單迴圈

下列範例示範如何平行處理簡單的迴圈，使用`parallel for`指示詞 ([一節 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md)上 16)。 迴圈反覆項目變數是預設的情況下，私人的因此不需要明確指定 private 子句中。

```
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```