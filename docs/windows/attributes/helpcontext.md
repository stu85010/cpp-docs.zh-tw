---
title: helpcontext （c + + COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 921e5370303cb62830ec281bcefd7c03331efaeb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552746"
---
# <a name="helpcontext"></a>helpcontext

指定的內容識別碼，可讓使用者檢視中此項目相關的資訊**協助**檔案。

## <a name="syntax"></a>語法

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>參數

*id*<br/>
說明主題的內容識別碼。 請參閱[HTML 說明： 程式的即時線上說明](../../mfc/html-help-context-sensitive-help-for-your-programs.md)如需有關內容識別碼。

## <a name="remarks"></a>備註

**Helpcontext** c + + 屬性具有相同的功能[helpcontext](/windows/desktop/Midl/helpcontext) MIDL 屬性。

## <a name="example"></a>範例

範例，請參閱[defaultvalue](defaultvalue.md)如需如何使用的範例**helpcontext**。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**介面**， **typedef**，**類別**、 方法、 屬性|
|**可重複**|否|
|**必要屬性**|無|
|**無效屬性**|無|

如需詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[IDL 屬性](idl-attributes.md)<br/>
[介面屬性](interface-attributes.md)<br/>
[類別屬性](class-attributes.md)<br/>
[方法屬性](method-attributes.md)<br/>
[Typedef、Enum、Union 和 Struct 屬性](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)