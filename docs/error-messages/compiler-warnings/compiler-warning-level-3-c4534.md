---
title: 編譯器警告 (層級 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: a2af04502082f7fb30d59af5e6434161227c6d30
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437247"
---
# <a name="compiler-warning-level-3-c4534"></a>編譯器警告 (層級 3) C4534

'constructor' 將不會類別 'class'，因為預設引數的預設建構函式

未受管理的類別可以有預設值的參數的建構函式，編譯器會將它作為預設建構函式。 使用標示的類別`value`關鍵字不會將建構函式使用預設值用於其參數為預設建構函式。

如需詳細資訊，請參閱 <<c0> [ 類別和結構](../../windows/classes-and-structs-cpp-component-extensions.md)。

下列範例會產生 C4534:

```
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```