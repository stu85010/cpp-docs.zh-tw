---
title: 定義巨集的位置
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 130863f8c5640a0c4915734732d93fc00d3d6479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656244"
---
# <a name="where-to-define-macros"></a>定義巨集的位置

在命令列、 指令檔、 makefile 或 Tools.ini 檔案定義巨集。

在以 makefile 或 Tools.ini 檔案中，每個巨集的定義必須出現在不同的行，而且開頭空格或定位字元。會忽略空格或等號前後的索引標籤。 所有[個字元的字串](../build/defining-an-nmake-macro.md)是常值，包括周圍的引號和內嵌的空格。

在命令列或指令檔中，空格和定位點分隔的引數，並不能用在等號。 如果`string`有內嵌空格或定位點，以雙引號括住字串本身或整個巨集 ("")。

## <a name="see-also"></a>另請參閱

[定義 NMAKE 巨集](../build/defining-an-nmake-macro.md)