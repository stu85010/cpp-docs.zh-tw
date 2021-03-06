---
title: 編譯器警告 (層級 1) C4730
ms.date: 11/04/2016
f1_keywords:
- C4730
helpviewer_keywords:
- C4730
ms.assetid: 11303e3f-162b-4b19-970a-479686123a68
ms.openlocfilehash: 4da60194deaeac3c79f8c3e9be3bd87d91bc7ca2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487031"
---
# <a name="compiler-warning-level-1-c4730"></a>編譯器警告 (層級 1) C4730

'main': 混合 _m64 和浮點運算式可能會導致不正確的程式碼

函式使用[__m64](../../cpp/m64.md)並**float**/**double**型別。 因為 MMX 和浮點數暫存器共用相同的實體暫存器空間 （不能同時使用），使用`__m64`並**浮點數**/**double**中相同的型別函式可能會導致資料損毀，可能會造成例外狀況。

若要安全地使用`__m64`型別和浮點類型相同的函式中，使用其中一種類型的每個指示應以 **_m_empty （)** （供 MMX 使用) 或 **_m_femms （)** （供 3DNow ！)內建函式。

下列範例會產生 C4730:

```
// C4730.cpp
// compile with: /W1
// processor: x86
#include "mmintrin.h"

void func(double)
{
}

int main(__m64 a, __m64 b)
{
   __m64 m;
   double f;
   f = 1.0;
   m = _m_paddb(a, b);
   // uncomment the next line to resolve C4730
   // _m_empty();
   func(f * 3.0);   // C4730
}
```