---
title: 遠端封存屬性 (C++ Linux)
ms.date: 9/26/2017
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: bcd0e0eef16addc60743000b6ed8cba12276e29c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50439218"
---
# <a name="remote-archive-properties-c-linux"></a>遠端封存屬性 (C++ Linux)

屬性 | 描述
--- | ---
建立封存索引 | 建立封存索引 (cf. ranlib)。  如此可加速連結作業，並降低其本身程式庫內出現相依性。
建立精簡型封存 | 建立精簡型封存。  精簡型封存包含物件的相對路徑，而不會內嵌物件。  必須刪除現有程式庫，才可於精簡型和一般型之間切換。
建立時不發出警告 | 不要在建立程式庫時發出警告。
截斷時間戳記 | 在時間戳記與 UID/GID 使用零。
隱藏啟動橫幅 | 不要顯示版本號碼。
詳細資訊 | 詳細資訊
其他選項 | 其他選項。
輸出檔案 | /OUT 選項會覆寫 lib 所建立的程式之預設名稱與位置。
封存工具 | 指定在連結靜態物件期間要叫用的程式，或遠端系統上封存工具的路徑。
封存工具逾時 | 遠端封存工具逾時 (毫秒)。
複製輸出 | 指定是否要從遠端系統，將組建輸出檔案複製到本機電腦。
