---
title: .FPO
ms.date: 08/30/2018
f1_keywords:
- .FPO
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
ms.openlocfilehash: 83d6e81ea7dd35038f27f2721f3cc41fe49ef1bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570494"
---
# <a name="fpo"></a>.FPO

。FPO 指示詞會控制偵錯記錄至.debug$ F 區段或區段的發出。

## <a name="syntax"></a>語法

> FPO (*cdwLocals*， *cdwParams*， *cbProlog*， *cbRegs*， *fUseBP*， *cbFrame*)

### <a name="parameters"></a>參數

*cdwLocals*<br/>
本機變數，不帶正負號的 32 位元值數目。

*cdwParams*<br/>
DWORD，不帶正負號的 16 位元值參數的大小。

*cbProlog*<br/>
在函式初構程式碼，不帶正負號的 8 位元值的位元組數目。

*cbRegs*<br/>
數字儲存的暫存器。

*fUseBP*<br/>
指出是否已配置的 ebp 暫存器。 0 或 1。

*cbFrame*<br/>
指出畫面格型別。  請參閱[FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data)如需詳細資訊。

## <a name="see-also"></a>另請參閱

[指示詞參考](../../assembler/masm/directives-reference.md)<br/>