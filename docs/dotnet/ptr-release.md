---
title: ptr::Release
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ptr.Release
- ptr::Release
- msclr.com.ptr.Release
- msclr::com::ptr::Release
helpviewer_keywords:
- Release method
ms.assetid: 7855781e-e4f6-4ad5-86a5-a81e2c3d90db
ms.openlocfilehash: 276d79688213864c31cf04a59f48a8799bf84371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544920"
---
# <a name="ptrrelease"></a>ptr::Release

釋放 COM 物件上擁有的所有參考。

## <a name="syntax"></a>語法

```
void Release();
```

## <a name="remarks"></a>備註

呼叫此函式釋放 COM 物件上的所有已擁有的參考和 COM 物件，若要設定的內部控制代碼`nullptr`。  如果沒有其他 COM 物件上的參考，也會在終結。

## <a name="example"></a>範例

這個範例實作 CLR 類別，此類別使用 `com::ptr` 來包裝其私用成員 `IXMLDOMDocument` 物件。  `ReplaceDocument`成員函式使用`Release`附加新的文件前釋放任何先前的文件物件。

```
// comptr_release.cpp
// compile with: /clr /link msxml2.lib
#include <msxml2.h>
#include <msclr\com\ptr.h>

#import <msxml3.dll> raw_interfaces_only

using namespace System;
using namespace System::Runtime::InteropServices;
using namespace msclr;

// a ref class that uses a com::ptr to contain an
// IXMLDOMDocument object
ref class XmlDocument {
public:
   // construct the internal com::ptr with a null interface
   // and use CreateInstance to fill it
   XmlDocument(String^ progid) {
      m_ptrDoc.CreateInstance(progid);
   }

   // replace currently held COM object with another one
   void ReplaceDocument(IXMLDOMDocument* pDoc) {
      // release current document object
      m_ptrDoc.Release();
      // attach the new document object
      m_ptrDoc.Attach(pDoc);
   }

   // note that the destructor will call the com::ptr destructor
   // and automatically release the reference to the COM object

private:
   com::ptr<IXMLDOMDocument> m_ptrDoc;
};

// unmanaged function that creates a raw XML DOM Document object
IXMLDOMDocument* CreateDocument() {
   IXMLDOMDocument* pDoc = NULL;
   Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,
      CLSCTX_INPROC_SERVER, IID_IXMLDOMDocument, (void**)&pDoc));
   return pDoc;
}

// use the ref class to handle an XML DOM Document object
int main() {
   IXMLDOMDocument* pDoc = NULL;

   try {
      // create the class from a progid string
      XmlDocument doc("Msxml2.DOMDocument.3.0");

      // get another document object from unmanaged function and
      // store it in place of the one held by our ref class
      pDoc = CreateDocument();
      doc.ReplaceDocument(pDoc);
      // no further need for raw object reference
      pDoc->Release();
      pDoc = NULL;
   }
   catch (Exception^ e) {
      Console::WriteLine(e);
   }
   finally {
      if (NULL != pDoc) {
         pDoc->Release();
      }
   }
}
```

## <a name="requirements"></a>需求

**標頭檔** \<msclr\com\ptr.h >

**命名空間**msclr::com

## <a name="see-also"></a>另請參閱

[ptr 成員](../dotnet/ptr-members.md)<br/>
[ptr::Detach](../dotnet/ptr-detach.md)