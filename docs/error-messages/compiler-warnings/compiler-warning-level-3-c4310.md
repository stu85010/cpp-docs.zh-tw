---
title: 編譯器警告 (層級 3) C4310
ms.date: 11/04/2016
f1_keywords:
- C4310
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
ms.openlocfilehash: b8d011d0e41c7d3fe6de7468d098ddd08f09565c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481064"
---
# <a name="compiler-warning-level-3-c4310"></a>編譯器警告 (層級 3) C4310

轉換截斷常數值

常數值會轉換成較小的類型。 編譯器會執行轉換，會截斷資料。 下列範例會產生 C4310:

```
// C4310.cpp
// compile with: /W4
int main() {
   long int a;
   a = (char) 128;   // C4310, use value 0-127 to resolve
}
```