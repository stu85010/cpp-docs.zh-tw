---
title: IOleInPlaceActiveObjectImpl 類別
ms.date: 11/04/2016
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
ms.openlocfilehash: 785972af55cdf594bb45b0257e626aa5344af60a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447459"
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl 類別

這個類別提供方法來協助就地控制項與其容器之間的通訊。

> [!IMPORTANT]
>  此類別和其成員不能在 Windows 執行階段中執行的應用程式。

## <a name="syntax"></a>語法

```
template<class T>
class IOleInPlaceActiveObjectImpl
```

#### <a name="parameters"></a>參數

*T*<br/>
您的類別，衍生自`IOleInPlaceActiveObjectImpl`。

## <a name="members"></a>成員

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|啟用即時線上說明。 ATL 實作會傳回 E_NOTIMPL。|
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|可讓非強制回應對話方塊。 ATL 實作會傳回 S_OK。|
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|取得視窗控制代碼。|
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|在容器文件視窗啟用或停用時，通知控制項。 ATL 實作會傳回 S_OK。|
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|容器的最上層框架視窗啟用或停用時，通知控制項。 ATL 實作會傳回|
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|通知控制項，它需要調整大小框線。 ATL 實作會傳回 S_OK。|
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|處理從容器的功能表快速鍵訊息。 ATL 實作會傳回 E_NOTIMPL。|

## <a name="remarks"></a>備註

[和](/windows/desktop/api/oleidl/nn-oleidl-ioleinplaceactiveobject)介面可協助就地控制項與其容器之間的通訊; 例如，通訊作用中狀態的控制項和容器，並通知控制項它需要調整大小它本身。 類別`IOleInPlaceActiveObjectImpl`提供的預設實作`IOleInPlaceActiveObject`，並支援`IUnknown`資訊傳送給傾印裝置在偵錯組建。

**相關文章** [ATL 教學課程](../../atl/active-template-library-atl-tutorial.md)，[建立 ATL 專案](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>繼承階層

`IOleInPlaceActiveObject`

`IOleInPlaceActiveObjectImpl`

## <a name="requirements"></a>需求

**標頭：** atlctl.h

##  <a name="contextsensitivehelp"></a>  IOleInPlaceActiveObjectImpl::ContextSensitiveHelp

啟用即時線上說明。

```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```

### <a name="return-value"></a>傳回值

傳回 E_NOTIMPL。

### <a name="remarks"></a>備註

請參閱[IOleWindow::ContextSensitiveHelp](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-contextsensitivehelp) Windows SDK 中。

##  <a name="enablemodeless"></a>  IOleInPlaceActiveObjectImpl::EnableModeless

可讓非強制回應對話方塊。

```
HRESULT EnableModeless(BOOL fEnable);
```

### <a name="return-value"></a>傳回值

傳回 S_OK。

### <a name="remarks"></a>備註

請參閱[IOleInPlaceActiveObject::EnableModeless](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-enablemodeless) Windows SDK 中。

##  <a name="getwindow"></a>  IOleInPlaceActiveObjectImpl::GetWindow

容器會呼叫此函式來取得控制項的視窗控制代碼。

```
HRESULT GetWindow(HWND* phwnd);
```

### <a name="remarks"></a>備註

某些容器無法運作，無視窗，即使它是目前的視窗型控制項。 在 ATL 的實作中，如果`CComControl::m_bWasOnceWindowless`資料成員是 TRUE，則函數會傳回 E_FAIL。 否則，如果\* *phwnd*不是 NULL，`GetWindow`指派*phwnd*至控制項類別的資料成員`m_hWnd`，並傳回 S_OK。

請參閱[IOleWindow::GetWindow](/windows/desktop/api/oleidl/nf-oleidl-iolewindow-getwindow) Windows SDK 中。

##  <a name="ondocwindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnDocWindowActivate

在容器文件視窗啟用或停用時，通知控制項。

```
HRESULT OnDocWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>傳回值

傳回 S_OK。

### <a name="remarks"></a>備註

請參閱[ioleinplaceactiveobject:: Ondocwindowactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-ondocwindowactivate) Windows SDK 中。

##  <a name="onframewindowactivate"></a>  IOleInPlaceActiveObjectImpl::OnFrameWindowActivate

容器的最上層框架視窗啟用或停用時，通知控制項。

```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```

### <a name="return-value"></a>傳回值

傳回 S_OK。

### <a name="remarks"></a>備註

請參閱[ioleinplaceactiveobject:: Onframewindowactivate](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-onframewindowactivate) Windows SDK 中。

##  <a name="resizeborder"></a>  IOleInPlaceActiveObjectImpl::ResizeBorder

通知控制項，它需要調整大小框線。

```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```

### <a name="return-value"></a>傳回值

傳回 S_OK。

### <a name="remarks"></a>備註

請參閱[ioleinplaceactiveobject:: Resizeborder](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-resizeborder) Windows SDK 中。

##  <a name="translateaccelerator"></a>  IOleInPlaceActiveObjectImpl::TranslateAccelerator

處理從容器的功能表快速鍵訊息。

```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```

### <a name="return-value"></a>傳回值

這個方法支援下列傳回值：

如果訊息已成功轉譯為 S_OK。

如果訊息未被翻譯，S_FALSE。

### <a name="remarks"></a>備註

請參閱[:: Translateaccelerator](/windows/desktop/api/oleidl/nf-oleidl-ioleinplaceactiveobject-translateaccelerator) Windows SDK 中。

## <a name="see-also"></a>另請參閱

[CComControl 類別](../../atl/reference/ccomcontrol-class.md)<br/>
[ActiveX 控制項介面](/windows/desktop/com/activex-controls-interfaces)<br/>
[類別概觀](../../atl/atl-class-overview.md)
