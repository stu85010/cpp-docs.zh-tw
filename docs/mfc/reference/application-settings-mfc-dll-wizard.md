---
title: MFC DLL 精靈、應用程式設定
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: 66e7b907e3ed50c97e5cc864d51c621713cbf992
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455948"
---
# <a name="application-settings-mfc-dll-wizard"></a>MFC DLL 精靈、應用程式設定

使用 MFC DLL 精靈的這個頁面來設計和加入新的 MFC DLL 專案的基本功能。

## <a name="dll-type"></a>DLL 類型

選取您想要建立之 DLL 的類型。

- **MFC DLL 使用共用 MFC DLL**

   選取此選項即可連結到您的程式，做為共用的 DLL 的 MFC 程式庫。 使用此選項，您無法共用 MFC 物件會與您的 DLL 呼叫的應用程式。 您的程式在執行階段會呼叫 MFC 程式庫。 如果它使用 MFC 程式庫的多個執行檔所組成，此選項會降低您的程式的磁碟和記憶體需求。 Win32 與 MFC 程式可以在 DLL 中呼叫函式。 您必須轉散發 MFC DLL，這種類型的專案。

- **使用 MFC 的標準 MFC DLL 以靜態方式連結**

   選取此選項可在建置階段將程式以靜態方式連結至 MFC 程式庫。 Win32 與 MFC 程式可以在 DLL 中呼叫函式。 雖然此選項會增加程式的大小，則您不需要轉散發 MFC DLL，這種類型的專案。 您無法在您的 DLL 和呼叫的應用程式之間共用 MFC 物件。

- **MFC 擴充 DLL**

   如果您想要在執行階段，請呼叫 MFC 程式庫程式，而且您想要共用您的 DLL 和呼叫的應用程式之間的 MFC 物件，請選取此選項。 如果它由所有使用 MFC 程式庫的多個可執行檔所組成，此選項會降低您的程式、 磁碟和記憶體需求。 只有 MFC 程式可以在 DLL 中呼叫函式。 您必須轉散發 MFC DLL，這種類型的專案。

## <a name="additional-features"></a>其他功能

選取是否要在 MFC DLL 應該支援自動化，以及是否應支援 Windows 通訊端。

- **Automation**

   選取 **自動化**允許您的程式操作另一個程式中實作的物件。 選取**自動化**也會公開給其他自動化用戶端程式。 請參閱[自動化](../../mfc/automation.md)如需詳細資訊。

- **Windows 通訊端**

   選取此選項以指出您的程式，支援 Windows 通訊端。 Windows 通訊端，可讓您撰寫的程式可透過 TCP/IP 網路通訊。

   當您的 MFC DLL 與 Windows 通訊端會建立支援， [cwinapp:: Initinstance](../../mfc/reference/cwinapp-class.md#initinstance)初始化支援通訊端與 MFC 標頭檔 StdAfx.h 包含 AfxSock.h。

## <a name="see-also"></a>另請參閱

[MFC DLL 精靈](../../mfc/reference/mfc-dll-wizard.md)<br/>
[建立 MFC DLL 專案](../../mfc/reference/creating-an-mfc-dll-project.md)

