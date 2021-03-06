---
title: 一般 HTTP 用戶端應用程式中的步驟
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: a73d220f4ab7f58960ccfe4b09f98f0cd0956406
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630785"
---
# <a name="steps-in-a-typical-http-client-application"></a>一般 HTTP 用戶端應用程式中的步驟

下表顯示的步驟，您可能會執行一般的 HTTP 用戶端應用程式：

|您的目標|採取的動作|效果|
|---------------|----------------------|-------------|
|開始 HTTP 工作階段。|建立[CInternetSession](../mfc/reference/cinternetsession-class.md)物件。|初始化 WinInet 並連接至伺服器。|
|連接至 HTTP 伺服器。|使用[cinternetsession:: Gethttpconnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)。|傳回[CHttpConnection](../mfc/reference/chttpconnection-class.md)物件。|
|開啟 HTTP 要求。|使用[chttpconnection::](../mfc/reference/chttpconnection-class.md#openrequest)。|傳回[CHttpFile](../mfc/reference/chttpfile-class.md)物件。|
|傳送 HTTP 要求。|使用[CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders)並[CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest)。|尋找檔案。 如果找不到檔案則傳回 FALSE。|
|從檔案讀取。|使用[CHttpFile](../mfc/reference/chttpfile-class.md)。|讀取指定使用您所提供的緩衝區的位元組數目。|
|處理例外狀況。|使用[CInternetException](../mfc/reference/cinternetexception-class.md)類別。|處理所有通用網際網路例外狀況類型。|
|結束 HTTP 工作階段。|處置[CInternetSession](../mfc/reference/cinternetsession-class.md)物件。|自動清除開啟檔案控制代碼和連接。|

## <a name="see-also"></a>另請參閱

[Win32 網際網路延伸模組 (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[網際網路用戶端類別的必要條件](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[使用 MFC WinInet 類別建立網際網路用戶端應用程式](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
