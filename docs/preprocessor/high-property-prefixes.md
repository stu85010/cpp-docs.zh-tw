---
title: high_property_prefixes
ms.date: 10/18/2018
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: 130d19f275612e153955ae49f299fe2f36d098bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579808"
---
# <a name="highpropertyprefixes"></a>high_property_prefixes

**C + + 特定**

為三個屬性方法指定替代的前置詞。

## <a name="syntax"></a>語法

```
high_property_prefixes("GetPrefix","PutPrefix","PutRefPrefix")
```

### <a name="parameters"></a>參數

*GetPrefix*<br/>
若要使用的前置詞`propget`方法。

*PutPrefix*<br/>
若要使用的前置詞`propput`方法。

*PutRefPrefix*<br/>
若要使用的前置詞`propputref`方法。

## <a name="remarks"></a>備註

根據預設，高階錯誤處理`propget`， `propput`，並`propputref`方法會公開由成員函式名稱前置詞`Get`， `Put`，和`PutRef`分別。

**END c + + 特定的**

## <a name="see-also"></a>另請參閱

[#import 屬性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import 指示詞](../preprocessor/hash-import-directive-cpp.md)