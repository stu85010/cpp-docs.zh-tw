---
title: Makefile 前置處理中的運算式
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: 8d7b8cd489eabf239cbc993181142ca84431cd82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594866"
---
# <a name="expressions-in-makefile-preprocessing"></a>Makefile 前置處理中的運算式

**！如果**或 **！ELSE IF** `constantexpression`組成 （以十進位或 C 語言標記） 的整數常數、 字串常數或命令。 使用以群組運算式的括號。 運算式使用的 C 樣式帶正負號長整數算術，數字是範圍-2147483648 到 2147483647 的 32 位元二補數格式。

運算式可以使用採取行動的運算子，常數值、 命令、 字串、 巨集，以及檔案系統路徑的結束代碼。

## <a name="what-do-you-want-to-know-more-about"></a>您還想知道關於哪些方面的詳細資訊？

[Makefile 前置處理運算子](../build/makefile-preprocessing-operators.md)

[前置處理中執行程式](../build/executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>另請參閱

[Makefile 前置處理](../build/makefile-preprocessing.md)