---
title: 略過序列化機制
ms.date: 11/04/2016
helpviewer_keywords:
- archive objects [MFC]
- bypassing serialization
- archives [MFC], serialization
- serialization [MFC], bypassing
- archives [MFC]
- serialization [MFC], role of framework
- serialization [MFC], overriding
ms.assetid: 48d4a279-b51c-4ba5-81cd-ed043312b582
ms.openlocfilehash: 4c76be874752a577aaeb4c3641818f8a2850b465
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556594"
---
# <a name="bypassing-the-serialization-mechanism"></a>略過序列化機制

如您所見，架構提供了預設的方式從檔案讀取和寫入資料。 將封存物件序列化符合許許多多應用程式的需求。 這類應用程式會將檔案完全讀入記憶體，讓使用者更新檔案，然後再將更新的版本寫入磁碟。

不過，部分應用程式是以非常不同的方式處理資料，而對這些應用程式將封存序列化就不適當。 範例包含資料庫程式、僅編輯大型檔案的一部分的程式、僅寫入純文字檔的程式以及共用資料檔的程式。

在這些情況下，您可以覆寫[Serialize](../mfc/reference/cobject-class.md#serialize)函式，以不同方式來斡旋檔案動作，透過[CFile](../mfc/reference/cfile-class.md)物件而非[CArchive](../mfc/reference/carchive-class.md)物件。

您可以使用`Open`， `Read`， `Write`， `Close`，並`Seek`類別成員函式`CFile`開啟檔案，檔案指標移到 （搜尋） 至檔案中的特定點讀取資料錄 （指定的位元組數目)，可讓使用者更新記錄，然後再次搜尋到相同的點，並寫回至檔案記錄。 架構會為您開啟檔案，所以您可以使用類別 `GetFile` 的 `CArchive` 成員函式取得 `CFile` 物件的指標。 對於更複雜且彈性的用途，您可以覆寫[OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument)並[OnSaveDocument](../mfc/reference/cdocument-class.md#onsavedocument)類別成員函式`CWinApp`。 如需詳細資訊，請參閱類別[CFile](../mfc/reference/cfile-class.md)中*MFC 參考 》*。

在此案例中，您的 `Serialize` 覆寫不會執行任何動作，除非例如您在文件關閉時要其讀取和寫入檔案標頭以使其保持最新。

## <a name="see-also"></a>另請參閱

[使用文件](../mfc/using-documents.md)

