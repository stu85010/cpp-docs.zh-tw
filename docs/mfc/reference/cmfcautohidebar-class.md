---
title: CMFCAutoHideBar 類別
ms.date: 10/18/2018
f1_keywords:
- CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CMFCAutoHideBar
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AddAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::AllowShowOnPaneMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::CalcFixedLayout
- AFXAUTOHIDEBAR/CMFCAutoHideBar::Create
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetFirstAHWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::GetVisibleCount
- AFXAUTOHIDEBAR/CMFCAutoHideBar::OnShowControlBarMenu
- AFXAUTOHIDEBAR/CMFCAutoHideBar::RemoveAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetActiveInGroup
- AFXAUTOHIDEBAR/CMFCAutoHideBar::SetRecentVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::ShowAutoHideWindow
- AFXAUTOHIDEBAR/CMFCAutoHideBar::StretchPane
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UnSetAutoHideMode
- AFXAUTOHIDEBAR/CMFCAutoHideBar::UpdateVisibleState
- AFXAUTOHIDEBAR/CMFCAutoHideBar::m_nShowAHWndDelay
helpviewer_keywords:
- CMFCAutoHideBar [MFC], CMFCAutoHideBar
- CMFCAutoHideBar [MFC], AddAutoHideWindow
- CMFCAutoHideBar [MFC], AllowShowOnPaneMenu
- CMFCAutoHideBar [MFC], CalcFixedLayout
- CMFCAutoHideBar [MFC], Create
- CMFCAutoHideBar [MFC], GetFirstAHWindow
- CMFCAutoHideBar [MFC], GetVisibleCount
- CMFCAutoHideBar [MFC], OnShowControlBarMenu
- CMFCAutoHideBar [MFC], RemoveAutoHideWindow
- CMFCAutoHideBar [MFC], SetActiveInGroup
- CMFCAutoHideBar [MFC], SetRecentVisibleState
- CMFCAutoHideBar [MFC], ShowAutoHideWindow
- CMFCAutoHideBar [MFC], StretchPane
- CMFCAutoHideBar [MFC], UnSetAutoHideMode
- CMFCAutoHideBar [MFC], UpdateVisibleState
- CMFCAutoHideBar [MFC], m_nShowAHWndDelay
ms.assetid: 54c8d84f-de64-4efd-8a47-3ea0ade40a70
ms.openlocfilehash: 8592a5485afedab075a21215e1ffa140a8c66e28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50619449"
---
# <a name="cmfcautohidebar-class"></a>CMFCAutoHideBar 類別

`CMFCAutoHideBar` 類別是實作自動隱藏功能的特殊工具列類別。

如需詳細資訊，請參閱中的原始程式碼**VC\\atlmfc\\src\\mfc** Visual Studio 安裝資料夾。

## <a name="syntax"></a>語法

```
class CMFCAutoHideBar : public CPane
```

## <a name="members"></a>成員

### <a name="public-constructors"></a>公用建構函式

|名稱|描述|
|----------|-----------------|
|[CMFCAutoHideBar::CMFCAutoHideBar](#cmfcautohidebar)||

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[CMFCAutoHideBar::AddAutoHideWindow](#addautohidewindow)||
|[CMFCAutoHideBar::AllowShowOnPaneMenu](#allowshowonpanemenu)|(覆寫 `CPane::AllowShowOnPaneMenu`。)|
|[CMFCAutoHideBar::CalcFixedLayout](#calcfixedlayout)|(覆寫[cbasepane:: Calcfixedlayout](../../mfc/reference/cbasepane-class.md#calcfixedlayout)。)|
|[CMFCAutoHideBar::Create](#create)|會建立一種控制列，並將它附加至[CPane](../../mfc/reference/cpane-class.md)物件。 (覆寫[cpane:: Create](../../mfc/reference/cpane-class.md#create)。)|
|[CMFCAutoHideBar::GetFirstAHWindow](#getfirstahwindow)||
|[CMFCAutoHideBar::GetVisibleCount](#getvisiblecount)||
|[CMFCAutoHideBar::OnShowControlBarMenu](#onshowcontrolbarmenu)|當特殊窗格功能表即將顯示時由架構呼叫。 (覆寫[cpane:: Onshowcontrolbarmenu](../../mfc/reference/cpane-class.md#onshowcontrolbarmenu)。)|
|[CMFCAutoHideBar::RemoveAutoHideWindow](#removeautohidewindow)||
|[CMFCAutoHideBar::SetActiveInGroup](#setactiveingroup)|(覆寫[cpane:: Setactiveingroup](../../mfc/reference/cpane-class.md#setactiveingroup)。)|
|[CMFCAutoHideBar::SetRecentVisibleState](#setrecentvisiblestate)||
|[CMFCAutoHideBar::ShowAutoHideWindow](#showautohidewindow)||
|[CMFCAutoHideBar::StretchPane](#stretchpane)|垂直或水平伸展窗格。 (覆寫[cbasepane:: Stretchpane](../../mfc/reference/cbasepane-class.md#stretchpane)。)|
|[CMFCAutoHideBar::UnSetAutoHideMode](#unsetautohidemode)||
|[CMFCAutoHideBar::UpdateVisibleState](#updatevisiblestate)||

### <a name="data-members"></a>資料成員

|名稱|描述|
|----------|-----------------|
|[CMFCAutoHideBar::m_nShowAHWndDelay](#m_nshowahwnddelay)|當使用者將滑鼠游標置於上方之間的時間延遲[CMFCAutoHideButton 類別](../../mfc/reference/cmfcautohidebutton-class.md)和目前在架構顯示相關聯的視窗。|

## <a name="remarks"></a>備註

當使用者將停駐窗格切換為自動隱藏模式時，架構會自動建立 `CMFCAutoHideBar` 物件。 它也會建立必要[CAutoHideDockSite](../../mfc/reference/cautohidedocksite-class.md)並[CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)物件。 每個 `CAutoHideDockSite` 物件與一個個別的 `CMFCAutoHideButton` 相關聯。

當使用者的滑鼠停留在 `CMFCAutoHideButton` 上方時，`CMFCAutoHideBar` 類別會實作 `CAutoHideDockSite` 的顯示。 當工具列收到 WM_MOUSEMOVE 訊息時，`CMFCAutoHideBar` 會啟動計時器。 當計時器完成時，會將 WM_TIMER 事件通知傳送給工具列。 工具列會藉由檢查滑鼠指標是否放置在相同的自動隱藏按鈕上方 (在計時器啟動時所放置)，以處理此事件。 如果是，則顯示附加的 `CAutoHideDockSite`。

您可以設定 `m_nShowAHWndDelay` 來控制計時器的延遲長度。 預設值為 400 毫秒。

## <a name="example"></a>範例

下列範例示範如何建構 `CMFCAutoHideBar` 物件及使用其 `GetDockSiteRow` 方法。

[!code-cpp[NVC_MFC_RibbonApp#26](../../mfc/reference/codesnippet/cpp/cmfcautohidebar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>繼承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCAutoHideBar](../../mfc/reference/cmfcautohidebar-class.md)

## <a name="requirements"></a>需求

**標頭：** afxautohidebar.h

## <a name="addautohidewindow"></a>  CMFCAutoHideBar::AddAutoHideWindow

將功能加入 `CDockablePane` 視窗以自動隱藏該功能。

```
CMFCAutoHideButton* AddAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    DWORD dwAlignment);
```

### <a name="parameters"></a>參數

*pAutoHideWnd*<br/>
[in]您想要隱藏視窗。

*dwAlignment*<br/>
[in]值，指定與應用程式視窗的 [自動隱藏] 按鈕的對齊方式。

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

*DwAlignment*參數會指出自動隱藏按鈕的應用程式中的所在位置。 這個參數可以是下列任何一個值：

- CBRS_ALIGN_LEFT

- CBRS_ALIGN_RIGHT

- CBRS_ALIGN_TOP

- CBRS_ALIGN_BOTTOM

## <a name="allowshowonpanemenu"></a>  CMFCAutoHideBar::AllowShowOnPaneMenu

```
virtual BOOL AllowShowOnPaneMenu() const;
```

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

## <a name="calcfixedlayout"></a>  CMFCAutoHideBar::CalcFixedLayout

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>參數

[in]*bStretch*<br/>

[in]*bHorz*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

## <a name="cmfcautohidebar"></a>  CMFCAutoHideBar::CMFCAutoHideBar

建構 CMFCAutoHideBar 物件。

```
CMFCAutoHideBar();
```

### <a name="remarks"></a>備註

## <a name="create"></a>  CMFCAutoHideBar::Create

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    DWORD dwControlBarStyle = AFX_DEFAULT_PANE_STYLE,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>參數

*lpszClassName*<br/>

*cheaderctrl:: Create*<br/>

*rect*<br/>

*pParentWnd*<br/>

*nID*<br/>

*dwControlBarStyle*<br/>

*pContext*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

## <a name="getfirstahwindow"></a>  CMFCAutoHideBar::GetFirstAHWindow

傳回應用程式中第一個自動隱藏視窗的指標。

```
CDockablePane* GetFirstAHWindow();
```

### <a name="return-value"></a>傳回值

應用程式中的第一個自動隱藏視窗，或如果沒有，則為 NULL。

### <a name="remarks"></a>備註

## <a name="getvisiblecount"></a>  CMFCAutoHideBar::GetVisibleCount

取得可見的自動隱藏按鈕數目。

```
int GetVisibleCount();
```

### <a name="return-value"></a>傳回值

傳回可見的自動隱藏按鈕數目。

### <a name="remarks"></a>備註

## <a name="m_nshowahwnddelay"></a>  CMFCAutoHideBar::m_nShowAHWndDelay

當使用者將滑鼠游標置於上方之間的時間延遲[CMFCAutoHideButton 類別](../../mfc/reference/cmfcautohidebutton-class.md)和目前在架構顯示相關聯的視窗。

```
int CMFCAutoHideBar::m_nShowAHWndDelay = 400;
```

### <a name="remarks"></a>備註

當使用者將滑鼠游標置於`CMFCAutoHideButton`，架構會顯示相關聯的視窗之前，會稍微延遲。 這個參數會決定該延遲，以毫秒為單位的長度。

## <a name="onshowcontrolbarmenu"></a>  CMFCAutoHideBar::OnShowControlBarMenu

```
virtual BOOL OnShowControlBarMenu(CPoint);
```

### <a name="parameters"></a>參數

[in]*CPoint*<br/>

### <a name="return-value"></a>傳回值

### <a name="remarks"></a>備註

## <a name="removeautohidewindow"></a>  CMFCAutoHideBar::RemoveAutoHideWindow

移除和終結自動隱藏視窗。

```
    BOOL RemoveAutoHideWindow(CDockablePane* pAutoHideWnd);
```

### <a name="parameters"></a>參數

CDockablePane * *pAutoHideWnd*自動隱藏視窗，以移除。

### <a name="return-value"></a>傳回值

如果成功，則為 TRUE，否則為 FALSE。

### <a name="remarks"></a>備註

## <a name="setactiveingroup"></a>  CMFCAutoHideBar::SetActiveInGroup

將自動隱藏列標幟為作用中。

```
virtual void SetActiveInGroup(BOOL bActive);
```

### <a name="parameters"></a>參數

[in]BOOL *bActive*設為作用中，否則為 FALSE，則為 TRUE。

### <a name="remarks"></a>備註

請參閱 [CPane::SetActiveInGroup](../../mfc/reference/cpane-class.md#setactiveingroup)。

## <a name="setrecentvisiblestate"></a>  CMFCAutoHideBar::SetRecentVisibleState

```
void SetRecentVisibleState(BOOL bState);
```

### <a name="parameters"></a>參數

*bState*<br/>
[in]若要設定的狀態。

### <a name="remarks"></a>備註

## <a name="showautohidewindow"></a>  CMFCAutoHideBar::ShowAutoHideWindow

顯示自動隱藏視窗。

```
BOOL ShowAutoHideWindow(
    CDockablePane* pAutoHideWnd,
    BOOL bShow,
    BOOL bDelay);
```

### <a name="parameters"></a>參數

*pAutoHideWnd*<br/>
[in]若要顯示的視窗。

*bShow*<br/>
[in]如果為 true，則顯示視窗。

*bDelay*<br/>
[in]會忽略這個參數。

### <a name="return-value"></a>傳回值

如果成功，則為 TRUE，否則為 FALSE。

### <a name="remarks"></a>備註

## <a name="stretchpane"></a>  CMFCAutoHideBar::StretchPane

將摺疊狀態的自動隱藏列調整成適合 `CMFCAutoHideButton` 物件的大小。

```
virtual CSize StretchPane(
    int nLength,
    BOOL bVert);
```

### <a name="parameters"></a>參數

*nLength*<br/>
[in]值未在基底實作。 在衍生實作中，這個值可用來表示已調整窗格的長度。

*bVert*<br/>
[in]值未在基底實作。 在衍生實作中，使用 true 以控制代碼，自動隱藏列垂直摺疊，大小寫和 FALSE，自動隱藏列是水平摺疊案例。

### <a name="return-value"></a>傳回值

產生的已調整窗格大小。

### <a name="remarks"></a>備註

衍生類別可以覆寫這個方法以自訂行為。

## <a name="unsetautohidemode"></a>  CMFCAutoHideBar::UnSetAutoHideMode

停用自動隱藏列群組的自動隱藏模式。

```
void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup)
```

### <a name="parameters"></a>參數

[in] pFirstBarInGroup 群組中的第一個自動隱藏列的指標。

### <a name="remarks"></a>備註

## <a name="updatevisiblestate"></a>  CMFCAutoHideBar::UpdateVisibleState

架構會在需要重新繪製自動隱藏列時呼叫。

```
void UpdateVisibleState();
```

### <a name="remarks"></a>備註

## <a name="see-also"></a>另請參閱

[階層架構圖表](../../mfc/hierarchy-chart.md)<br/>
[類別](../../mfc/reference/mfc-classes.md)<br/>
[CPane 類別](../../mfc/reference/cpane-class.md)<br/>
[CAutoHideDockSite 類別](../../mfc/reference/cautohidedocksite-class.md)<br/>
[CMFCAutoHideButton 類別](../../mfc/reference/cmfcautohidebutton-class.md)
