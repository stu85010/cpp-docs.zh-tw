---
title: 匿名類別類型
ms.date: 11/04/2016
helpviewer_keywords:
- class types [C++], anonymous
- anonymous class types
ms.assetid: 9ba667b2-8c2a-4c29-82a6-fa120b9233c8
ms.openlocfilehash: 9cd27fb40522a07ce4591b654ee8a6dda53b4f28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456403"
---
# <a name="anonymous-class-types"></a>匿名類別類型

可以是匿名的類別 — 也就是它們可以宣告沒有*識別碼*。 這是很有用，當您取代類別名稱取代**typedef**名稱，如下所示：

```cpp
typedef struct
{
    unsigned x;
    unsigned y;
} POINT;
```

> [!NOTE]
>  上述範例中的匿名類別用法對於保留與現有 C 程式碼的相容性而言很實用。 在某些 C 程式碼，使用**typedef**搭配匿名結構的情況相當普遍。

另外，當您想要讓類別成員的參考出現，就像該參考不是包含在另一個類別中一般時，匿名類別也相當實用，如下所示：

```cpp
struct PTValue
{
    POINT ptLoc;
    union
    {
        int  iValue;
        long lValue;
    };
};

PTValue ptv;
```

在上述程式碼中，`iValue`可以使用物件成員選取運算子存取 (**。**)，如下所示：

```cpp
int i = ptv.iValue;
```

匿名類別會受到某些限制  (如需匿名等位的詳細資訊，請參閱[等位](../cpp/unions.md)。)匿名類別：

- 不能具有建構函式或解構函式。

- 不可做為引數傳遞至函式 (除非使用省略符號讓類型檢查失敗)。

- 不可做為函式的傳回值傳回。

## <a name="anonymous-structs"></a>匿名結構

### <a name="microsoft-specific"></a>Microsoft 特定的

Microsoft C 擴充功能可讓您在另一個結構內宣告結構變數，而不需為它命名。 這些巢狀結構稱為匿名結構。 C++ 不允許匿名結構。

您可以存取匿名結構的成員，就如同它們是包含結構中的成員。

```cpp
// anonymous_structures.c
#include <stdio.h>

struct phone
{
    int  areacode;
    long number;
};

struct person
{
    char   name[30];
    char   gender;
    int    age;
    int    weight;
    struct phone;    // Anonymous structure; no name needed
} Jim;

int main()
{
    Jim.number = 1234567;
    printf_s("%d\n", Jim.number);
}
//Output: 1234567
```

**結束 Microsoft 專屬**