---
title: CFontHolder 類別
ms.date: 11/04/2016
f1_keywords:
- CFontHolder
- AFXCTL/CFontHolder
- AFXCTL/CFontHolder::CFontHolder
- AFXCTL/CFontHolder::GetDisplayString
- AFXCTL/CFontHolder::GetFontDispatch
- AFXCTL/CFontHolder::GetFontHandle
- AFXCTL/CFontHolder::InitializeFont
- AFXCTL/CFontHolder::QueryTextMetrics
- AFXCTL/CFontHolder::ReleaseFont
- AFXCTL/CFontHolder::Select
- AFXCTL/CFontHolder::SetFont
- AFXCTL/CFontHolder::m_pFont
helpviewer_keywords:
- CFontHolder [MFC], CFontHolder
- CFontHolder [MFC], GetDisplayString
- CFontHolder [MFC], GetFontDispatch
- CFontHolder [MFC], GetFontHandle
- CFontHolder [MFC], InitializeFont
- CFontHolder [MFC], QueryTextMetrics
- CFontHolder [MFC], ReleaseFont
- CFontHolder [MFC], Select
- CFontHolder [MFC], SetFont
- CFontHolder [MFC], m_pFont
ms.assetid: 728ab472-0c97-440d-889f-1324c6e1b6b8
ms.openlocfilehash: 24a33aafa279f47bcfabd1ac3f3ee8d4abd4c731
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659638"
---
# <a name="cfontholder-class"></a>CFontHolder 類別

實作內建字型屬性，並封裝 Windows 字型物件和 `IFont` 介面的功能。

## <a name="syntax"></a>語法

```
class CFontHolder
```

## <a name="members"></a>成員

### <a name="public-constructors"></a>公用建構函式

|名稱|描述|
|----------|-----------------|
|[CFontHolder::CFontHolder](#cfontholder)|建構 `CFontHolder` 物件。|

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[CFontHolder::GetDisplayString](#getdisplaystring)|擷取容器的屬性瀏覽器中顯示的字串。|
|[CFontHolder::GetFontDispatch](#getfontdispatch)|傳回字型的`IDispatch`介面。|
|[CFontHolder::GetFontHandle](#getfonthandle)|傳回 Windows 字型的控制代碼。|
|[CFontHolder::InitializeFont](#initializefont)|初始化`CFontHolder`物件。|
|[CFontHolder::QueryTextMetrics](#querytextmetrics)|擷取相關的字型資訊。|
|[CFontHolder::ReleaseFont](#releasefont)|中斷`CFontHolder`物件從`IFont`和`IFontNotification`介面。|
|[CFontHolder::Select](#select)|選取字型資源放入裝置內容中。|
|[CFontHolder::SetFont](#setfont)|連接`CFontHolder`物件至`IFont`介面。|

### <a name="public-data-members"></a>公用資料成員

|名稱|描述|
|----------|-----------------|
|[CFontHolder::m_pFont](#m_pfont)|指標`CFontHolder`物件的`IFont`介面。|

## <a name="remarks"></a>備註

`CFontHolder` 沒有基底類別。

使用此類別來實作自訂的字型屬性，為您的控制項。 如需建立這類屬性的詳細資訊，請參閱文章[ActiveX 控制項： 使用字型](../../mfc/mfc-activex-controls-using-fonts.md)。

## <a name="inheritance-hierarchy"></a>繼承階層

`CFontHolder`

## <a name="requirements"></a>需求

**標頭：** afxctl.h

##  <a name="cfontholder"></a>  CFontHolder::CFontHolder

建構 `CFontHolder` 物件。

```
explicit CFontHolder(LPPROPERTYNOTIFYSINK pNotify);
```

### <a name="parameters"></a>參數

*pNotify*<br/>
字型的指標`IPropertyNotifySink`介面。

### <a name="remarks"></a>備註

您必須呼叫`InitializeFont`使用之前，先初始化產生的物件。

##  <a name="getdisplaystring"></a>  CFontHolder::GetDisplayString

擷取可以容器的屬性瀏覽器中顯示的字串。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>參數

*strValue*<br/>
若要參考[CString](../../atl-mfc-shared/reference/cstringt-class.md)要保存的顯示字串。

### <a name="return-value"></a>傳回值

已成功擷取的字串; 如果為非零否則為 0。

##  <a name="getfontdispatch"></a>  CFontHolder::GetFontDispatch

呼叫此函式可擷取字型的分派介面的指標。

```
LPFONTDISP GetFontDispatch();
```

### <a name="return-value"></a>傳回值

指標`CFontHolder`物件的`IFontDisp`介面。 請注意，此函式，呼叫`GetFontDispatch`必須呼叫`IUnknown::Release`當它完成時，此介面指標上。

### <a name="remarks"></a>備註

呼叫`InitializeFont`再呼叫`GetFontDispatch`。

##  <a name="getfonthandle"></a>  CFontHolder::GetFontHandle

呼叫此函式可取得 Windows 字型的控制代碼。

```
HFONT GetFontHandle();

HFONT GetFontHandle(
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>參數

*cyLogical*<br/>
以邏輯單位，在其中繪製控制項的矩形的高度。

*cyHimetric*<br/>
MM_HIMETRIC 單位，控制項的高度。

### <a name="return-value"></a>傳回值

字型物件控制代碼否則為 NULL。

### <a name="remarks"></a>備註

比率*cyLogical*並*cyHimetric*用來計算適當的顯示大小，以邏輯單位，如 MM_HIMETRIC 單位表示字型的點數大小：

顯示大小 = ( *cyLogical* / *cyHimetric*) X 字型大小

不含任何參數的版本將控制代碼傳回螢幕的正確調整大小的字型。

##  <a name="initializefont"></a>  CFontHolder::InitializeFont

初始化`CFontHolder`物件。

```
void InitializeFont(
    const FONTDESC* pFontDesc = NULL,
    LPDISPATCH pFontDispAmbient = NULL);
```

### <a name="parameters"></a>參數

*pFontDesc*<br/>
字型描述結構的指標 ( [FONTDESC](/windows/desktop/api/olectl/ns-olectl-tagfontdesc))，指定字型的特性。

*pFontDispAmbient*<br/>
容器的環境字型屬性的指標。

### <a name="remarks"></a>備註

如果*pFontDispAmbient*不是 NULL，`CFontHolder`物件所連接的複製品`IFont`容器的環境字型屬性所使用的介面。

如果*pFontDispAmbient*是 NULL，新的字型物件會建立從所指向的字型描述*pFontDesc*或者，如果*pFontDesc*從預設值是 NULL，描述。

呼叫此函式之後建構`CFontHolder`物件。

##  <a name="m_pfont"></a>  CFontHolder::m_pFont

指標`CFontHolder`物件的`IFont`介面。

```
LPFONT m_pFont;
```

##  <a name="querytextmetrics"></a>  CFontHolder::QueryTextMetrics

擷取資訊所代表的實體字型`CFontHolder`物件。

```
void QueryTextMetrics(LPTEXTMETRIC lptm);
```

### <a name="parameters"></a>參數

*lptm*<br/>
指標[TEXTMETRIC](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica)接收資訊的結構。

##  <a name="releasefont"></a>  CFontHolder::ReleaseFont

此函式中斷`CFontHolder`物件從其`IFont`介面。

```
void ReleaseFont();
```

##  <a name="select"></a>  CFontHolder::Select

呼叫此函式以指定的裝置內容至選取控制項的字型。

```
CFont* Select(
    CDC* pDC,
    long cyLogical,
    long cyHimetric);
```

### <a name="parameters"></a>參數

*pDC*<br/>
在其中選取字型的裝置內容。

*cyLogical*<br/>
以邏輯單位，在其中繪製控制項的矩形的高度。

*cyHimetric*<br/>
MM_HIMETRIC 單位，控制項的高度。

### <a name="return-value"></a>傳回值

已取代為字型的指標。

### <a name="remarks"></a>備註

請參閱[GetFontHandle](#getfonthandle)的討論*cyLogical*並*cyHimetric*參數。

##  <a name="setfont"></a>  CFontHolder::SetFont

釋放任何現有的字型，並連接`CFontHolder`物件至`IFont`介面。

```
void SetFont(LPFONT pNewFont);
```

### <a name="parameters"></a>參數

*pNewFont*<br/>
新的指標`IFont`介面。

## <a name="see-also"></a>另請參閱

[階層架構圖表](../../mfc/hierarchy-chart.md)<br/>
[CPropExchange 類別](../../mfc/reference/cpropexchange-class.md)
