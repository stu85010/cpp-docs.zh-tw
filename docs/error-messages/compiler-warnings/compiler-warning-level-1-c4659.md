---
title: 編譯器警告 (層級 1) C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 2aef25e922d8f38ac7103b1b12ccb31c282f0403
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443458"
---
# <a name="compiler-warning-level-1-c4659"></a>編譯器警告 (層級 1) C4659

\#pragma 'pragma': 使用保留的區段 'segment' 有未定義的行為，請使用 #pragma 註解 (linker，...)

.Drectve 選項用來傳遞選項給連結器。 改為使用 pragma[註解](../../preprocessor/comment-c-cpp.md)傳遞連結器選項。

```
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```