---
title: 編譯器錯誤 C3080
ms.date: 11/04/2016
f1_keywords:
- C3080
helpviewer_keywords:
- C3080
ms.assetid: ff62a3f7-9b3b-44bd-b8d9-f3a8e5354560
ms.openlocfilehash: 5b610d54331349c53ff01f5c09bb53ff52216c26
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455818"
---
# <a name="compiler-error-c3080"></a>編譯器錯誤 C3080

'finalizer_function': 完成項不能有儲存類別規範

如需詳細資訊，請參閱 <<c0> [ 解構函式和完成項中如何： 定義和使用類別和結構 (C + + /cli CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)。

## <a name="example"></a>範例

下列範例會產生 C3080。

```
// C3080.cpp
// compile with: /clr /c
ref struct rs {
protected:
   static !rs(){}   // C3080
   !rs(){}   // OK
};
```