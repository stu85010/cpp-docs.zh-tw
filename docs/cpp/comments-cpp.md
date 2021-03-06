---
title: 註解 （c + +）
ms.date: 11/04/2016
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
ms.openlocfilehash: a90d9d37e69cb2e8be4ab18f77026fdce1221307
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506102"
---
# <a name="comments-c"></a>註解 （c + +）

註解是會被編譯器忽略，但對程式設計人員而言很有用的文字。 註解通常用來標註程式碼供未來參考。 編譯器會將它們視為空白字元。 您可以使用在測試中的註解來停用特定行程式碼;不過， `#if` / `#endif`效果更好，前置處理器指示詞，這因為您可以圍繞包含註解的程式碼，但您無法巢狀註解。

C++ 註解以下列其中一種方式撰寫：

- `/*` (斜線、星號) 字元，後面接著任何字元序列 (包括新行)，後面接著 `*/` 字元。 這語法與 ANSI C 相同。

- `//` (兩個斜線) 字元，後面接著任何字元序列。 一個沒有前置反斜線的新行會終止這種形式的註解。 因此，它通常稱為「單行註解」。

註解字元 (`/*`、`*/` 和 `//`) 在字元常數、字串常值或註解中沒有特殊意義。 因此，使用第一種語法的註解不可以是巢狀。

## <a name="see-also"></a>另請參閱

[語彙慣例](../cpp/lexical-conventions.md)