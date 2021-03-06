---
title: 建構輸入資料流物件
ms.date: 11/04/2016
helpviewer_keywords:
- input stream objects
ms.assetid: ab94866e-6ffe-4f15-b4db-0bd23e636075
ms.openlocfilehash: 89d681f1a092957bc966d2ec788a0f9aa2261ada
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543672"
---
# <a name="constructing-input-stream-objects"></a>建構輸入資料流物件

如果您只使用 `cin` 物件，就不需要建構輸入資料流。 如果您使用下列項目，就必須建構輸入資料流︰

- [輸入檔案資料流建構函式](#vclrfinputfilestreamconstructorsanchor8)

- [輸入字串資料流建構函式](#vclrfinputstringstreamconstructorsanchor9)

## <a name="vclrfinputfilestreamconstructorsanchor8"></a> 輸入檔案資料流建構函式

下列兩種方式可用來建立輸入檔案資料流：

- 使用**void**引數建構函式，然後呼叫`open`成員函式：

   ```cpp
   ifstream myFile; // On the stack
   myFile.open("filename");

   ifstream* pmyFile = new ifstream; // On the heap
   pmyFile->open("filename");
   ```

- 在建構函式引動過程中，指定檔案名稱和模式旗標，以在建構程序期間開啟檔案：

   ```cpp
   ifstream myFile("filename");
   ```

## <a name="vclrfinputstringstreamconstructorsanchor9"></a> 輸入字串資料流建構函式

輸入字串資料流建構函式需要您已預先配置並初始化的儲存體位址：

```cpp
string s("123.45");

double amt;
istringstream myString(s);

//istringstream myString("123.45") also works
myString>> amt; // amt contains 123.45
```

## <a name="see-also"></a>另請參閱

[輸入資料流](../standard-library/input-streams.md)<br/>
