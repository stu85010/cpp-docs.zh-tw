---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: e558838ca9cd06fb5529f689d45a920db151d272
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643244"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits Namespace

描述常見的控制代碼為基礎的資源類型的特性。

## <a name="syntax"></a>語法

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>成員

### <a name="structures"></a>結構

|名稱|描述|
|----------|-----------------|
|[CriticalSectionTraits 結構](../windows/criticalsectiontraits-structure.md)|特製化`CriticalSection`支援無效的重要區段或函式來釋放重要區段物件。|
|[EventTraits 結構](../windows/eventtraits-structure.md)|定義特性`Event`類別控制代碼。|
|[FileHandleTraits 結構](../windows/filehandletraits-structure.md)|定義的檔案控制代碼的特性。|
|[HANDLENullTraits 結構](../windows/handlenulltraits-structure.md)|定義未初始化的控制代碼的一般特性。|
|[HANDLETraits 結構](../windows/handletraits-structure.md)|定義通用的控制代碼的特性。|
|[MutexTraits 結構](../windows/mutextraits-structure.md)|定義通用特性[Mutex](../windows/mutex-class1.md)類別。|
|[SemaphoreTraits 結構](../windows/semaphoretraits-structure.md)|定義號誌物件的一般的特性。|
|[SRWLockExclusiveTraits 結構](../windows/srwlockexclusivetraits-structure.md)|描述一般特性`SRWLock`獨佔的鎖定模式的類別。|
|[SRWLockSharedTraits 結構](../windows/srwlocksharedtraits-structure.md)|描述一般特性`SRWLock`以共用鎖定模式的類別。|

## <a name="requirements"></a>需求

**標頭：** corewrappers.h

**命名空間：** Microsoft::WRL::Wrappers

## <a name="see-also"></a>另請參閱

[Microsoft::WRL::Wrappers 命名空間](../windows/microsoft-wrl-wrappers-namespace.md)