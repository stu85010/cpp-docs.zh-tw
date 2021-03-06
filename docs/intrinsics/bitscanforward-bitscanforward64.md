---
title: _BitScanForward, _BitScanForward64
ms.date: 11/04/2016
f1_keywords:
- _BitScanForward
- _BitScanForward_cpp
- _BitScanForward64_cpp
- _BitScanForward64
helpviewer_keywords:
- _BitScanForward intrinsic
- bsf instruction
- BitScanForward intrinsic
ms.assetid: 405e60fb-0815-42a7-9b02-6fc035122203
ms.openlocfilehash: 87bb2a20e786982d8e0c710696f0339f579a84e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440465"
---
# <a name="bitscanforward-bitscanforward64"></a>_BitScanForward, _BitScanForward64

**Microsoft 專屬**

從遮罩資料的最低有效位元 (MSB) 到最高有效位元 (LSB) 搜尋設定位元 (1)。

## <a name="syntax"></a>語法

```
unsigned char _BitScanForward(
   unsigned long * Index,
   unsigned long Mask
);
unsigned char _BitScanForward64(
   unsigned long * Index,
   unsigned __int64 Mask
);
```

#### <a name="parameters"></a>參數

*Tuple*<br/>
[out]會使用找到的第一個設定位元 (1) 的位元位置載入。

*遮罩*<br/>
[in]要搜尋的 32 位元或 64 位元值。

## <a name="return-value"></a>傳回值

如果遮罩是零，則為 0；否則為非零。

## <a name="remarks"></a>備註

如果找到設定位元，會在第一個參數中傳回找到的第一個設定位元的位元位置。 如果找不到設定位元，就會傳回 0；否則，會傳回 1。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`_BitScanForward`|x86、 x64、 ARM|
|`_BitScanForward64`|ARM、 x64|

**標頭檔** \<intrin.h >

## <a name="example"></a>範例

```
// BitScanForward.cpp
// compile with: /EHsc
#include <iostream>
#include <intrin.h>
using namespace std;

#pragma intrinsic(_BitScanForward)

int main()
{
   unsigned long mask = 0x1000;
   unsigned long index;
   unsigned char isNonzero;

   cout << "Enter a positive integer as the mask: " << flush;
   cin >> mask;
   isNonzero = _BitScanForward(&index, mask);
   if (isNonzero)
   {
      cout << "Mask: " << mask << " Index: " << index << endl;
   }
   else
   {
      cout << "No set bits found.  Mask is zero." << endl;
   }
}
```

## <a name="input"></a>輸入

```
12
```

## <a name="sample-output"></a>範例輸出

```
Enter a positive integer as the mask:
Mask: 12 Index: 2
```

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建](../intrinsics/compiler-intrinsics.md)