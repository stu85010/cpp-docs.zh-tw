---
title: 編譯器錯誤 C2812
ms.date: 11/04/2016
f1_keywords:
- C2812
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
ms.openlocfilehash: 88b071f38cf41db9c929d25ffd526b3f2b7ca468
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531816"
---
# <a name="compiler-error-c2812"></a>編譯器錯誤 C2812

> \#匯入不支援使用 /clr: pure 和 /clr: safe

## <a name="remarks"></a>備註

**/Clr: pure**並 **/clr: safe**編譯器選項是在 Visual Studio 2015 中已被取代，而且不支援的 Visual Studio 2017 中。

[#import 指示詞](../../preprocessor/hash-import-directive-cpp.md)不支援 **/clr: pure**並 **/clr: safe**因為`#import`需要原生編譯器支援程式庫使用。

## <a name="example"></a>範例

下列範例會產生 C2812。

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```