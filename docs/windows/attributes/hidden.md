---
title: 隱藏 （c + + COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: c1d8c8d894ed9a54c0dd3af775d6fbfda0385906
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597609"
---
# <a name="hidden"></a>隱藏

表示項目存在，但不是會顯示在使用者導向的瀏覽器中。

## <a name="syntax"></a>語法

```cpp
[hidden]
```

## <a name="remarks"></a>備註

**隱藏**c + + 屬性具有相同的功能[隱藏](/windows/desktop/Midl/hidden)MIDL 屬性。

## <a name="example"></a>範例

範例，請參閱[可繫結](bindable.md)如需如何使用的範例**隱藏**。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**介面**，**類別**，**結構**、 方法、 屬性|
|**可重複**|否|
|**必要屬性**|**coclass** (當套用至**類別**或是**結構**)|
|**無效屬性**|無|

如需詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[IDL 屬性](idl-attributes.md)<br/>
[介面屬性](interface-attributes.md)<br/>
[類別屬性](class-attributes.md)<br/>
[方法屬性](method-attributes.md)