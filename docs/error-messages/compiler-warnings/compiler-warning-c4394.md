---
title: 編譯器警告 C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: 00c9e139e920473590389c05f076a7cd91a4fb8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548846"
---
# <a name="compiler-warning-c4394"></a>編譯器警告 C4394

'function': per-appdomain 符號不應該標示 __declspec （dllexport）

函式標示[appdomain](../../cpp/appdomain.md) `__declspec`修飾詞會編譯成 MSIL （不以原生），並匯出資料表 ([匯出](../../windows/export.md)`__declspec`修飾詞) 不支援 managed 函式。

您可以宣告 Managed 函式具有公用的存取範圍。 如需詳細資訊，請參閱 <<c0> [ 輸入可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)並[成員的可視性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility)。

C4394 一律發出為錯誤。  您可以關閉此警告，其中含有`#pragma warning`或 **/wd**; 請參閱[警告](../../preprocessor/warning.md)或[/w、 /W0、 /W1、 /W2、 / w3、 / w4、 /w1、 /w2、 / w3、 / w4、 /Wall、 /wd，/ /wo，我們 （警告層級）](../../build/reference/compiler-option-warning-level.md)如需詳細資訊。

## <a name="example"></a>範例

下列範例會產生 C4394。

```
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```