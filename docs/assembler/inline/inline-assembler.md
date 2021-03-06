---
title: 內嵌組合語言
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++]
- assembler [C++], inline
- assembly language [C++], inline
- inline assembler [C++]
- inline assembly [C++]
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
ms.openlocfilehash: f2be42cd5ab4d335d076a1eb4627c41f5b340350
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529281"
---
# <a name="inline-assembler"></a>內嵌組合語言

**Microsoft 專屬**

組合語言用於許多用途，例如改善程式速度、減少記憶體需求，以及控制硬體。 您可以使用內嵌組合語言，直接在 C 和 C++ 原始程式中內嵌組譯語言指令，而不需要額外的組譯和連結步驟。 內嵌組合語言已內建於編譯器，因此您不需要個別的組譯工具，例如 Microsoft Macro Assembler (MASM)。

> [!NOTE]
>  包含內嵌組譯程式碼的程式無法完全移植到其他硬體平台。 如果您為可攜性設計，請避免使用內嵌組譯工具。

內嵌組譯碼不支援 ARM 和 x64 處理器。  下列主題說明如何搭配 x86 處理器使用 Visual C/C++ 內嵌組合語言：

- [內嵌組合語言概觀](../../assembler/inline/inline-assembler-overview.md)

- [內嵌組譯碼的優點](../../assembler/inline/advantages-of-inline-assembly.md)

- [__asm](../../assembler/inline/asm.md)

- [在 __asm 區塊中使用組合語言](../../assembler/inline/using-assembly-language-in-asm-blocks.md)

- [在 __asm 區塊中使用 C 或 C++](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)

- [在內嵌組譯碼中使用和保留暫存器](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)

- [跳至內嵌組譯碼中的標籤](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)

- [在內嵌組譯碼中呼叫 C 函式](../../assembler/inline/calling-c-functions-in-inline-assembly.md)

- [在內嵌組譯碼中呼叫 C++ 函式](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)

- [將 __asm 區塊定義為 C 巨集](../../assembler/inline/defining-asm-blocks-as-c-macros.md)

- [最佳化內嵌組譯碼](../../assembler/inline/optimizing-inline-assembly.md)

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建和組件語言](../../intrinsics/compiler-intrinsics-and-assembly-language.md)<br/>
[C++ 語言參考](../../cpp/cpp-language-reference.md)<br/>