---
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 9367457a8e7f6be1f372244f8288a994eb777071
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613781"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

此選項會顯示 dll (兩者都以靜態方式連結並[延遲載入](../../build/reference/linker-support-for-delay-loaded-dlls.md))，從每個這些 Dll 的匯入至可執行檔或 DLL 和所有個別的匯入。

選擇性`file`規格可讓您指定只有該 DLL 的匯入將會顯示。 例如: 

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>備註

此選項所顯示的輸出會類似[/exports](../../build/reference/dash-exports.md)輸出。

只有[/HEADERS](../../build/reference/headers.md) DUMPBIN 選項只適用於所產生的檔案上[/GL](../../build/reference/gl-whole-program-optimization.md)編譯器選項。

## <a name="see-also"></a>另請參閱

[DUMPBIN 選項](../../build/reference/dumpbin-options.md)