---
title: /Zs (僅檢查語法)
ms.date: 11/04/2016
f1_keywords:
- /zs
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
ms.openlocfilehash: 5cdd52ba6c221cbfa1526c19f3d6cfaf26a96e51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429788"
---
# <a name="zs-syntax-check-only"></a>/Zs (僅檢查語法)

會告訴編譯器檢查命令列上的來源檔案的語法。

## <a name="syntax"></a>語法

```
/Zs
```

## <a name="remarks"></a>備註

使用此選項時，會建立沒有任何輸出檔案，以及錯誤訊息會寫入至標準輸出。

**/Zs**選項讓您快速找出並解決語法錯誤，才能在編譯和連結的原始程式檔。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 按一下 [C/C++]  資料夾。

1. 按一下 [命令列]  屬性頁。

1. 在 [其他選項]  方塊中，輸入編譯器選項。

### <a name="to-set-this-compiler-option-programmatically"></a>若要以程式方式設定這個編譯器選項

- 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>。

## <a name="see-also"></a>另請參閱

[編譯器選項](../../build/reference/compiler-options.md)<br/>
[設定編譯器選項](../../build/reference/setting-compiler-options.md)