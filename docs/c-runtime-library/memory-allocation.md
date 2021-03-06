---
title: 記憶體配置
ms.date: 11/04/2016
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
ms.openlocfilehash: e77548e9f85057f8e8a1c92e4a0aa904a58e14a6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618773"
---
# <a name="memory-allocation"></a>記憶體配置

使用這些常式配置、釋放及重新配置記憶體。

## <a name="memory-allocation-routines"></a>記憶體配置常式

|常式傳回的值|使用|
|-------------|---------|
|[_alloca](../c-runtime-library/reference/alloca.md)、[_malloca](../c-runtime-library/reference/malloca.md)|配置堆疊的記憶體|
|[calloc](../c-runtime-library/reference/calloc.md)|配置陣列的記憶體，將配置的區塊中的每個位元組初始化為 0|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|偵錯版本的 **calloc**；僅適用於偵錯版本的執行階段程式庫|
|[operator delete](../c-runtime-library/operator-delete-crt.md)|釋放配置的區塊|
|[operator delete&#91;&#93;](../c-runtime-library/delete-operator-crt.md)|釋放配置的區塊|
|[_expand](../c-runtime-library/reference/expand.md)|以不移動的方式展開或壓縮記憶體區塊|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|偵錯版本的 **_expand**；僅適用於偵錯版本的執行階段程式庫|
|[free](../c-runtime-library/reference/free.md)|釋放配置的區塊|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|偵錯版本的 **free**；僅適用於偵錯版本的執行階段程式庫|
|[_freea](../c-runtime-library/reference/freea.md)|從堆疊釋放配置的區塊|
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|取得 CRT 堆積的 Win32 HANDLE|
|[_heapadd](../c-runtime-library/heapadd.md)|將記憶體加入堆積|
|[_heapchk](../c-runtime-library/reference/heapchk.md)|檢查堆積的一致性|
|[_heapmin](../c-runtime-library/reference/heapmin.md)|釋放堆積中未使用的記憶體|
|[_heapset](../c-runtime-library/heapset.md)|使用指定的值填寫釋放堆積項目|
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|傳回堆積中每個項目的資訊|
|[malloc](../c-runtime-library/reference/malloc.md)|配置堆積中的記憶體區塊|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|偵錯版本的 **malloc**；僅適用於偵錯版本的執行階段程式庫|
|[_msize](../c-runtime-library/reference/msize.md)|傳回配置的區塊大小|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|偵錯版本的 **_msize**；僅適用於偵錯版本的執行階段程式庫|
|[new](../c-runtime-library/operator-new-crt.md)|配置堆積中的記憶體區塊|
|[new&#91;&#93;](../c-runtime-library/new-operator-crt.md)|配置堆積中的記憶體區塊|
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|傳回 **_set_new_handler** 所設定之目前新處理常式的位址|
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|傳回整數，此整數表示 **_set_new_mode** 為 **malloc** 所設定的新處理常式模式|
|[realloc](../c-runtime-library/reference/realloc.md)|將區塊重新配置為新的大小|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|偵錯版本的 **realloc**；僅適用於偵錯版本的執行階段程式庫|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|當 **new** 運算子 (為了配置記憶體) 失敗時，啟用錯誤處理機制，並啟用 C++ 標準程式庫的編譯|
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|為 **malloc** 設定新處理常式模式|

## <a name="see-also"></a>請參閱

[依類別排序的通用 C 執行階段常式](../c-runtime-library/run-time-routines-by-category.md)<br/>
