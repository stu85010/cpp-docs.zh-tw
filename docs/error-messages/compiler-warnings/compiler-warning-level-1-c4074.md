---
title: 編譯器警告 （層級 1） C4074
ms.date: 11/04/2016
f1_keywords:
- C4074
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
ms.openlocfilehash: d9b0259e95198396d8c34ca43781045248e22ad9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665560"
---
# <a name="compiler-warning-level-1-c4074"></a>編譯器警告 （層級 1） C4074

初始設定式置於編譯器保留的初始化區域

編譯器的初始化區域，即可指定此種[#pragma init_seg](../../preprocessor/init-seg.md)，已保留給 Microsoft。 C 執行階段程式庫初始化之前，可能會執行此區域中的程式碼。

下列範例會產生 C4074:

```
// C4074.cpp
// compile with: /W1
#pragma init_seg( compiler )   // C4074

// try this line to resolve the warning
// #pragma init_seg(user)

int main() {
}
```