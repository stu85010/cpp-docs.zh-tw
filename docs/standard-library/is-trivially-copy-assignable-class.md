---
title: is_trivially_copy_assignable 類別
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_assignable
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
ms.openlocfilehash: 831e7c5afdd39980876a8e8284a68fec2084a4e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630980"
---
# <a name="istriviallycopyassignable-class"></a>is_trivially_copy_assignable 類別

測試類型是否有 trivial 複製指派運算子。

## <a name="syntax"></a>語法

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>參數

*T*<br/>
要查詢的類型。

## <a name="remarks"></a>備註

如果型別述詞的執行個體保留 true 的型別*T*是具有 trivial 複製指派運算子，否則為 false 的類別。

類別的指派建構函式*T*微不足道，如果它以隱含方式提供，類別*T*沒有虛擬函式類別*T*沒有虛擬基底類別類別類型的所有非靜態資料成員都有 trivial 指派運算子和陣列的類別類型的所有非靜態資料成員的類別具有 trivial 指派運算子。

## <a name="requirements"></a>需求

**標頭：**\<type_traits>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[<type_traits>](../standard-library/type-traits.md)<br/>
