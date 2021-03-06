---
title: 編譯器警告 (層級 2) C4275
ms.date: 11/04/2016
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 985a622e2c89306c453ae6c860d21e6265d0fff1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594320"
---
# <a name="compiler-warning-level-2-c4275"></a>編譯器警告 (層級 2) C4275

非 DLL 介面 classkey 'identifier' 做為基底 DLL 介面 classkey 'identifier'

匯出的類別衍生自未匯出的類別。

若要匯出的類別時，將資料損毀的可能性降至最低[__declspec （dllexport)](../../cpp/dllexport-dllimport.md)，請確認：

- 所有靜態資料是透過從 DLL 匯出的函式存取。

- 沒有內嵌的方法，您的類別可以修改靜態資料。

- 沒有內嵌的方法，您的類別使用的 CRT 函式或其他程式庫函式會使用靜態資料。

- 沒有內嵌的類別函式會使用 CRT 函式或其他程式庫的功能，比方說，您存取靜態資料。

- 您的類別沒有任何方法 (不管內嵌) 可以用來使用 EXE 和 DLL 中的具現化其中有靜態資料差異的類型。

您可以避免匯出類別所定義的 DLL，定義具有虛擬函式，類別和函式您可以呼叫來具現化和刪除的物件類型。  然後，您就可以再呼叫虛擬函式類型。

如果您從 c + + 標準程式庫中，編譯的偵錯版本的型別衍生，可以在 Visual c + + 中忽略 C4275 (**/MTd**) 和其中的編譯器錯誤訊息指的是 _Container_base。

```
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```