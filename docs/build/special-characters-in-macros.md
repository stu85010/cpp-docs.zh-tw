---
title: 巨集中的特殊字元
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: bc40a4d2c3197f0cc85099d0a89ab511f3acf81c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555086"
---
# <a name="special-characters-in-macros"></a>巨集中的特殊字元

數字符號 （#） 之後定義所指定的註解。 若要指定常值的數字符號在巨集中，使用插入號 (^)，如 ^ #。

貨幣符號 （$） 指定的巨集引動過程。 若要指定常值 $，使用 $$。

若要擴充至新行的定義，在行尾加上反斜線 (\\)。 叫用巨集時，反斜線加上新行字元取代空格。 若要指定的行結尾的常值反斜線，前面加上插入號 (^)，或地在後面加上註解規範 （#）。

若要指定常值的新行字元，行尾處使用插入號 (^)，如：

```
CMDS = cls^
dir
```

## <a name="see-also"></a>另請參閱

[定義 NMAKE 巨集](../build/defining-an-nmake-macro.md)