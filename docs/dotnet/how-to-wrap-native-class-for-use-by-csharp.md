---
title: 如何：包裝原生類別以便讓 C# 使用
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- native code [C++], Visual C# and
- classes [C++], Visual C# and
ms.assetid: 988819ae-cc6a-4453-8ff5-be369210d962
ms.openlocfilehash: dc61c9749492f2f0dbe0c6b60abc2a9030cab4d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588093"
---
# <a name="how-to-wrap-native-class-for-use-by-c"></a>如何：包裝原生類別以便讓 C# 使用

此範例示範如何包裝原生 c + + 類別，因此它可供 C# 中，或其他.NET 語言撰寫的程式碼。

## <a name="example"></a>範例

```
// wrap_native_class_for_mgd_consumption.cpp
// compile with: /clr /LD
#include <windows.h>
#include <vcclr.h>
#using <System.dll>

using namespace System;

class UnmanagedClass {
public:
   LPCWSTR GetPropertyA() { return 0; }
   void MethodB( LPCWSTR ) {}
};

public ref class ManagedClass {
public:
   // Allocate the native object on the C++ Heap via a constructor
   ManagedClass() : m_Impl( new UnmanagedClass ) {}

   // Deallocate the native object on a destructor
   ~ManagedClass() {
      delete m_Impl;
   }

protected:
   // Deallocate the native object on the finalizer just in case no destructor is called
   !ManagedClass() {
      delete m_Impl;
   }

public:
   property String ^  get_PropertyA {
      String ^ get() {
         return gcnew String( m_Impl->GetPropertyA());
      }
   }

   void MethodB( String ^ theString ) {
      pin_ptr<const WCHAR> str = PtrToStringChars(theString);
      m_Impl->MethodB(str);
   }

private:
   UnmanagedClass * m_Impl;
};
```

## <a name="see-also"></a>另請參閱

[使用 C++ Interop (隱含 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)