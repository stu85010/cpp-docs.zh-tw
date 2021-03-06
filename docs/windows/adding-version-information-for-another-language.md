---
title: 新增另一個語言 （c + +） 的版本資訊
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version
helpviewer_keywords:
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
ms.assetid: 17f6273c-e1cc-441a-a3d8-f564341cbf20
ms.openlocfilehash: 6d79fb575817d5ba743e4efc460154eb03dca4f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534585"
---
# <a name="adding-version-information-for-another-language-c"></a>新增另一個語言 （c + +） 的版本資訊

### <a name="to-add-version-information-for-another-language-new-info-block"></a>加入另一種語言的版本資訊 (新增資訊區塊)

1. 按兩下版本資訊資源，在 [資源檢視](../windows/resource-view-window.md)中開啟它。

   > [!NOTE]
   > 如果您的專案尚未包含 .rc 檔，請參閱 [建立新的資源指令碼檔](../windows/how-to-create-a-resource-script-file.md)。

2. 以滑鼠右鍵在版本資訊表內按一下，然後從快顯功能表中選擇 [新增版本資訊區塊]  。

   這個命令會將額外的資訊區塊加入目前的版本資訊資源中，並在 [[屬性] 視窗](/visualstudio/ide/reference/properties-window)中開啟其對應的屬性。

3. 在 [屬性]  視窗中，為新的區塊選擇適當的語言和字元集。

如需將資源加入 managed 專案的詳細資訊，請參閱[Resources in Desktop Apps](/dotnet/framework/resources/index)中 *.NET Framework 開發人員指南*。 如需手動將資源檔加入 managed 專案、 存取資源、 顯示靜態資源及指派資源字串給屬性的資訊，請參閱[建立桌面應用程式的資源檔](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和當地語系化的受管理的應用程式中的資源上的資訊，請參閱[全球化和當地語系化.NET Framework 應用程式](/dotnet/standard/globalization-localization/index)。

## <a name="requirements"></a>需求

Win32

## <a name="see-also"></a>另請參閱

[版本資訊編輯器](../windows/version-information-editor.md)<br/>
[版本資訊 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)