---
title: 編譯器錯誤 C3454
ms.date: 11/04/2016
f1_keywords:
- C3454
helpviewer_keywords:
- C3454
ms.assetid: dc4e6d57-5b4d-4114-8d6f-22f9ae62925b
ms.openlocfilehash: 94c50ccd223567281e02c407e7ee22df75f859d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648795"
---
# <a name="compiler-error-c3454"></a>編譯器錯誤 C3454

類別宣告上不允許 [attribute]

必須定義類別，它才能是屬性。

如需詳細資訊，請參閱 [attribute](../../windows/attributes/attribute.md)。

## <a name="example"></a>範例

下列範例會產生 C3454。

```
// C3454.cpp
// compile with: /clr /c
using namespace System;

[attribute]   // C3454
ref class Attr1;

[attribute]   // OK
ref class Attr2 {};
```