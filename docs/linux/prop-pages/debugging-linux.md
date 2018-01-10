---
title: "偵錯工具屬性 (Linux C++) | Microsoft Docs"
ms.custom: 
ms.date: 9/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c1c0fcc-a49b-451c-a5cb-ce9711fac064
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 11ebb11cca19c98bf9f72b9f99f33d66464cd485
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/03/2018
---
# <a name="c-debugging-properties-linux-c"></a>C++ 偵錯工具屬性 (Linux C++)

屬性 | 描述 | 選擇
--- | ---| ---
啟動前命令 | 在偵錯開始前以及執行偵錯工具前，在殼層執行的命令，可用以影響偵錯環境。
計畫 | 在遠端系統上進入要偵測之程式的完整路徑。 此為遠端系統上的路徑。 若保留空白或未變更，則預設為目前的專案輸出。
程式引數 | 要傳遞到正在偵錯之程式的命令列引數。
工作目錄 | 遠端應用程式的工作目錄。 預設為使用者主目錄。
其他偵錯工具命令 | 要讓偵錯工具在開始偵錯之前執行的其他 gdb 命令。
偵錯工具連接埠號碼 | 用來與遠端偵錯工具進行偵錯工具通訊的連接埠號碼。 連接埠號碼不得已經用於本機。 此值必須為介於 1 到 65535 之間的正數。 如未提供，將會使用可用的連接埠號碼。
遠端偵錯工具連接埠號碼 | 遠端偵錯工具伺服器 (gdbserver) 在遠端系統上接聽的連接埠號碼。 連接埠號碼不得已經用於遠端系統。 此值必須為介於 1 到 65535 之間的正數。 如未提供，將會使用 4444 之後的可用連接埠號碼。
偵錯模式 | 指定偵錯工具與 gdb 的互動方式。 在 gdb 模式中，偵錯工具會在遠端系統上將 gdb 帶往殼層。 在 gdbserver 模式中，gdb 會在本機執行，並連線到在遠端執行的 gdbserver。 | **gdbserver**<br>**gdb**<br>
其他符號搜尋路徑 | 偵錯符號的其他搜尋路徑 (solib-search-path)。
偵錯子處理序 | 指定是否要啟用子處理序的偵錯。
啟用 Python 美化顯示 | 啟用運算式值的美化顯示。 只有 gdb 偵錯模式中支援。
視覺效果檔案 | 預設的原生視覺效果檔案 (.natvis)，包含 SLT 類型的視覺效果指示詞。 其他屬於目前解決方案的 .natvis 檔案，將會自動載入。
其他來源檔案路徑對應 | 偵錯工具將 Windows 來源檔案名稱對應至 Linux 來源檔案名稱時，所使用的其他對等路徑。 格式為 "\<windows-path>=\<linux-path>;..."。 如果在 Windows 路徑的來源檔案名稱，也在 Linux 路徑下相同的相對位置中，則會參考該來源檔案名稱。 在本機專案中找到的檔案不需要額外的對應。