---
title: "CMFCCustomColorsPropertyPage 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
dev_langs: C++
helpviewer_keywords: CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7dac4260c69e4d2bbf9c74965e73f6961dd6ad6b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage 類別
表示可以在色彩對話方塊中選取自訂色彩 屬性頁面。  
  
## <a name="syntax"></a>語法  
  
```  
class CMFCCustomColorsPropertyPage : public CPropertyPage  
```  
  
## <a name="members"></a>成員  
  
### <a name="public-constructors"></a>公用建構函式  
  
|||  
|-|-|  
|名稱|描述|  
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|預設建構函式。|  
  
### <a name="public-methods"></a>公用方法  
  
|||  
|-|-|  
|名稱|描述|  
|`CMFCCustomColorsPropertyPage::CreateObject`|由建立此類別類型的動態執行個體架構所使用。|  
|`CMFCCustomColorsPropertyPage::GetThisClass`|由架構用來取得指向[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)與此類別類型相關聯的物件。|  
|[CMFCCustomColorsPropertyPage::Setup](#setup)|設定色彩元件的屬性頁。|  
  
### <a name="remarks"></a>備註  
 `CMFCColorDialog`類別會使用這個類別顯示 [自訂色彩] 屬性頁。 如需有關`CMFCColorDialog`，請參閱[CMFCColorDialog 類別](../../mfc/reference/cmfccolordialog-class.md)。  
  
## <a name="example"></a>範例  
 下列範例示範如何建構`CMFCCustomColorsPropertyPage`物件，並設定屬性頁上的色彩元件。  
  
 [!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CPropertyPage](../../mfc/reference/cpropertypage-class.md)  
  
 [CMFCCustomColorsPropertyPage](../../mfc/reference/cmfccustomcolorspropertypage-class.md)  
  
## <a name="requirements"></a>需求  
 **標頭：** afxcustomcolorspropertypage.h  
  
##  <a name="setup"></a>CMFCCustomColorsPropertyPage::Setup  
 設定色彩元件的屬性頁。  
  
```  
void Setup(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>參數  
  
|||  
|-|-|  
|參數|描述|  
|[輸入] `R`|紅元件的 RGB 值。|  
|[輸入] `G`|綠元件的 RGB 值。|  
|[輸入] `B`|藍色元件的 RGB 值。|  
  
### <a name="remarks"></a>備註  
 這個方法會更新目前的 RGB 和相關聯的 HLS （色調、 亮度及飽和度） 色彩值的屬性頁。 [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo)架構初始化色彩 對話方塊，或在使用者按下滑鼠左的按鈕時，方法會呼叫這個方法。 如需有關`CMFCColorDialog`，請參閱[CMFCColorDialog 類別](../../mfc/reference/cmfccolordialog-class.md)。  
  
## <a name="see-also"></a>請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [類別](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog 類別](../../mfc/reference/cmfccolordialog-class.md)   
 [CMFCStandardColorsPropertyPage 類別](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)