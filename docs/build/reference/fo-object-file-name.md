---
title: /Fo (目的檔名稱)
ms.date: 11/04/2016
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
ms.openlocfilehash: 19e84cbb1be53c8e1a7ae32b6ea2fc3ceeb2edae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640332"
---
# <a name="fo-object-file-name"></a>/Fo (目的檔名稱)

指定要使用的目的檔 (.obj) 名稱或目錄，而不使用預設值。

## <a name="syntax"></a>語法

```
/Fopathname
```

## <a name="remarks"></a>備註

如果您不使用此選項，物件檔案會使用原始程式檔和.obj 擴充功能的基底名稱。 您可以使用任何名稱和您想，延伸模組，但建議使用的慣例是使用。 obj

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 按一下 [C/C++]  資料夾。

1. 按一下 [輸出檔]  屬性頁。

1. 修改**目的檔名稱**屬性。  在開發環境中，物件檔案必須具有的延伸模組。 obj

### <a name="to-set-this-compiler-option-programmatically"></a>若要以程式方式設定這個編譯器選項

- 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>。

## <a name="example"></a>範例

下列命令列建立目的檔中現有的目錄，\OBJECT，磁碟機 b 上名為 THIS.obj

```
CL /FoB:\OBJECT\ THIS.C
```

## <a name="see-also"></a>另請參閱

[輸出檔 (/F) 選項](../../build/reference/output-file-f-options.md)<br/>
[編譯器選項](../../build/reference/compiler-options.md)<br/>
[設定編譯器選項](../../build/reference/setting-compiler-options.md)<br/>
[指定路徑名稱](../../build/reference/specifying-the-pathname.md)