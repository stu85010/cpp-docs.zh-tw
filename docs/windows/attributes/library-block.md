---
title: library_block （c + + COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 76e643cb45d8a87408015e6e0726e47d423147f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459913"
---
# <a name="libraryblock"></a>library_block

會建構的 IDL 程式庫區塊內。

## <a name="syntax"></a>語法

```cpp
[library_block]
```

## <a name="remarks"></a>備註

當您將內部的程式庫區塊的建構時，您會確定，它會傳遞至類型程式庫，而不論是否為參考。 根據預設，唯一的建構會修改所[coclass](coclass.md)， [dispinterface](dispinterface.md)，並[idl_module](idl-module.md)屬性會放在程式庫區塊。

## <a name="example"></a>範例

下列程式碼，在自訂介面放置的程式庫區塊內。

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|任何位置|
|**可重複**|否|
|**必要屬性**|無|
|**無效屬性**|無|

如需詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[編譯器屬性](compiler-attributes.md)<br/>
[獨立屬性](stand-alone-attributes.md)