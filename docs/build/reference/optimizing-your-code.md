---
title: 最佳化程式碼
ms.date: 12/28/2017
helpviewer_keywords:
- performance, optimizing code
- optimization
- cl.exe compiler, performance
- optimization, C++ code
- code, optimizing
- performance, compiler
ms.openlocfilehash: d490bd704c53a160ee36dea0fd24a52211bfdc37
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525511"
---
# <a name="optimizing-your-code"></a>最佳化您的程式碼

藉由最佳化可執行檔，您可以達到快速的執行速度和小型的程式碼大小之間取得平衡。 本主題會討論一些可協助您最佳化程式碼的 Visual c + + 提供的機制。

## <a name="language-features"></a>語言功能

下列主題會描述一些在 C/c + + 語言中的最佳化功能。

[最佳化 Pragma 和關鍵字](../../build/reference/optimization-pragmas-and-keywords.md)<br/>
關鍵字和 pragma 可用於您的程式碼以提升效能的清單。

[依分類排列的編譯器選項](../../build/reference/compiler-options-listed-by-category.md)<br/>
一份 **/O**編譯器選項會明確影響執行速度或程式碼大小。

[右值參考宣告子：&&](../../cpp/rvalue-reference-declarator-amp-amp.md)<br/>
右值參考支援實作*移動語意*。 如果移動語意用來實作樣板程式庫，使用這些範本的應用程式的效能可大幅提升。

### <a name="the-optimize-pragma"></a>最佳化 pragma

如果最佳化的一段程式碼會導致錯誤或速度變慢，您可以使用[最佳化](../../preprocessor/optimize.md)pragma，來關閉該區段的最佳化功能。

將兩個 pragma，之間的程式碼，如下所示：

```cpp
#pragma optimize("", off)
// some code here
#pragma optimize("", on)
```

## <a name="programming-practices"></a>程式設計做法

當您編譯您的程式碼最佳化時，您可能會注意到其他警告訊息。 因為有些警告只與最佳化的程式碼，就會發生此行為。 如果您注意下列警告，您可以避免許多最佳化問題。

不合常理，最佳化的程式速度可能會導致執行速度變慢的程式碼。 這是因為某些速度最佳化作業增加程式碼大小。 例如，內嵌函式的函式呼叫的額外負荷。 不過，內嵌太多程式碼可能會讓您的程式大虛擬記憶體分頁的數目錯誤會增加。 因此，排除函式呼叫所獲得的速度可能會遺失記憶體交換。

下列主題討論的良好程式設計作法。

[改善時間關鍵程式碼的秘訣](../../build/reference/tips-for-improving-time-critical-code.md)<br/>
更好程式碼撰寫技術，可以產生較佳的效能。 本主題建議程式碼撰寫技術，可協助您確保您的程式碼的時間關鍵部分令人滿意。

[最佳化最佳做法](../../build/reference/optimization-best-practices.md)<br/>
提供有關如何最佳化您的應用程式的一般指導方針。

## <a name="debugging-optimized-code"></a>偵錯最佳化程式碼

因為最佳化可能會變更編譯器所建立的程式碼，我們建議您偵錯您的應用程式，並測量其效能，並再將程式碼最佳化。

下列主題提供有關如何偵錯的基本資訊。

- [Visual Studio 偵錯](/visualstudio/debugger/debugging-in-visual-studio)

- [建立發行組建時的常見問題](../../build/reference/common-problems-when-creating-a-release-build.md)

下列主題提供有關如何偵錯更進階的資訊。

- [如何：偵錯最佳化程式碼](/visualstudio/debugger/how-to-debug-optimized-code)

- [浮點數會失去精確度的原因](../../build/reference/why-floating-point-numbers-may-lose-precision.md)

下列主題提供如何最佳化建置、 載入和執行您的程式碼的相關資訊。

- [改善編譯器輸送量](../../build/reference/improving-compiler-throughput.md)

- [使用不帶 () 的函式名稱不會產生程式碼](../../build/reference/using-function-name-without-parens-produces-no-code.md)

- [最佳化內嵌組譯碼](../../assembler/inline/optimizing-inline-assembly.md)

- [指定 ATL 專案的編譯器最佳化](../../atl/reference/specifying-compiler-optimization-for-an-atl-project.md)

- [若要改善用戶端應用程式的效能，載入時應該使用何項最佳化技術？](../../build/dll-frequently-asked-questions.md#mfc_optimization)

## <a name="see-also"></a>另請參閱

[C/C++ 建置參考](../../build/reference/c-cpp-building-reference.md)
