---
title: 加入資源對話方塊 （c + +）
ms.date: 11/04/2016
f1_keywords:
- vc.editors.insertresource
helpviewer_keywords:
- resources [C++], adding
- Add Resource dialog box [C++]
ms.assetid: e9fb6967-738f-47e8-ab58-728cf35b3af0
ms.openlocfilehash: b20ec4a076e276c905a96c2deabd619ea10517f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503113"
---
# <a name="add-resource-dialog-box"></a>加入資源對話方塊

使用這個對話方塊將資源加入至 C++ Windows 桌面應用程式專案。

> [!NOTE]
> 這項資訊不適用於通用 Windows 平台應用程式中的資源。 如有關的詳細資訊，請參閱 <<c0> [ 應用程式資源和資源管理系統](/windows/uwp/app-resources/)。

### <a name="resource-type"></a>資源類型

指定您想要建立的資源種類。

您可以展開資料指標和對話方塊資源類別來顯示其他資源。 這些資源位於 Visual Studio...\Microsoft `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct。 如果您加入.rct 檔案，您必須將它們放在這個目錄中，或者您必須指定[include 路徑](../windows/how-to-specify-include-directories-for-resources.md)它們。 如此，那些檔案中的資源將會顯示在適當分類底下的第二層。 您可以加入的 .rct 檔案數目沒有任何預設限制。

樹狀目錄控制項最上層所顯示的資源，是 Visual Studio 所提供的預設資源。

### <a name="new"></a>新增

建立資源，根據您在 [選取的型別**資源類型**] 方塊中。 資源會在適當的編輯器中開啟。 例如，如果您建立對話方塊資源時，它會在中開啟[對話方塊編輯器](../windows/dialog-editor.md)。

### <a name="import"></a>匯入

會開啟**匯入**對話方塊中，在其中您可以瀏覽至資源您想要匯入至您目前的專案。 您可以匯入點陣圖、圖示、游標、HTML 資源檔、音效 (.WAV) 資源檔或自訂資源檔。

### <a name="custom"></a>自訂

會開啟[新的自訂資源對話方塊](../windows/new-custom-resource-dialog-box.md)中您可以建立自訂的資源。 自訂資源只能在二進位編輯器中編輯。

## <a name="requirements"></a>需求

無

## <a name="see-also"></a>另請參閱

[如何：建立資源](../windows/how-to-create-a-resource.md)