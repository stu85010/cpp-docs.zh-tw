---
title: 巨集替換
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 8daaa55418839fa969cf3a31efa092fcf21487e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616082"
---
# <a name="macro-substitution"></a>巨集替換

當*macroname*叫用時，出現的每個*string1*在其定義中字串會取代*string2*。

## <a name="syntax"></a>語法

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>備註

巨集取代是區分大小寫，以及是常值;*string1*並*string2*無法叫用巨集。 替代不會修改原始定義。 您可以使用取代文字中任何預先定義的巨集，除了[ $$@ ](../build/filename-macros.md)。

沒有空格或定位點前面的冒號;任何冒號之後會被視為常值。 如果*string2*是 null，所有發生次數*string1*會刪除從巨集的定義字串。

## <a name="see-also"></a>另請參閱

[使用 NMAKE 巨集](../build/using-an-nmake-macro.md)