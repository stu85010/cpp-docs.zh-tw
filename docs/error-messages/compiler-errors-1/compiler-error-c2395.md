---
title: 編譯器錯誤 C2395
ms.date: 11/04/2016
f1_keywords:
- C2395
helpviewer_keywords:
- C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
ms.openlocfilehash: dd3bd922e2bfa61da2da87d368bb4b28237161f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599832"
---
# <a name="compiler-error-c2395"></a>編譯器錯誤 C2395

'your_type::operator'op'' : CLR or WinRT 運算子無效。 至少一個參數必須是下列類型：'T'、'T%'、'T&'、'T^'、'T^%'、'T^&'，其中 T = 'your_type'

Windows 執行階段或 Managed 類型中的運算子沒有至少一個參數，其類型與運算子傳回值的類型相同。

下列範例會產生 C2395，並示範如何修正此問題：

```
// C2395.cpp
// compile with: /clr /c
value struct V {
   static V operator *(int i, char c);   // C2395

   // OK
   static V operator *(V v, char c);
   // or
   static V operator *(int i, V& rv);
};
```