---
title: IPersistPropertyBagImpl 類別
ms.date: 11/04/2016
f1_keywords:
- IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl
- ATLCOM/ATL::IPersistPropertyBagImpl::GetClassID
- ATLCOM/ATL::IPersistPropertyBagImpl::InitNew
- ATLCOM/ATL::IPersistPropertyBagImpl::Load
- ATLCOM/ATL::IPersistPropertyBagImpl::Save
helpviewer_keywords:
- IPersistPropertyBagImpl class
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
ms.openlocfilehash: 644f26ffbfb29003780eb2fc7acf3471d101ec57
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549067"
---
# <a name="ipersistpropertybagimpl-class"></a>IPersistPropertyBagImpl 類別

這個類別會實作`IUnknown`，可讓用戶端提供的屬性包以儲存其屬性的物件。

> [!IMPORTANT]
>  此類別和其成員不能在 Windows 執行階段中執行的應用程式。

## <a name="syntax"></a>語法

```
template <class T>
class ATL_NO_VTABLE IPersistPropertyBagImpl : public IPersistPropertyBag
```

#### <a name="parameters"></a>參數

*T*<br/>
您的類別，衍生自`IPersistPropertyBagImpl`。

## <a name="members"></a>成員

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[IPersistPropertyBagImpl::GetClassID](#getclassid)|擷取物件的 CLSID。|
|[IPersistPropertyBagImpl::InitNew](#initnew)|初始化新建立的物件。 ATL 實作會傳回 S_OK。|
|[IPersistPropertyBagImpl::Load](#load)|從用戶端提供的屬性包中載入物件的屬性。|
|[IPersistPropertyBagImpl::Save](#save)|將物件的屬性儲存到用戶端提供的屬性包中。|

## <a name="remarks"></a>備註

[IPersistPropertyBag](https://msdn.microsoft.com/library/aa768205.aspx)介面可讓用戶端提供的屬性包以儲存其屬性的物件。 類別`IPersistPropertyBagImpl`提供此介面的預設實作，並實作`IUnknown`資訊傳送給傾印裝置在偵錯組建。

`IPersistPropertyBag` 可搭配[IPropertyBag](https://msdn.microsoft.com/library/aa768196.aspx)並[IErrorLog](https://msdn.microsoft.com/library/aa768231.aspx)。 用戶端必須實作這些後者的兩個介面。 透過`IPropertyBag`，用戶端儲存及載入物件的個別屬性。 透過`IErrorLog`，物件與用戶端可以報告遇到的任何錯誤。

**相關文章** [ATL 教學課程](../../atl/active-template-library-atl-tutorial.md)，[建立 ATL 專案](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>繼承階層

`IPersistPropertyBag`

`IPersistPropertyBagImpl`

## <a name="requirements"></a>需求

**標頭：** atlcom.h

##  <a name="getclassid"></a>  IPersistPropertyBagImpl::GetClassID

擷取物件的 CLSID。

```
STDMETHOD(GetClassID)(CLSID* pClassID);
```

### <a name="remarks"></a>備註

請參閱[IPersist::GetClassID](/windows/desktop/api/objidl/nf-objidl-ipersist-getclassid) Windows SDK 中。

##  <a name="initnew"></a>  IPersistPropertyBagImpl::InitNew

初始化新建立的物件。

```
STDMETHOD(InitNew)();
```

### <a name="return-value"></a>傳回值

傳回 S_OK。

### <a name="remarks"></a>備註

請參閱[IPersistPropertyBag::InitNew](https://msdn.microsoft.com/library/aa768204.aspx) Windows SDK 中。

##  <a name="load"></a>  IPersistPropertyBagImpl::Load

從用戶端提供的屬性包中載入物件的屬性。

```
STDMETHOD(Load)(LPPROPERTYBAG pPropBag, LPERRORLOG pErrorLog);
```

### <a name="remarks"></a>備註

ATL 會使用物件的屬性對應，來擷取這項資訊。

請參閱[IPersistPropertyBag::Load](https://msdn.microsoft.com/library/aa768206.aspx) Windows SDK 中。

##  <a name="save"></a>  IPersistPropertyBagImpl::Save

將物件的屬性儲存到用戶端提供的屬性包中。

```
STDMETHOD(Save)(
    LPPROPERTYBAG pPropBag,
    BOOL fClearDirty,
    BOOL fSaveAllProperties);
```

### <a name="remarks"></a>備註

ATL 會使用物件的屬性對應來儲存這項資訊。 根據預設，這個方法會儲存所有屬性的值為何*fSaveAllProperties*。

請參閱[IPersistPropertyBag::Save](https://msdn.microsoft.com/library/aa768207.aspx) Windows SDK 中。

## <a name="see-also"></a>另請參閱

[BEGIN_PROP_MAP](property-map-macros.md#begin_prop_map)<br/>
[類別概觀](../../atl/atl-class-overview.md)
