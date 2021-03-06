---
title: 移植協力廠商程式庫
ms.date: 01/10/2017
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
ms.openlocfilehash: 1abd7f05614317237c911ceb69c243211a373e34
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658298"
---
# <a name="porting-third-party-libraries"></a>移植協力廠商程式庫

將專案升級至目前版本的 Visual C++ 時，也需要升級專案所使用的任何程式庫，以使用相同的版本和利用編譯器來建置程式庫和您的專案。 (如需詳細資訊，請參閱[潛在升級問題概觀](overview-of-potential-upgrade-issues-visual-cpp.md))。

## <a name="introducing-vcpkg"></a>vcpkg 簡介

過去，尋找和升級協力廠商程式庫有時是非 trivial 工作。 為了更輕鬆地取得和重建 C++ 協力廠商的開放原始碼程式庫，Visual C++ 小組已建立稱為 **VC++ 封裝工具**或 **vcpkg** 的命令列工具。 Vcpkg 具有許多常見 C++ 開放原始碼程式庫的可搜尋目錄。 您可以直接從 vcpkg 命令列於目錄中安裝任何程式庫。 安裝程式庫時，vcpkg 會在電腦上建立目錄樹狀結構，並在此資料夾中新增 .h、.lib 和二進位檔。 您可以在編譯命令列中使用此資料夾，或使用 vcpkg 整合安裝命令將它整合到 Visual Studio 2015 或以上版本。 整合程式庫位置之後，Visual Studio 可以找到它，並將它新增至您建立的任何新專案。 若要使用程式庫，只要對其使用 `#include`，Visual Studio 就會自動將 .lib 路徑新增到專案設定，並將 dll 複製到解決方案資料夾。 如需詳細資訊，請參閱 [vcpkg：C++ 的套件管理員](../vcpkg.md)。

## <a name="reporting-issues"></a>回報問題

如果您的程式庫不存在於 **vcpkg** 目錄中，則可以在 [GitHub 存放庫](https://github.com/Microsoft/vcpkg/issues)提出問題，社群和 Visual C++ 小組可在該處看到問題，並可能會建立此程式庫的移植檔。

針對專屬協力廠商程式庫 (非開放程式碼)，建議您連絡程式庫提供者。 不過，我們有興趣知道您正在使用和無法使用的任何專屬程式庫，請讓我們知道您依存的程式庫 (您可以透過 vcupgrade@microsoft.com 連絡我們)。

## <a name="see-also"></a>請參閱

[Visual C++ 移植和升級指南](visual-cpp-porting-and-upgrading-guide.md)