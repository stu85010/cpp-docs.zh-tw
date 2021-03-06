---
title: 函式呼叫運算子：()
ms.date: 11/04/2016
helpviewer_keywords:
- ( ) function call operator
- function calls, C++ functions
- () function call operator
- postfix operators [C++]
- function calls, operator
- functions [C++], function-call operator
- function call operator ()
ms.assetid: 50c92e59-a4bf-415a-a6ab-d66c679ee80a
ms.openlocfilehash: 79c43ed11bfc73ec4bfaedad0a20b45fb6ca1ffb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676242"
---
# <a name="function-call-operator-"></a>函式呼叫運算子：()

函式呼叫運算子，後面是後置運算式 **（)**，指定函式呼叫。

## <a name="syntax"></a>語法

```
postfix-expression
( [argument-expression-list ] )
```

## <a name="remarks"></a>備註

函式呼叫運算子的引數是以逗號分隔的零或多個運算式，即函式的實際引數。

*後置運算式*必須評估為函式位址 （例如，函式識別項或函式指標的值），以及*引數運算式清單*是一份 （分隔的運算式以逗點） 的值 （引數） 會傳遞至函式。 *argument-expression-list* 引數可以是空的。

*後置運算式*必須是其中一種類型：

- 傳回類型 `T` 的函式。 如以下範例宣告所示

    ```cpp
    T func( int i )
    ```

- 傳回類型 `T` 之函式的指標。 如以下範例宣告所示

    ```cpp
    T (*func)( int i )
    ```

- 傳回類型 `T` 之函式的參考。 如以下範例宣告所示

    ```cpp
    T (&func)(int i)
    ```

- 傳回類型 `T` 的成員指標函式取值 (Dereference)。 函式呼叫的範例如下

    ```cpp
    (pObject->*pmf)();
    (Object.*pmf)();
    ```

## <a name="example"></a>範例

下列範例呼叫具有三個引數的標準程式庫函式 `strcat_s`：

```cpp
// expre_Function_Call_Operator.cpp
// compile with: /EHsc

#include <iostream>
#include <string>

// C++ Standard Library name space
using namespace std;

int main()
{
    enum
    {
        sizeOfBuffer = 20
    };

    char s1[ sizeOfBuffer ] = "Welcome to ";
    char s2[ ] = "C++";

    strcat_s( s1, sizeOfBuffer, s2 );

    cout << s1 << endl;
}
```

```Output
Welcome to C++
```

## <a name="function-call-results"></a>函式呼叫結果

除非函式宣告為參考類型，否則函式呼叫會判斷值為右值。 具有參考傳回型別的函式會評估為左值，而且可以在指派陳述式的左邊使用，如下所示：

```cpp
// expre_Function_Call_Results.cpp
// compile with: /EHsc
#include <iostream>
class Point
{
public:
    // Define "accessor" functions as
    // reference types.
    unsigned& x() { return _x; }
    unsigned& y() { return _y; }
private:
    unsigned _x;
    unsigned _y;
};

using namespace std;
int main()
{
    Point ThePoint;

    ThePoint.x() = 7;           // Use x() as an l-value.
    unsigned y = ThePoint.y();  // Use y() as an r-value.

    // Use x() and y() as r-values.
    cout << "x = " << ThePoint.x() << "\n"
         << "y = " << ThePoint.y() << "\n";
}
```

上述程式碼中定義的類別，稱為`Point`，其中包含私用資料物件來代表*x*並*y*座標。 這些資料物件必須經過修改，而且必須擷取其值。 這個程式只是這種類別的數項設計之一，使用 `GetX` 和 `SetX` 或 `GetY` 和 `SetY` 則是另一種可能的設計方式。

傳回類別類型、類別類型的指標或類別類型的參考之函式可以做為成員選擇運算子的左運算元使用。 因此，下列程式碼是合法的：

```cpp
// expre_Function_Results2.cpp
class A {
public:
   A() {}
   A(int i) {}
   int SetA( int i ) {
      return (I = i);
   }

   int GetA() {
      return I;
   }

private:
   int I;
};

A func1() {
   A a = 0;
   return a;
}

A* func2() {
   A *a = new A();
   return a;
}

A& func3() {
   A *a = new A();
   A &b = *a;
   return b;
}

int main() {
   int iResult = func1().GetA();
   func2()->SetA( 3 );
   func3().SetA( 7 );
}
```

函式可以透過遞迴方式呼叫。 如需函式宣告的詳細資訊，請參閱[函式](functions-cpp.md)。 相關的資料位於[程式和連結](../cpp/program-and-linkage-cpp.md)。

## <a name="see-also"></a>另請參閱

[後置運算式](../cpp/postfix-expressions.md)<br/>
[C++ 內建運算子、優先順序和順序關聯性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[函式呼叫](../c-language/function-call-c.md)