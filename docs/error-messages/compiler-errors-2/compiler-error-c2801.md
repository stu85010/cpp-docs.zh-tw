---
title: 編譯器錯誤 C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 44f7988f9fedb882972b2823f2fe70d9512d4e87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484782"
---
# <a name="compiler-error-c2801"></a>編譯器錯誤 C2801

'operator operator' 必須是非靜態成員

下列運算子可以多載只做為非靜態成員：

- 指派 `=`

- 類別成員存取 `->`

- Subscripting `[]`

- 函式呼叫 `()`

可能的 C2801 原因：

- 多載的運算子不是類別、 結構或等位成員。

- 宣告多載的運算子`static`。

- 下列範例會產生 C2801:

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```