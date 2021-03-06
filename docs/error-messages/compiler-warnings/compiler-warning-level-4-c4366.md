---
title: 編譯器警告 (層級 4) C4366
ms.date: 11/04/2016
f1_keywords:
- C4366
helpviewer_keywords:
- C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
ms.openlocfilehash: 11fcb0070359201de39ca5f33c83d000e02f0835
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629062"
---
# <a name="compiler-warning-level-4-c4366"></a>編譯器警告 (層級 4) C4366

一元 'operator' 運算子的結果可能未對齊

如果因為封裝結構成員可能曾經是未對齊，編譯器會警告時，要將成員的位址指派給對齊的指標。 根據預設，會對齊所有指標。

若要解決 C4366，請變更結構的對齊方式或宣告指標[__unaligned](../../cpp/unaligned.md)關鍵字。

如需詳細資訊，請參閱 __unaligned 並[組件](../../preprocessor/pack.md)。

## <a name="example"></a>範例

下列範例會產生 C4366。

```
// C4366.cpp
// compile with: /W4 /c
// processor: IPF x64
#pragma pack(1)
struct X {
   short s1;
   int s2;
};

int main() {
   X x;
   short * ps1 = &x.s1;   // OK
   int * ps2 = &x.s2;   // C4366
}
```