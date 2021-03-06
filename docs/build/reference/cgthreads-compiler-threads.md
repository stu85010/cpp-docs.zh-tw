---
title: /CGTHREADS (編譯器執行緒)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: 1c459604d90b23953bbf3f250708c393fa78277d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495104"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (編譯器執行緒)

設定在指定連結時間程式碼產生時要用於最佳化和程式碼產生的 cl.exe 執行緒數目。

## <a name="syntax"></a>語法

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>引數

*數字*<br/>
cl.exe 要使用的執行緒數目上限，範圍在 1 到 8 之間。

## <a name="remarks"></a>備註

**/CGTHREADS**選項指定執行緒 cl.exe 使用的最大數目以平行方式的最佳化和程式碼產生階段的編譯時連結時間程式碼產生 ([/LTCG](../../build/reference/ltcg-link-time-code-generation.md)) 是指定此項目。 根據預設，cl.exe 使用四個執行緒，如同 **/CGTHREADS:4**所指定。 如果可以使用更多處理器核心，則較大的 `number` 值可以改善建置時間。

針對建置可以指定多個層級的平行處理原則。 Msbuild.exe 參數 **/maxcpucount**指定可以平行執行的 MSBuild 處理序數目。 [/MP （使用多個處理序建置）](../../build/reference/mp-build-with-multiple-processes.md)編譯器旗標會指定同時編譯原始程式檔的 cl.exe 處理序數目。 [/Cgthreads](../../build/reference/cgthreads-code-generation-threads.md)編譯器選項會指定每個 cl.exe 處理序所使用的執行緒數目。 由於處理器可同時執行的執行緒數目最多只能與處理器核心數目相同，因此同時針對所有這些選項指定較大的值不僅沒有什麼用處，反而可能適得其反。 如需如何平行建置專案的詳細資訊，請參閱[同時建置多個專案](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個連結器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 選取 **組態屬性**，**連結器**資料夾。

1. 選取 **命令列**屬性頁。

1. 修改**其他選項**屬性，以包括 **/CGTHREADS:**`number`，其中`number`是從 1 到 8 的值，然後選擇**確定**。

### <a name="to-set-this-linker-option-programmatically"></a>若要以程式設計方式設定這個連結器選項

- 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>另請參閱

[連結器選項](../../build/reference/linker-options.md)<br/>
[設定連結器選項](../../build/reference/setting-linker-options.md)