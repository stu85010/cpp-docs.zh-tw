---
title: OLE 初始化
ms.date: 11/04/2016
f1_keywords:
- afxdisp/AfxOleInit
- afxdisp/AfxEnableControlContainer
helpviewer_keywords:
- OLE initialization
ms.assetid: aa8a54a7-24c3-4344-b2c6-dbcf6084fa31
ms.openlocfilehash: c935dbf88b3c70cdd9ec585685bf6231ded01dde
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623323"
---
# <a name="ole-initialization"></a>OLE 初始化

應用程式必須先初始化 OLE 系統 DLL 並驗證 DLL 版本是否正確，才可以使用 OLE 系統服務。 `AfxOleInit`函式會初始化 OLE 系統 Dll。

### <a name="ole-initialization"></a>OLE 初始化

|||
|-|-|
|[AfxOleInit](#afxoleinit)|初始化 OLE 程式庫。|
|[AfxEnableControlContainer](#afxenablecontrolcontainer)|呼叫應用程式物件的 `InitInstance` 函式中的這個函式，可支援 OLE 控制項的內含項目。|

## <a name="afxenablecontrolcontainer"></a> AfxEnableControlContainer

呼叫應用程式物件的 `InitInstance` 函式中的這個函式，可支援 OLE 控制項的內含項目。

### <a name="syntax"></a>語法

```
void AfxEnableControlContainer( );
```

### <a name="remarks"></a>備註

如需 OLE 控制項 （現在稱為 ActiveX 控制項） 的詳細資訊，請參閱[ActiveX 控制項主題](../mfc-activex-controls.md)。

### <a name="requirements"></a>需求

**標頭：** afxdisp.h

##  <a name="afxoleinit"></a>  AfxOleInit

初始化 OLE 支援應用程式。

```
BOOL AFXAPI AfxOleInit();
```

### <a name="return-value"></a>傳回值

如果成功則為非零0，如果初始化失敗，可能是因為已安裝正確版本的 OLE 系統 Dll。

### <a name="remarks"></a>備註

呼叫此函式以初始化 OLE 的 MFC 應用程式對的支援。 呼叫此函式時，便會執行下列動作：

- 初始化 COM 程式庫上呼叫的應用程式的目前 apartment。 如需詳細資訊，請參閱 < [OleInitialize](/windows/desktop/api/ole2/nf-ole2-oleinitialize)。

- 建立訊息篩選物件，實作[IMessageFilter](/windows/desktop/api/objidl/nn-objidl-imessagefilter)介面。 可存取此訊息篩選，藉由呼叫[AfxOleGetMessageFilter](application-control.md#afxolegetmessagefilter)。

> [!NOTE]
>  如果**AfxOleInit**稱為從 MFC DLL，則呼叫會失敗。 函式會假設，如果從 DLL 呼叫它時，OLE 系統先前已初始化所呼叫的應用程式，就會發生失敗。

> [!NOTE]
>  MFC 應用程式必須初始化為單一執行緒 apartment (STA)。 如果您呼叫[CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex)中您`InitInstance`覆寫，請指定 COINIT_APARTMENTTHREADED （而不是 COINIT_MULTITHREADED）。

### <a name="requirements"></a>需求

**標頭：** afxdisp.h

## <a name="see-also"></a>另請參閱

[巨集和全域](../../mfc/reference/mfc-macros-and-globals.md)
