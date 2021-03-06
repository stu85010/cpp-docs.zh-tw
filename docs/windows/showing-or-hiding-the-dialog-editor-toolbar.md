---
title: 顯示或隱藏對話方塊編輯器工具列 （c + +）
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], showing or hiding Dialog editor toolbar
- toolbars [C++], showing
- toolbars [C++], hiding
- Dialog Editor [C++], showing or hiding toolbar
ms.assetid: 93c255e1-90eb-48b6-8602-450acda75bed
ms.openlocfilehash: e025f560a47f85d17b8c56a4db19f322069d33ef
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631084"
---
# <a name="showing-or-hiding-the-dialog-editor-toolbar-c"></a>顯示或隱藏對話方塊編輯器工具列 （c + +）

當您開啟** 對話方塊**在 c + + 專案中，編輯器**對話方塊編輯器**工具列會自動出現在您的解決方案的頂端。

### <a name="dialog-editor-toolbar"></a>對話方塊編輯器工具列

|圖示|意義|圖示|意義|
|----------|-------------|----------|-------------|
|![測試對話方塊 按鈕](../mfc/media/vcdialogeditortestdialog.png "vcDialogEditorTestDialog")|文字方塊|![水平均等陳列 按鈕](../mfc/media/vcdialogeditoracross.png "vcDialogEditorAcross")|橫向|
|![將按鈕靠左對齊](../mfc/media/vcdialogeditoralignlefts.png "vcDialogEditorAlignLefts")|對齊主控項的左緣|![垂直均等陳列 按鈕](../mfc/media/vcdialogeditordown.png "vcDialogEditorDown")|下移|
|![將權限按鈕對齊](../mfc/media/vcdialogeditoralignrights.png "vcDialogEditorAlignRights")|對齊主控項的右緣|![讓相同寬度 按鈕](../mfc/media/vcdialogeditorsamewidth.png "vcDialogEditorSameWidth")|設定成相同寬度|
|![將頂端的按鈕對齊](../mfc/media/vcdialogeditoraligntops.png "vcDialogEditorAlignTops")|對齊主控項的上緣|![讓相同高度 按鈕](../mfc/media/vcdialogeditormakesameheight.png "vcDialogEditorMakeSameHeight")|設定成相同高度|
|![靠下對齊按鈕](../mfc/media/vcdialogeditoralignbottoms.png "vcDialogEditorAlignBottoms")|靠下對齊|![讓相同的大小 按鈕](../mfc/media/vcdialogeditorsamesize.png "vcDialogEditorSameSize")|設定成相同大小|
|![垂直置中 按鈕](../mfc/media/vcdialogeditorvertical.png "vcDialogEditorVertical")|垂直|![切換格線 按鈕](../mfc/media/vcdialogeditortogglegrid.png "vcDialogEditorToggleGrid")|切換格線|
|![水平置中 按鈕](../mfc/media/vcdialogeditorhorizontal.png "vcDialogEditorHorizontal")|水平|![切換輔助線 按鈕](../mfc/media/vcdialogeditortoggleguides.png "vcDialogEditorToggleGuides")|切換輔助線|

**對話方塊編輯器**工具列包含用來排列控制項上的對話方塊中，例如大小和對齊方式的版面配置的按鈕。 **對話方塊編輯器**工具列按鈕上對應至命令**格式**功能表。 如需詳細資訊，請參閱 < [ 對話方塊編輯器的快速鍵](../windows/accelerator-keys-for-the-dialog-editor.md)。

如果您正在進行** 對話方塊**編輯器中，您可以切換顯示**對話方塊編輯器**選取從清單中的可用工具列和視窗的工具列。

### <a name="to-show-or-hide-the-dialog-editor-toolbar"></a>若要顯示或隱藏對話方塊編輯器工具列

1. 在上**檢視**功能表上，按一下**工具列**然後選擇**對話方塊編輯器**從子功能表。

   > [!NOTE]
   > **對話方塊編輯器**工具列會顯示根據預設，當您在對話方塊編輯器中開啟對話方塊資源; 不過，如果您明確地關閉工具列，您必須叫用它的下次您開啟對話方塊資源。

如需將資源加入 managed 專案的詳細資訊，請參閱[Resources in Desktop Apps](/dotnet/framework/resources/index)中 *.NET Framework 開發人員指南*。 如需手動將資源檔加入 managed 專案、 存取資源、 顯示靜態資源及指派資源字串給屬性的資訊，請參閱[建立桌面應用程式的資源檔](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和當地語系化的受管理的應用程式中的資源上的資訊，請參閱[全球化和當地語系化.NET Framework 應用程式](/dotnet/standard/globalization-localization/index)。

## <a name="requirements"></a>需求

Win32

## <a name="see-also"></a>另請參閱

[對話方塊上控制項的排列方式](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[如何：建立資源](../windows/how-to-create-a-resource.md)<br/>
[資源檔](../windows/resource-files-visual-studio.md)<br/>
[對話方塊編輯器](../windows/dialog-editor.md)