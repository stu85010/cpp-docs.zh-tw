---
title: 位元組索引
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 4e19868e5297e1c1615efabde2aee418bc53c51e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448811"
---
# <a name="byte-indices"></a>位元組索引

使用下列秘訣：

- 使用位元組類索引轉換為字串提供類似於指標操作所造成的問題。 請考慮此範例中，它會掃描反斜線字元的字串：

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   這可能會編製索引後隨位元組，而不是前導位元組，並因此它可能會指向`character`。

- 使用[_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md)解決上述問題的函式：

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   這正確索引前導位元組，因此要`character`。 `_mbclen`函式會判斷字元 （1 或 2 個位元組） 的大小。

## <a name="see-also"></a>另請參閱

[MBCS 程式設計提示](../text/mbcs-programming-tips.md)<br/>
[字串中的最後一個字元](../text/last-character-in-a-string.md)