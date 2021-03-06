---
title: __outwordstring
ms.date: 11/04/2016
f1_keywords:
- __outwordstring
helpviewer_keywords:
- rep outsw instruction
- __outwordstring intrinsic
- outsw instruction
ms.assetid: b470c7a0-1de9-4370-886a-b2c3a1f842f4
ms.openlocfilehash: df7ca6ddbb80c21397beb91b8e671f248f2a1d9c
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326286"
---
# <a name="outwordstring"></a>__outwordstring

**Microsoft 專屬**

會產生`rep outsw`指示，會傳送`Count`開頭的字`Buffer`出所指定的 I/O 連接埠`Port`。

## <a name="syntax"></a>語法

```
void __outwordstring(
   unsigned short Port,
   unsigned short* Buffer,
   unsigned long Count
);
```

#### <a name="parameters"></a>參數

*連接埠*<br/>
[in]若要將資料傳送至連接埠。

*Buffer*<br/>
[in]指定的連接埠傳送資料的指標。

*計數*<br/>
[in]要傳送的單字數目。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`__outwordstring`|x86、x64|

**標頭檔** \<intrin.h >

## <a name="remarks"></a>備註

此常式僅可作為內建常式使用。

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建](../intrinsics/compiler-intrinsics.md)