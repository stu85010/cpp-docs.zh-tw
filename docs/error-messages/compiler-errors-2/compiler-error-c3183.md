---
title: 編譯器錯誤 C3183
ms.date: 11/04/2016
f1_keywords:
- C3183
helpviewer_keywords:
- C3183
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
ms.openlocfilehash: 232e9999bc31ac3e01833e7982acfb03e9d0afaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497224"
---
# <a name="compiler-error-c3183"></a>編譯器錯誤 C3183

無法在 Managed 或 WinRT 類型 'type' 內部定義未命名的類別、結構或等位

內嵌在 Managed 或 WinRT 類型中的類型必須命名。

下列範例會產生 C3183：

```
// C3183a.cpp
// compile with: /clr /c
ref class Test
{
   ref class
   {  // C3183, delete class or name it
      int a;
      int b;
   };
};
```
