---
title: IRegistrar 介面
ms.date: 2/1/2017
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
ms.openlocfilehash: 3494920164ed3a62713298d2cafdbdc27dbb2b97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534767"
---
# <a name="iregistrar-interface"></a>IRegistrar 介面

這個介面會定義在 atliface.h，而且會在內部使用 CAtlModule 成員函式這類[UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced)。

## <a name="syntax"></a>語法

```
typedef interface IRegistrar IRegistrar;
```

## <a name="remarks"></a>備註

請參閱主題[使用可置換的參數 （登錄器的前置處理器）](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)如需詳細資訊。

## <a name="members"></a>成員

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|註冊資源。 |
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| 取消註冊該資源。|
|[IRegistrar::FileRegister](#fileregister)|註冊檔案。|
|[IRegistrar::FileUnregister](#fileunregister)|取消登錄該檔案。|
|[IRegistrar::StringRegister](#stringregister)|註冊的字串。|
|[IRegistrar::StringUnregister](#stringunregister)|取消註冊的字串|
|[IRegistrar::ResourceRegister](#resourceregister)|註冊資源。|
|[IRegistrar::ResourceUnregister](#resourceunregister)|取消註冊該資源。|

## <a name="requirements"></a>需求

**標頭：** atlifase.h

##  <a name="resourceregistersz"></a>  IRegistrar::ResourceRegisterSz

註冊資源。

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="resourceunregistersz"></a>  IRegistrar::ResourceUnregisterSz

取消註冊該資源。

```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="fileregister"></a>  IRegistrar::FileRegister

註冊檔案。

```
virtual HRESULT STDMETHODCALLTYPE FileRegister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

##  <a name="fileunregister"></a>  IRegistrar::FileUnregister

取消登錄該檔案。

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister(
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```

##  <a name="stringregister"></a>  IRegistrar::StringRegister

註冊指定的字串資料。

```
virtual HRESULT STDMETHODCALLTYPE StringRegister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

##  <a name="stringunregister"></a>  IRegistrar::StringUnregister

取消註冊指定的字串資料。

```
virtualHRESULT STDMETHODCALLTYPE StringUnregister(
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```

##  <a name="resourceregister"></a>  IRegistrar::ResourceRegister

註冊資源。

```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

##  <a name="resourceunregister"></a>  IRegistrar::ResourceUnregister

取消註冊該資源。

```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister(
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```

## <a name="see-also"></a>另請參閱

[使用可置換的參數 (登錄器的前置處理器)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)<br/>
[類別概觀](../../atl/atl-class-overview.md)<br/>
[模組類別](../../atl/atl-module-classes.md)<br/>
[登錄元件 （登錄器）](../../atl/atl-registry-component-registrar.md)
