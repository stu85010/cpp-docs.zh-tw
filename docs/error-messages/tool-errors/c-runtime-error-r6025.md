---
title: C 執行階段錯誤 R6025
ms.date: 11/04/2016
f1_keywords:
- R6025
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
ms.openlocfilehash: 461bfb2aa46053ec56fff67de70038b1fcd97389
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639558"
---
# <a name="c-runtime-error-r6025"></a>C 執行階段錯誤 R6025

純虛擬函式呼叫

> [!NOTE]
> 如果您遇到這個錯誤訊息時執行應用程式時，應用程式已關閉發生內部問題。 此錯誤最常見的原因是應用程式或已損毀的安裝中的 bug。
>
> 您可以嘗試進行下列步驟來修正這個錯誤：
>
> - 使用**應用程式和功能**或是**程式和功能**頁面**控制台**修復或重新安裝程式。
> - 請檢查**Windows Update**中**控制台**軟體更新。
> - 檢查應用程式的更新版本。 如果問題持續發生，請連絡應用程式廠商。

**適用於程式設計人員的資訊**

任何具有已具現化物件來處理純虛擬函式呼叫。

此錯誤被因為是抽象的基底類別，透過指標由衍生類別中的型別轉換，但實際上是基底類別的指標呼叫虛擬函式。 發生於從轉型**void** <strong>\*</strong>類別的指標時**void** <strong>\*</strong>已在基底類別的建構期間建立。

