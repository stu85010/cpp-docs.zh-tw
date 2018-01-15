---
title: "執行階段物件模型服務 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.macros
dev_langs: C++
helpviewer_keywords: run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 986657681dabf1136b072f65b2df76b63f216504
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="run-time-object-model-services"></a>執行階段物件模型服務
類別[CObject](../../mfc/reference/cobject-class.md)和[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)封裝數個物件服務，包括執行階段類別資訊、 序列化和動態物件建立的存取。 從 `CObject` 衍生的所有類別都會繼承此功能。  
  
 對執行階段類別資訊的存取可讓您決定在執行階段的物件類別相關資訊。 當您需要進行函式引數的額外類別檢查時，以及當您必須根據物件類別撰寫特殊用途的程式碼時，能夠在執行階段決定物件的類別就很有用。 C++ 語言並不直接支援執行階段類別資訊。  
  
 序列化是對於檔案來回寫入或讀取物件內容的程序。 即使應用程式結束之後，您還是可以使用序列化儲存物件的內容。 當應用程式重新啟動時，您可以從檔案讀取物件。 這類資料物件稱為「持續性」。  
  
 動態物件建立可讓您在執行階段建立指定類別的物件。 例如，因為架構需要動態建立文件、檢視和框架物件，所以必須支援動態建立。  
  
 下表列出支援的執行階段類別資訊、序列化和動態建立的 MFC 巨集。  
  
 如需有關這些執行階段物件服務和序列化的詳細資訊，請參閱文章[CObject 類別： 存取執行階段類別資訊](../../mfc/accessing-run-time-class-information.md)。  
  
### <a name="run-time-object-model-services-macros"></a>執行階段物件模型服務巨集  
  


|||  
|-|-|  
|[DECLARE_DYNAMIC](#declare_dynamic)|啟用對於執行階段類別資訊的存取 (必須在類別宣告中使用)。|  
|[DECLARE_DYNCREATE](#declare_dyncreate)|啟用動態建立和存取執行階段類別資訊 (必須在類別宣告中使用)。|  
|[DECLARE_SERIAL](#declare_serial)|啟用序列化和存取執行階段類別資訊 (必須在類別宣告中使用)。|  
|[您的類別](#implement_dynamic)|啟用對執行階段類別資訊的存取 (必須在類別實作中使用)。|  
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|啟用動態建立和存取執行階段資訊 (必須在類別實作中使用)。|  
|[IMPLEMENT_SERIAL](#implement_serial)|允許序列化和存取執行階段類別資訊 (必須在類別實作中使用)。|  
|[RUNTIME_CLASS](#runtime_class)|傳回對應至已命名類別的 `CRuntimeClass` 結構。|  


 OLE 經常需要在執行階段動態建立物件。 例如，OLE 伺服器應用程式必須能夠動態建立 OLE 項目以回應來自用戶端的要求。 同樣地，Automation 伺服器必須能夠建立項目以回應從 Automation 用戶端的要求。  
  
 MFC 程式庫提供 OLE 兩個特定巨集。  
  
### <a name="dynamic-creation-of-ole-objects"></a>動態建立 OLE 物件  

 






|||  
|-|-|  
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|判斷通用控制項程式庫是否實作指定的 API。|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|判斷通用控制項程式庫是否實作指定的 API。|
|[DECLARE_OLECREATE](#declare_olecreate)|讓物件透過 OLE Automation 建立。|  
|[DECLARE_OLECTLTYPE](#declare_olectltype)|宣告**GetUserTypeNameID**和`GetMiscStatus`控制類別成員函式。|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|宣告 OLE 控制項提供一份屬性頁以顯示其屬性。|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|讓物件經由 OLE 系統建立。|  
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|實作**GetUserTypeNameID**和`GetMiscStatus`控制類別成員函式。|  
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|這個巨集或[IMPLEMENT_OLECREATE](#implement_olecreate)必須出現在使用任何類別實作檔`DECLARE_OLECREATE`。 |

## <a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS
判斷通用控制項程式庫是否實作指定的 API。  
   
### <a name="syntax"></a>語法  
  ```  
AFX_COMCTL32_IF_EXISTS(  proc );  
```
### <a name="parameters"></a>參數  
 `proc`  
 包含函式名稱以 Null 結束之字串的指標或指定函式的序數值。 如果這個參數是序數值，它必須是低序位文字；高序位文字必須為零。 這個參數必須是 Unicode 值。  
   
### <a name="remarks"></a>備註  
 使用這個巨集來判斷是否通用控制項程式庫函式所指定`proc`(而不是呼叫[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212)。  
   
### <a name="requirements"></a>需求  
 afxcomctl32.h、afxcomctl32.inl  
   
### <a name="see-also"></a>請參閱  
 [隔離的 MFC 通用控制項程式庫](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)
 
## <a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2
判斷通用控制項程式庫是否實作指定的 API (這是 Unicode 版本[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists))。  
   
### <a name="syntax"></a>語法    
```  
AFX_COMCTL32_IF_EXISTS2( proc );  
```
### <a name="parameters"></a>參數  
 `proc`  
 包含函式名稱以 Null 結束之字串的指標或指定函式的序數值。 如果這個參數是序數值，它必須是低序位文字；高序位文字必須為零。 這個參數必須是 Unicode 值。  
   
### <a name="remarks"></a>備註  
 使用這個巨集來判斷是否通用控制項程式庫函式所指定`proc`(而不是呼叫[GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212)。 這個巨集就的 Unicode 版本`AFX_COMCTL32_IF_EXISTS`。  
   
### <a name="requirements"></a>需求  
 afxcomctl32.h、afxcomctl32.inl  
   
### <a name="see-also"></a>請參閱  
 [隔離的 MFC 通用控制項程式庫](../isolation-of-the-mfc-common-controls-library.md) [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)



##  <a name="declare_dynamic"></a>DECLARE_DYNAMIC  
 加入衍生的類別時存取的物件類別的執行階段資訊的能力`CObject`。  
  
```
DECLARE_DYNAMIC(class_name) 
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
### <a name="remarks"></a>備註  
 新增`DECLARE_DYNAMIC`巨集，以標頭 (.h) 的模組類別，然後將該模組包含在所有.cpp 模組需要存取此類別的物件。  
  
 如果您使用**DECLARE**_**動態**和`IMPLEMENT_DYNAMIC`巨集所述，您可以接著使用`RUNTIME_CLASS`巨集和`CObject::IsKindOf`函式來判斷在執行物件的類別時間。  
  
 如果`DECLARE_DYNAMIC`隨附於類別宣告中，然後`IMPLEMENT_DYNAMIC`必須包含在類別實作。  
  
 如需有關`DECLARE_DYNAMIC`巨集，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
### <a name="example"></a>範例  
 請參閱範例的[IMPLEMENT_DYNAMIC](#implement_dynamic)。  

### <a name="requirements"></a>需求  
 **標頭：** afx.h 

##  <a name="declare_dyncreate"></a>DECLARE_DYNCREATE  
 可讓物件的`CObject`-衍生類別，以在執行階段動態建立。  
  
```
DECLARE_DYNCREATE(class_name)   
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
### <a name="remarks"></a>備註  
 架構會使用這項功能，以動態方式建立新的物件。 例如，新建立的檢視當您開啟新文件。 文件、 檢視和框架類別應該支援動態建立，因為架構需要動態地建立。  
  
 新增`DECLARE_DYNCREATE`類別的.h 模組中的巨集然後包含該模組中所有.cpp 模組需要存取此類別的物件。  
  
 如果`DECLARE_DYNCREATE`隨附於類別宣告中，然後`IMPLEMENT_DYNCREATE`必須包含在類別實作。  
  
 如需有關`DECLARE_DYNCREATE`巨集，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
> [!NOTE]
>  `DECLARE_DYNCREATE`巨集包含的所有功能`DECLARE_DYNAMIC`。  
  
### <a name="example"></a>範例  
 請參閱範例的[IMPLEMENT_DYNCREATE](#implement_dyncreate)。  

### <a name="requirements"></a>需求  
 **標頭：** afx.h 

 
## <a name="declareolectltype"></a>DECLARE_OLECTLTYPE
宣告**GetUserTypeNameID**和`GetMiscStatus`控制類別成員函式。  
   
### <a name="syntax"></a>語法    
```
DECLARE_OLECTLTYPE( class_name )  
```
### <a name="parameters"></a>參數  
 *class_name*  
 控制項類別名稱。  
   
### <a name="remarks"></a>備註  
 **GetUserTypeNameID**和`GetMiscStatus`是純虛擬函式，在宣告`COleControl`。 因為這些函式是純虛擬的它們必須覆寫控制項類別中。 除了**DECLARE_OLECTLTYPE**，您必須新增`IMPLEMENT_OLECTLTYPE`巨集，以您的控制項類別宣告中。  
   
### <a name="requirements"></a>需求  
 **標頭：** afxctl.h  
   
### <a name="see-also"></a>請參閱  
 [IMPLEMENT_OLECTLTYPE](#implement_olectltype)
 

## <a name="declareproppageids"></a>DECLARE_PROPPAGEIDS
宣告 OLE 控制項提供一份屬性頁以顯示其屬性。  
   
### <a name="syntax"></a>語法    
```
DECLARE_PROPPAGEIDS( class_name )  
```
### <a name="parameters"></a>參數  
 *class_name*  
 擁有屬性頁的控制項類別名稱。  
   
### <a name="remarks"></a>備註  
 使用`DECLARE_PROPPAGEIDS`巨集，在類別宣告的結尾。 接著，在定義類別的成員函式的.cpp 檔案，使用`BEGIN_PROPPAGEIDS`巨集，每個控制項的屬性頁的巨集項目和`END_PROPPAGEIDS`巨集來宣告屬性頁面清單的結尾。  
  
 如需有關屬性頁的詳細資訊，請參閱文章[ActiveX 控制項： 屬性頁](../mfc-activex-controls-property-pages.md)。  
   
### <a name="requirements"></a>需求  
 **標頭：** afxctl.h  
   
### <a name="see-also"></a>請參閱   
 [BEGIN_PROPPAGEIDS](#begin_proppageids)   
 [END_PROPPAGEIDS](#end_proppageids)

##  <a name="declare_serial"></a>DECLARE_SERIAL  
 會產生所需的 c + + 標頭碼`CObject`-衍生可序列化的類別。  
  
```
DECLARE_SERIAL(class_name)   
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
### <a name="remarks"></a>備註  
 序列化是物件的檔案中寫入或讀取以及內容的程序。  
  
 使用`DECLARE_SERIAL`巨集在.h 模組中，然後將該模組包含在所有.cpp 模組需要存取此類別的物件。  
  
 如果`DECLARE_SERIAL`隨附於類別宣告中，然後`IMPLEMENT_SERIAL`必須包含在類別實作。  
  
 `DECLARE_SERIAL`巨集包含的所有功能`DECLARE_DYNAMIC`和`DECLARE_DYNCREATE`。  
  
 您可以使用**AFX_API**巨集將會自動將匯出`CArchive`引出運算子的類別使用`DECLARE_SERIAL`和`IMPLEMENT_SERIAL`巨集。 括號，類別宣告 （位於.h 檔案） 為下列程式碼：  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 如需有關`DECLARE_SERIAL`巨集，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]  
  
### <a name="requirements"></a>需求  
 **標頭：** afx.h 

##  <a name="implement_dynamic"></a>您的類別  
 產生的 c + + 程式碼所需的動態`CObject`-衍生的類別名稱與階層內的位置與執行階段存取的類別。  
  
```
IMPLEMENT_DYNAMIC(class_name, base_class_name)  
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
 `base_class_name`  
 基底類別的名稱。  
  
### <a name="remarks"></a>備註  
 使用`IMPLEMENT_DYNAMIC`.cpp 模組，然後再連結產生的物件一次程式碼的巨集。  
  
 如需詳細資訊，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]  

### <a name="requirements"></a>需求  
 **標頭：** afx.h 

##  <a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE  
 可讓物件的`CObject`-衍生類別以動態方式建立在執行時間搭配使用時`DECLARE_DYNCREATE`巨集。  
  
```
IMPLEMENT_DYNCREATE(class_name, base_class_name)   
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
 `base_class_name`  
 基底類別的實際名稱。  
  
### <a name="remarks"></a>備註  
 架構會建立新的物件，以動態方式，例如從磁碟讀取物件在序列化期間時使用這項功能。 新增`IMPLEMENT_DYNCREATE`類別實作檔中的巨集。 如需詳細資訊，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
 如果您使用`DECLARE_DYNCREATE`和`IMPLEMENT_DYNCREATE`巨集，然後您可以使用`RUNTIME_CLASS`巨集和`CObject::IsKindOf`來在執行階段判斷物件的類別成員函式。  
  
 如果`DECLARE_DYNCREATE`隨附於類別宣告中，然後`IMPLEMENT_DYNCREATE`必須包含在類別實作。  
  
 請注意，此巨集定義，將會叫用類別的預設建構函式。 如果非一般建構函式會明確實作的類別，它必須同時也可以明確實作預設建構函。 預設建構函式可以加入至類別的**私人**或**保護**成員各節，以防止從外部類別實作所呼叫。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]  
  
 [!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]  

### <a name="requirements"></a>需求  
 **標頭：** afx.h 

## <a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS
這個巨集或[IMPLEMENT_OLECREATE](#implement_olecreate)必須出現在使用任何類別實作檔`DECLARE_OLECREATE`。  
   
### <a name="syntax"></a>語法    
```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags, 
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
  
```
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
 *external_name*  
 物件名稱公開給其他應用程式 （以引號括住）。  
  
 `nFlags`  
 包含一或多個下列旗標：  
  
-   `afxRegInsertable`可讓控制項出現在插入物件對話方塊中的 OLE 物件。    
-   `afxRegApartmentThreading`在 ThreadingModel 登錄中設定執行緒模型 = Apartment。    
-   **afxRegFreeThreading** ThreadingModel 登錄中設定執行緒模型 = 可用。  
  
     您可以結合兩個旗標`afxRegApartmentThreading`和`afxRegFreeThreading`設定 ThreadingModel = Both。 請參閱[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)執行緒模型註冊的詳細資訊的 Windows SDK 中。    
 *l*， *w1*， *w2*， *b1*， *b2*， *b3*， *b4*， *b5*， *b6*， *b7*， *b8*  
 此類別的元件**CLSID**。  
   
### <a name="remarks"></a>備註  
  
> [!NOTE]
>  如果您使用`IMPLEMENT_OLECREATE_FLAGS`，您可以指定哪些物件支援使用的執行緒模型`nFlags`參數。 如果您想要支援只有單一 treading 模型，使用`IMPLEMENT_OLECREATE`。  
  
 External name 是公開給其他應用程式的識別碼。 用戶端應用程式使用的外部名稱從 automation 伺服程式要求此類別的物件。  
  
 OLE 類別 ID 是唯一的 128 位元識別碼的物件。 它由一個**長**、 兩個**WORD**，以及八**位元組**s 所表示的*l*， *w1*， *w2*，和*b1*透過*b8*語法描述中。 應用程式精靈和程式碼精靈視需要為您建立唯一的 OLE 類別 Id。  
   
### <a name="requirements"></a>需求  
 **標頭：** afxdisp.h  
   
### <a name="see-also"></a>請參閱  
 [巨集和全域變數](mfc-macros-and-globals.md)   
 [DECLARE_OLECREATE](#declare_olecreate)   
 [CLSID 金鑰](http://msdn.microsoft.com/library/windows/desktop/ms691424)


## <a name="implement_olecreate"></a>IMPLEMENT_OLECTLTYPE
實作**GetUserTypeNameID**和`GetMiscStatus`控制類別成員函式。  
   
### <a name="syntax"></a>語法    
```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )  
```
### <a name="parameters"></a>參數  
 *class_name*  
 控制項類別名稱。  
  
 *idsUserTypeName*  
 包含控制項的外部名稱的字串資源 ID。  
  
 *dwOleMisc*  
 包含一或多個旗標的列舉。 如需有關這個列舉的詳細資訊，請參閱[OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Windows SDK 中。  
   
### <a name="remarks"></a>備註  
 除了`IMPLEMENT_OLECTLTYPE`，您必須新增**DECLARE_OLECTLTYPE**巨集，以您的控制項類別宣告中。  
  
 **GetUserTypeNameID**成員函式傳回的資源字串，識別您的控制項類別。 `GetMiscStatus`傳回**OLEMISC**位元為您的控制項。 此列舉會指定描述控制項的其他特性設定的集合。 如需完整的說明**OLEMISC**設定，請參閱[OLEMISC](http://msdn.microsoft.com/library/windows/desktop/ms678497) Windows SDK 中。  
  
> [!NOTE]
>  ActiveX ControlWizard 所使用的預設值為： **OLEMISC_ACTIVATEWHENVISIBLE**， **OLEMISC_SETCLIENTSITEFIRST**， **OLEMISC_INSIDEOUT**， **OLEMISC_CANTLINKINSIDE**，和**OLEMISC_RECOMPOSEONRESIZE**。  
   
### <a name="requirements"></a>需求  
 **標頭：** afxctl.h  
   
### <a name="see-also"></a>請參閱  
 [巨集和全域變數](mfc-macros-and-globals.md)   
 [DECLARE_OLECTLTYPE](#declare_olectltype)

##  <a name="implement_serial"></a>IMPLEMENT_SERIAL  
 產生的 c + + 程式碼所需的動態`CObject`-衍生的類別名稱與階層內的位置與執行階段存取的類別。  
  
```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)  
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
 `base_class_name`  
 基底類別的名稱。  
  
 *wSchema*  
 A **UINT** 」 版本號碼"會讓還原序列化程式找出並處理所建立的資料保存在編碼之前程式版本。 類別結構描述編號不能為-1。  
  
### <a name="remarks"></a>備註  
 使用`IMPLEMENT_SERIAL`巨集.cpp 單元; 然後將產生的物件程式碼連結一次。  
  
 您可以使用**AFX_API**巨集將會自動將匯出`CArchive`引出運算子的類別使用`DECLARE_SERIAL`和`IMPLEMENT_SERIAL`巨集。 括號，類別宣告 （位於.h 檔案） 為下列程式碼：  
  
 [!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]  
  
 如需詳細資訊，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]  

### <a name="requirements"></a>需求  
 **標頭：** afx.h 

##  <a name="runtime_class"></a>RUNTIME_CLASS  
 從 c + + 類別的名稱取得執行階段類別結構。  
  
```
RUNTIME_CLASS(class_name)  
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 （不以引號括住） 類別的實際名稱。  
  
### <a name="remarks"></a>備註  
 `RUNTIME_CLASS`將指標傳回至[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)所指定的類別結構*class_name*。 只有`CObject`-衍生的類別宣告與`DECLARE_DYNAMIC`， `DECLARE_DYNCREATE`，或`DECLARE_SERIAL`會傳回指向`CRuntimeClass`結構。  
  
 如需詳細資訊，請參閱[CObject 類別主題](../../mfc/using-cobject.md)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]  

### <a name="requirements"></a>需求  
 **標頭：** afx.h 
   
##  <a name="declare_olecreate"></a>DECLARE_OLECREATE  
 可讓物件的`CCmdTarget`-衍生類別，以透過 OLE automation 建立。  
  
```
DECLARE_OLECREATE(class_name) 
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
### <a name="remarks"></a>備註  
 這個巨集可讓其他 OLE 功能的應用程式建立此類型的物件。  
  
 新增`DECLARE_OLECREATE`類別的.h 模組中的巨集，然後包含該模組中所有.cpp 模組需要存取此類別的物件。  
  
 如果`DECLARE_OLECREATE`隨附於類別宣告中，然後`IMPLEMENT_OLECREATE`必須包含在類別實作。 類別宣告使用`DECLARE_OLECREATE`也必須使用`DECLARE_DYNCREATE`或`DECLARE_SERIAL`。  

### <a name="requirements"></a>需求  
 **標頭**: afxdisp.h  

##  <a name="implement_olecreate"></a>IMPLEMENT_OLECREATE  
 這個巨集或[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)必須出現在使用任何類別實作檔`DECLARE_OLECREATE`。  
  
```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)  
```  
  
### <a name="parameters"></a>參數  
 *class_name*  
 類別的實際名稱。  
  
 *external_name*  
 物件名稱公開給其他應用程式 （以引號括住）。  
  
 *l*， *w1*， *w2*， *b1*， *b2*， *b3*， *b4*， *b5*， *b6*， *b7*， *b8*  
 此類別的元件**CLSID**。  
  
### <a name="remarks"></a>備註  
  
> [!NOTE]
>  如果您使用`IMPLEMENT_OLECREATE`，您可以根據預設，支援只有單一執行緒模型。 如果您使用`IMPLEMENT_OLECREATE_FLAGS`，您可以指定哪些物件支援使用的執行緒模型`nFlags`參數。  
  
 External name 是公開給其他應用程式的識別碼。 用戶端應用程式使用的外部名稱從 automation 伺服程式要求此類別的物件。  
  
 OLE 類別 ID 是唯一的 128 位元識別碼的物件。 它由一個**長**、 兩個**WORD**，以及八**位元組**s 所表示的*l*， *w1*， *w2*，和*b1*透過*b8*語法描述中。 應用程式精靈和程式碼精靈視需要為您建立唯一的 OLE 類別 Id。  

### <a name="requirements"></a>需求  
 **標頭**: afxdisp.h 

## <a name="see-also"></a>請參閱  
 [巨集和全域變數](../../mfc/reference/mfc-macros-and-globals.md)
