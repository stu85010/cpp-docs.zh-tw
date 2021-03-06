---
title: CComAllocator 類別
ms.date: 11/04/2016
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
ms.openlocfilehash: 83ea5cdbc2460d308edf89647dafba65cb327f03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658870"
---
# <a name="ccomallocator-class"></a>CComAllocator 類別

這個類別提供方法來管理使用 COM 記憶體常式的記憶體。

## <a name="syntax"></a>語法

```
class CComAllocator
```

## <a name="members"></a>成員

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[CComAllocator::Allocate](#allocate)|呼叫這個靜態方法，以配置記憶體。|
|[CComAllocator::Free](#free)|呼叫此靜態方法來釋放已配置的記憶體。|
|[CComAllocator::Reallocate](#reallocate)|呼叫這個靜態方法，以重新配置記憶體。|

## <a name="remarks"></a>備註

此類別由[CComHeapPtr](../../atl/reference/ccomheapptr-class.md)提供 COM 記憶體配置常式。 對應類別[CCRTAllocator](../../atl/reference/ccrtallocator-class.md)，提供相同的方法使用的 CRT 常式。

## <a name="requirements"></a>需求

**標頭：** atlbase.h

##  <a name="allocate"></a>  CComAllocator::Allocate

呼叫此靜態函式以配置記憶體。

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>參數

*nBytes*<br/>
要配置的位元組數目。

### <a name="return-value"></a>傳回值

傳回 void 指標至配置的空間，或如果沒有足夠的可用記憶體，則為 NULL。

### <a name="remarks"></a>備註

配置記憶體。 請參閱[CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc)如需詳細資訊。

##  <a name="free"></a>  CComAllocator::Free

呼叫此靜態函式來釋放已配置的記憶體。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>參數

*p*<br/>
配置的記憶體之指標。

### <a name="remarks"></a>備註

釋放配置的記憶體。 請參閱[CoTaskMemFree](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemfree)如需詳細資訊。

##  <a name="reallocate"></a>  CComAllocator::Reallocate

呼叫此靜態函式以重新配置記憶體。

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>參數

*p*<br/>
配置的記憶體之指標。

*nBytes*<br/>
要重新配置的位元組數目。

### <a name="return-value"></a>傳回值

傳回 void 指標至配置的空間或 NULL，如果沒有足夠的記憶體

### <a name="remarks"></a>備註

調整配置的記憶體數量。 請參閱[CoTaskMemRealloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemrealloc)如需詳細資訊。

## <a name="see-also"></a>另請參閱

[CComHeapPtr 類別](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator 類別](../../atl/reference/ccrtallocator-class.md)<br/>
[類別概觀](../../atl/atl-class-overview.md)
