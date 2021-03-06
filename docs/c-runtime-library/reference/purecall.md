---
title: _purecall
ms.date: 11/04/2016
apiname:
- _purecall
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: a7a6db42dc4b8d9b2962a66c7866aae9db55eb3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541179"
---
# <a name="purecall"></a>_purecall

預設的純虛擬函式呼叫錯誤處理常式。 呼叫純虛擬成員函式時，編譯器會產生程式碼以呼叫此函式。

## <a name="syntax"></a>語法

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>備註

**_Purecall**函式是 Microsoft Visual c + + 編譯器的 Microsoft 特定實作詳細資料。 此函式不是由您的程式碼直接呼叫，而且沒有公用標頭宣告。 因為它是 C 執行階段程式庫的公用匯出，所以會在此進行說明。

呼叫純虛擬函式會產生錯誤，因為它有沒有實作。 編譯器會產生程式碼叫用 **_purecall**錯誤處理常式函式呼叫純虛擬函式時。 根據預設， **_purecall**終止程式。 終止前， **_purecall**函式會叫用 **_purecall_handler**函式在已設定處理程序。 您可以為純虛擬函式呼叫安裝您自己的錯誤處理函式，以攔截它們，用於偵錯或報告目的。 若要使用您自己的錯誤處理常式，建立具有的函式 **_purecall_handler**簽章，然後使用[_set_purecall_handler](get-purecall-handler-set-purecall-handler.md)使它成為目前的處理常式。

## <a name="requirements"></a>需求

**_Purecall**函式沒有標頭宣告。 **_Purecall_handler** typedef 定義於\<stdlib.h >。

## <a name="see-also"></a>另請參閱

[依字母順序排列的函式參考](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler、_set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
