---
title: ref new 和 gcnew (C + + /cli 和 C + + /CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
ms.openlocfilehash: dd78bcb7283cb08f4971192274686710fe22181f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641764"
---
# <a name="ref-new-gcnew--ccli-and-ccx"></a>ref new 和 gcnew (C + + /cli 和 C + + /CX)

**新的 ref**彙總關鍵字，其配置當物件變成無法存取，並傳回控制代碼回收的類型的執行個體 ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) 所配置物件。

## <a name="all-runtimes"></a>所有執行階段

記憶體配置類型的執行個體**ref 新**會自動取消配置。

A**新的 ref**作業會擲回`OutOfMemoryException`如果無法配置記憶體。

如需有關如何配置和解除配置記憶體給原生 c + + 類型的詳細資訊，請參閱 <<c0> [ 新和 delete 運算子](../cpp/new-and-delete-operators.md)。

## <a name="windows-runtime"></a>Windows 執行階段

使用**ref 新**為 Windows 執行階段物件您想要自動管理其存留期間配置記憶體。 當其參考計數歸零時 (參考的最後一個複本已離開範圍之後發生)，會自動取消配置物件。 如需詳細資訊，請參閱 < [Ref 類別與結構](../cppcx/ref-classes-and-structs-c-cx.md)。

### <a name="requirements"></a>需求

編譯器選項：`/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Managed 類型 （參考或實值類型） 的記憶體配置**gcnew**，並解除配置使用記憶體回收。

### <a name="requirements"></a>需求

編譯器選項：`/clr`

### <a name="examples"></a>範例

下列範例會使用**gcnew**配置訊息物件。

```cpp
// mcppv2_gcnew_1.cpp
// compile with: /clr
ref struct Message {
   System::String^ sender;
   System::String^ receiver;
   System::String^ data;
};

int main() {
   Message^ h_Message  = gcnew Message;
  //...
}
```

下列範例會使用**gcnew**來建立使用類似參考類型的 boxed 實的值類型。

```cpp
// example2.cpp : main project file.
// compile with /clr
using namespace System;
value class Boxed {
    public:
        int i;
};
int main()
{
    Boxed^ y = gcnew Boxed;
    y->i = 32;
    Console::WriteLine(y->i);
    return 0;
}
```

```Output
32
```

## <a name="see-also"></a>另請參閱

[適用於.NET 和 UWP 的元件延伸模組](../windows/component-extensions-for-runtime-platforms.md)