---
title: 2.7.2.1 private
ms.date: 11/04/2016
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
ms.openlocfilehash: c1a2560eb80c848605698c435e3a0f0f7e66b75a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536951"
---
# <a name="2721-private"></a>2.7.2.1 private

`private`子句宣告為私用小組的每個執行緒的變數清單中的變數。 語法`private`子句如下所示：

```
private(variable-list)
```

中指定的變數的行為`private`子句如下所示。 具有自動儲存期的新物件配置的建構。 大小和新物件的對齊會取決於變數的類型。 此配置發生一次在小組中，每個執行緒和預設建構函式會叫用類別物件，如有必要，否則的初始值為未定。  原始變數所參考的物件具有不定值的建構的項目、 動態建構的範圍內，不得修改和不定值從建構在結束時。

中的指示詞的建構之語彙範圍內，變數會參考新的私用物件配置的執行緒。

若要限制`private`子句如下所示：

- 中指定的類別類型的變數`private`子句必須具有可存取且明確的預設建構函式。

- 中指定的變數`private`子句不能有**const**-限定型別，除非它具有類型的類別`mutable`成員。

- 中指定的變數`private`子句不能是不完整的類型或參考型別。

- 在出現的變數`reduction`子句**平行**指示詞中不能指定`private`繫結至平行建構之工作共用指示詞子句。