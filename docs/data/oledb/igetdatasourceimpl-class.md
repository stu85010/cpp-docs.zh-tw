---
title: IGetDataSourceImpl 類別
ms.date: 11/04/2016
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
ms.openlocfilehash: cd6b56f4281a2fdde77229ec54be6d6289a87148
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556565"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl 類別

提供實作[IGetDataSource](https://docs.microsoft.com/previous-versions/windows/desktop/ms709721(v=vs.85))物件。

## <a name="syntax"></a>語法

```cpp
template <class T>
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource
```

### <a name="parameters"></a>參數

*T*<br/>
您的類別，衍生自`IGetDataSourceImpl`。

## <a name="requirements"></a>需求

**Header:** atldb.h

## <a name="members"></a>成員

### <a name="interface-methods"></a>介面方法

|||
|-|-|
|[GetDataSource](#getdatasource)|在 建立工作階段資料來源物件上傳回的介面指標。|

## <a name="remarks"></a>備註

這是必要的介面上的工作階段取得的資料來源物件的介面指標時。

## <a name="getdatasource"></a> Igetdatasourceimpl:: Getdatasource

在 建立工作階段資料來源物件上傳回的介面指標。

### <a name="syntax"></a>語法

```cpp
STDMETHOD(GetDataSource)(REFIID riid,
   IUnknown ** ppDataSource);
```

#### <a name="parameters"></a>參數

請參閱[IGetDataSource::GetDataSource](https://docs.microsoft.com/previous-versions/windows/desktop/ms725443(v=vs.85))中*OLE DB 程式設計人員參考*。

### <a name="remarks"></a>備註

如果您需要存取資料來源物件中的屬性很有用。

## <a name="see-also"></a>另請參閱

[OLE DB 提供者樣板](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB 提供者範本架構](../../data/oledb/ole-db-provider-template-architecture.md)