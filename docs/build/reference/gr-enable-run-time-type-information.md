---
title: /GR (啟用執行階段類型資訊)
ms.date: 11/04/2016
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: b0b618b1018912f1cf0172fc461ac2849c4faf5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579344"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (啟用執行階段類型資訊)

加入程式碼以在執行階段檢查物件類型。

## <a name="syntax"></a>語法

```
/GR[-]
```

## <a name="remarks"></a>備註

當 **/GR**時，編譯器就會定義`_CPPRTTI`前置處理器巨集。 根據預設， **/GR**上。 **/GR-** 停用執行階段類型資訊。

使用 **/GR**如果編譯器無法以靜態方式解析您的程式碼中的物件類型。 您通常需要 **/GR**選項時您的程式碼會使用[dynamic_cast 運算子](../../cpp/dynamic-cast-operator.md)或是[typeid](../../cpp/typeid-operator.md)。 不過， **/GR**會增加您的映像的.rdata 區段的大小。 如果您的程式碼不會使用**dynamic_cast**或是**typeid**， **/GR-** 可能會產生較小的影像。

如需有關執行階段類型檢查的詳細資訊，請參閱 <<c0> [ 執行階段類型資訊](../../cpp/run-time-type-information.md)中*c + + 語言參考*。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 按一下 [C/C++]  資料夾。

1. 按一下 **語言**屬性頁。

1. 修改**啟用執行階段類型資訊**屬性。

### <a name="to-set-this-compiler-option-programmatically"></a>若要以程式方式設定這個編譯器選項

- 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>。

## <a name="see-also"></a>另請參閱

[編譯器選項](../../build/reference/compiler-options.md)<br/>
[設定編譯器選項](../../build/reference/setting-compiler-options.md)