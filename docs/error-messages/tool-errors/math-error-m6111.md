---
title: 運算錯誤 M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 44f406881d64d13e23ca2c0911ee278c864a2c11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510782"
---
# <a name="math-error-m6111"></a>運算錯誤 M6111

stack 反向溢位

浮點運算導致 8087/287/387 副處理器或模擬器上的堆疊反向溢位。

此錯誤通常因為呼叫`long double`不傳回值的函式。 例如，下列會產生此錯誤時編譯並執行：

```
long double ld() {};
main ()
{
  ld();
}
```

程式結束，結束代碼 139。