---
title: 編譯器錯誤 C2355
ms.date: 11/04/2016
f1_keywords:
- C2355
helpviewer_keywords:
- C2355
ms.assetid: 0a947881-d61f-4f98-8409-32140f39500b
ms.openlocfilehash: 80871a73a7c3b4ad04b475539015f85d21ae88b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611272"
---
# <a name="compiler-error-c2355"></a>編譯器錯誤 C2355

'this'：只能在非靜態成員函式或非靜態資料成員初始設定式內部參考

`this` 指標只在非靜態成員函式或非靜態資料成員初始設定式內部才有效。 在類別宣告之外的成員函式定義的類別範圍不正確地限定時，就會產生這個錯誤。 在該類別中未宣告的函式中使用 `this` 指標時，也可能會發生錯誤。

若要修正此問題，請確定成員函式定義符合類別中的成員函式宣告，而且未宣告為靜態。 關於資料成員初始設定式，請確定資料成員未宣告為靜態。

下列範例會產生 C2355，並示範如何修正此問題：

```
// C2355.cpp
// compile with: /c
class MyClass {};
MyClass *p = this;   // C2355

// OK
class MyClass2 {
public:
   void Test() {
      MyClass2 *p = this;
   }
};
```