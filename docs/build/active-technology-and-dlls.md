---
title: Active 技術和 DLL
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: 270c64df9af792a73acf1ad408aca02e7fadc30f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535807"
---
# <a name="active-technology-and-dlls"></a>Active 技術和 DLL

Active 技術可讓物件伺服程式完全實作於 DLL 內。 此類型的伺服器稱為同處理序伺服器。 MFC 不完全支援同處理序伺服器的視覺化編輯的所有功能主要是因為 Active 技術不提供伺服器連結到容器的主要訊息迴圈的方式。 MFC 會需要存取容器應用程式的訊息迴圈來處理快速鍵和閒置時間處理。

如果您正在撰寫 Automation 伺服程式，而且您的伺服器有沒有使用者介面，您可以讓 server 同處理序伺服器，並將它完全放入 DLL。

## <a name="what-do-you-want-to-know-more-about"></a>您還想知道關於哪些方面的詳細資訊？

- [Automation 伺服程式](../mfc/automation-servers.md)

## <a name="see-also"></a>另請參閱

[Visual C++ 中的 DLL](../build/dlls-in-visual-cpp.md)