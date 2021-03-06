---
title: time_base 類別
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: e790237e506aa32bafdb39938d841307bbc4d9c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593397"
---
# <a name="timebase-class"></a>time_base 類別

類別可做為 facet 的基底類別的樣板類別 time_get，只會將列舉型別定義`dateorder`和此類型的數個常數。

## <a name="syntax"></a>語法

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>備註

每個常數特性都會以不同的方式描述，來將日期元件排序。 這些常數如下：

- `no_order` 指定沒有特定順序。

- `dmy` 指定該順序天、 月、 年，如 2 年 12 月 1979 年。

- `mdy` 指定該順序月、 日、 年，如 12 月 2 日，1979 年。

- `ymd` 指定該順序年、 月、 日，1979年/12/2 如。

- `ydm` 指定該順序年、 日、 月，如 1979:2 年 12 月。

## <a name="requirements"></a>需求

**標頭︰**\<locale>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
