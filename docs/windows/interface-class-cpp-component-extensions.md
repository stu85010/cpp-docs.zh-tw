---
title: 介面類別 (C + + /cli 和 C + + /CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- interface_CPP
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
ms.openlocfilehash: 57bb83e91492995551ec155c2bcd6bbff3da3186
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517126"
---
# <a name="interface-class--ccli-and-ccx"></a>介面類別 (C + + /cli 和 C + + /CX)

宣告介面。  如需原生介面資訊，請參閱[__interface](../cpp/interface.md)。

## <a name="all-runtimes"></a>所有執行階段

### <a name="syntax"></a>語法

```cpp
interface_access
interface class
name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};
```

### <a name="parameters"></a>參數

*interface_access*<br/>
組件外部介面的存取範圍。  可能的值為**公開金鑰**並**私人**。  **私用**是預設值。 巢狀的介面不能有*interface_access*規範。

*name*<br/>
介面的名稱。

*inherit_access*<br/>
存取範圍*base_interface*。  唯一允許協助工具的基底介面是**公開**（預設值）。

*base_interface*<br/>
（選擇性）介面的基底介面*名稱*。

### <a name="remarks"></a>備註

**介面結構**相當於**介面類別**。

介面可以包含宣告的函式、 事件和屬性。  所有介面成員都具有公用存取範圍。 介面也可以包含靜態資料成員、 函式、 事件和屬性，並在介面中，必須定義這些靜態成員。

介面會定義可能會實作類別的方式。 介面不是類別和類別僅可以實作介面。 如果類別方法，定義介面中宣告的函式，被實作該函式，不會被覆寫。 因此，名稱查閱不包含介面成員。

類別或衍生自介面的結構必須實作介面的所有成員。 實作介面時*名稱*您也必須實作的介面中`base_interface`清單。

如需詳細資訊，請參閱:

- [介面靜態建構函式](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)

- [泛型介面 (C++/CLI)](../windows/generic-interfaces-visual-cpp.md)

如需其他的 CLR 型別資訊，請參閱[類別和結構](../windows/classes-and-structs-cpp-component-extensions.md)。

您可以在編譯時期偵測類型是否具有介面`__is_interface_class(type)`。 如需詳細資訊，請參閱 <<c0> [ 類型特性的編譯器支援](../windows/compiler-support-for-type-traits-cpp-component-extensions.md)。

在開發環境中，您可以取得 F1 說明這些關鍵字的反白顯示關鍵字，(`interface class`，例如)，然後按 F1。

## <a name="windows-runtime"></a>Windows 執行階段

### <a name="remarks"></a>備註

(這個語言功能沒有只適用於 Windows 執行階段的備註。)

### <a name="requirements"></a>需求

編譯器選項：`/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>備註

(這個語言功能沒有只適用於 Common Language Runtime 的備註。)

### <a name="requirements"></a>需求

編譯器選項：`/clr`

### <a name="examples"></a>範例

下列程式碼範例示範如何介面可以定義 clock 函式的行為。

```cpp
// mcppv2_interface_class.cpp
// compile with: /clr
using namespace System;

public delegate void ClickEventHandler(int, double);

// define interface with nested interface
public interface class Interface_A {
   void Function_1();

   interface class Interface_Nested_A {
      void Function_2();
   };
};

// interface with a base interface
public interface class Interface_B : Interface_A {
   property int Property_Block;
   event ClickEventHandler^ OnClick;
   static void Function_3() { Console::WriteLine("in Function_3"); }
};

// implement nested interface
public ref class MyClass : public Interface_A::Interface_Nested_A {
public:
   virtual void Function_2() { Console::WriteLine("in Function_2"); }
};

// implement interface and base interface
public ref class MyClass2 : public Interface_B {
private:
   int MyInt;

public:
   // implement non-static function
   virtual void Function_1() { Console::WriteLine("in Function_1"); }

   // implement property
   property int Property_Block {
      virtual int get() { return MyInt; }
      virtual void set(int value) { MyInt = value; }
   }
   // implement event
   virtual event ClickEventHandler^ OnClick;

   void FireEvents() {
      OnClick(7, 3.14159);
   }
};

// class that defines method called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }
};

int main() {
   // call static function in an interface
   Interface_B::Function_3();

   // instantiate class that implements nested interface
   MyClass ^ x = gcnew MyClass;
   x->Function_2();

   // instantiate class that implements interface with base interface
   MyClass2 ^ y = gcnew MyClass2;
   y->Function_1();
   y->Property_Block = 8;
   Console::WriteLine(y->Property_Block);

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);

   // invoke events
   y->FireEvents();

   // unhook handler to event
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);

   // call implemented function via interface handle
   Interface_A^ hi = gcnew MyClass2();
   hi->Function_1();
}
```

```Output
in Function_3

in Function_2

in Function_1

8

OnClick: 7, 3.14159

in Function_1
```

下列程式碼範例示範兩種方式可使用相同的簽章宣告在多個介面，而且其中一個類別會使用這些介面實作函式。

```cpp
// mcppv2_interface_class_2.cpp
// compile with: /clr /c
interface class I {
   void Test();
   void Test2();
};

interface class J : I {
   void Test();
   void Test2();
};

ref struct R : I, J {
   // satisfies the requirement to implement Test in both interfaces
   virtual void Test() {}

   // implement both interface functions with explicit overrides
   virtual void A() = I::Test2 {}
   virtual void B() = J::Test2 {}
};
```

## <a name="see-also"></a>另請參閱

[適用於.NET 和 UWP 的元件延伸模組](../windows/component-extensions-for-runtime-platforms.md)