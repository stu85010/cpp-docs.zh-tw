---
title: 定義對話方塊控制項 （c + +） 的成員變數
ms.date: 11/04/2016
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
ms.openlocfilehash: 56a7d01d26656c8cf9def3bf09e3ccb18fb436fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449448"
---
# <a name="defining-member-variables-for-dialog-controls-c"></a>定義對話方塊控制項 （c + +） 的成員變數

若要定義任何對話方塊控制項 (按鈕除外) 的成員變數，您可以使用下列方法。

> [!NOTE]
> 本文只適用於 MFC 專案內的對話方塊控制項。 ATL 專案應使用**新的 Windows 訊息和事件處理常式** 對話方塊。

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>定義對話方塊控制項的成員變數 (非按鈕)

1. 在 [對話方塊編輯器](../windows/dialog-editor.md)，在選取的控制項。

2. 同時按下**Ctrl**機碼，請按兩下對話方塊控制項。

   [加入成員變數精靈](../ide/add-member-variable-wizard.md)隨即出現。

3. 輸入中的相關資訊**加入成員變數**精靈。 如需詳細資訊，請參閱 <<c0> [ 對話資料交換](../mfc/dialog-data-exchange.md)。

4. 按一下  **確定**以返回**對話方塊**編輯器。

   > [!TIP]
   > 若要從任何對話方塊控制項跳至其現有的處理常式，請按兩下控制項。

您也可以使用**成員變數**索引標籤中**MFC 類別精靈**新增成員變數，指定的類別，並檢視這些已定義。

## <a name="requirements"></a>需求

MFC

## <a name="see-also"></a>另請參閱

[將訊息對應到函式](../mfc/reference/mapping-messages-to-functions.md)<br/>
[使用程式碼精靈新增功能](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[MFC 類別精靈](../mfc/reference/mfc-class-wizard.md)<br/>
[新增類別](../ide/adding-a-class-visual-cpp.md)<br/>
[新增成員函式](../ide/adding-a-member-function-visual-cpp.md)<br/>
[新增成員變數](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[覆寫虛擬函式](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC 訊息處理常式](../mfc/reference/adding-an-mfc-message-handler.md)