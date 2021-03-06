---
title: ATL 預先定義的符號
ms.date: 11/04/2016
helpviewer_keywords:
- symbols [C++], ATL predefined
- ATL symbols
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
ms.openlocfilehash: 37d24dcfb65566b2b13c8b1ba8c826ec68271477
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654398"
---
# <a name="atl-predefined-symbols"></a>ATL 預先定義的符號

ATL 標頭檔中定義這些符號，但是它們可以支援標準的 Windows 應用程式函數和動作。 這些符號主要用於與對話方塊。 當您正在使用對話方塊和控制項中[對話方塊編輯器](../windows/dialog-editor.md)，這些符號會出現在**屬性**通用控制項相關聯的視窗。 比方說，如果您的對話方塊中有**取消**按鈕，命令將會是相關聯的符號 IDCANCEL 中[屬性 視窗](/visualstudio/ide/reference/properties-window)。

|||
|-|-|
|IDABORT|控制： 對話方塊的 [中止] 按鈕|
|IDC_STATIC|控制： 靜態控制項|
|IDCANCEL|控制： 對話方塊的 [取消] 按鈕|
|IDIGNORE|控制： 對話方塊的 [忽略] 按鈕|
|IDNO|控制： 對話方塊的 [無] 按鈕|
|IDOK|控制項： 對話方塊 [確定] 按鈕|
|IDR_ACCELERATOR1|資源： 快速鍵對應表|
|IDRETRY|控制： 對話方塊的 [重試] 按鈕|
|IDS_PROJNAME|字串： 目前的應用程式名稱|
|IDYES|控制： 對話方塊 [是] 按鈕|

## <a name="requirements"></a>需求

ATL

## <a name="see-also"></a>另請參閱

[預先定義的符號識別碼](../windows/predefined-symbol-ids.md)<br/>
[符號：資源識別項](../windows/symbols-resource-identifiers.md)