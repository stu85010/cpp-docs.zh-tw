---
title: "將 ATL 支援加入至 MFC 專案 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.adding.atl.mfc
dev_langs: C++
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: b5fe15d6-7752-4818-b9f9-62482ad35c95
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 92a4e9096cf72f6556c8ceb36e12cdff97139712
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="adding-atl-support-to-your-mfc-project"></a>將 ATL 支援加入至 MFC 專案
如果您已經建立以 MFC 為基礎的應用程式，然後您可以新增支援的 Active Template Library (ATL) 中輕鬆地執行將 ATL 支援加入至 MFC 專案精靈。  
  
> [!NOTE]
>  ATL 和 MFC 不通常支援 Visual Studio 的 Express 版本中。  
  
> [!NOTE]
>  這項支援只適用於簡單的 COM 物件加入至 MFC 可執行檔或 DLL 專案。 您可以將其他的 COM 物件 （包括 ActiveX 控制項） 加入 MFC 專案，但物件可能無法如預期般運作。  
  
### <a name="to-add-atl-support-to-your-mfc-project"></a>將 ATL 支援加入 MFC 專案  
  
1.  在 [方案總管] 中，以滑鼠右鍵按一下您要將 ATL 支援加入的專案。  
  
2.  在捷徑功能表，按一下 **新增**，然後按一下 **加入類別**。  
  
3.  選取**加入 ATL 支援加入至 MFC 專案**圖示。  
  
    > [!NOTE]
    >  此圖示位於 [ATL] 資料夾中**類別**窗格。  
  
4.  出現提示時，按一下**是**加入 ATL 支援。  
  
 如需有關如何將 ATL 支援加入 MFC 專案的程式碼的變更的詳細資訊，請參閱[詳細資料加入 ATL 支援的 ATL 精靈](../../mfc/reference/details-of-atl-support-added-by-the-atl-wizard.md)  
  
## <a name="see-also"></a>請參閱  
 [加入類別](../../ide/adding-a-class-visual-cpp.md)   
 [使用程式碼精靈加入功能](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [加入成員函式](../../ide/adding-a-member-function-visual-cpp.md)   
 [加入成員變數](../../ide/adding-a-member-variable-visual-cpp.md)   
 [覆寫虛擬函式](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 訊息處理常式](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [巡覽類別結構](../../ide/navigating-the-class-structure-visual-cpp.md)