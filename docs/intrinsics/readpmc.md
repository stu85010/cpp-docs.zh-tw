---
title: __readpmc
ms.date: 11/04/2016
f1_keywords:
- __readpmc
helpviewer_keywords:
- Read Performance Monitoring Counters instruction
- __readpmc intrinsic
- rdpmc instruction
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
ms.openlocfilehash: 059d9344fa329e69666abaca4d73122ab29f8d2a
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326429"
---
# <a name="readpmc"></a>__readpmc

**Microsoft 專屬**

會產生`rdpmc`指令，讀取效能監視所指定的計數器`counter`。

## <a name="syntax"></a>語法

```
unsigned __int64 __readpmc(
   unsigned long counter
);
```

#### <a name="parameters"></a>參數

*counter*<br/>
[in]要讀取的效能計數器。

## <a name="return-value"></a>傳回值

指定的效能計數器的值。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`__readpmc`|x86、x64|

**標頭檔** \<intrin.h >

## <a name="remarks"></a>備註

此內建只適用於核心模式，且此常式僅可作為內建。

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建](../intrinsics/compiler-intrinsics.md)