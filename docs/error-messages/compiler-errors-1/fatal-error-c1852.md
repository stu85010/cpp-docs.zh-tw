---
title: 嚴重錯誤 C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 895c2fc988c9566f9e50b1ac1a18eb4dc1c6661a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601496"
---
# <a name="fatal-error-c1852"></a>嚴重錯誤 C1852

'filename' 是無效的先行編譯標頭檔

檔案不是先行編譯標頭檔。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>透過檢查下列可能原因進行修正

1. 使用 **/Yu** 或 **#pragma hdrstop**指定的檔案無效。

1. 如果您未指定副檔名，編譯器會假設副檔名為 .pch。