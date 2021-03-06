---
title: _tempnam_dbg、_wtempnam_dbg
ms.date: 11/04/2016
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
ms.openlocfilehash: 804c8ad1f17c6ee1df563cafc69ee7aef494d1cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596452"
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg、_wtempnam_dbg

函式的版本[_tempnam、 _wtempnam、 tmpnam、 _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)使用的偵錯版本**malloc**， **_malloc_dbg**。

## <a name="syntax"></a>語法

```C
char *_tempnam_dbg(
   const char *dir,
   const char *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wtempnam_dbg(
   const wchar_t *dir,
   const wchar_t *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>參數

*dir*<br/>
若沒有 TMP 環境變數，或是 TMP 不是有效的目錄時，檔案名稱中所使用的路徑。

*prefix*<br/>
將會附加至所傳回的名稱的字串 **_tempnam**。

*blockType*<br/>
要求的記憶體區塊類型： **_CLIENT_BLOCK**或是 **_NORMAL_BLOCK**。

*filename*<br/>
要求配置作業的原始程式檔名稱的指標或**NULL**。

*linenumber*<br/>
其中要求配置作業的原始程式檔中的行號或**NULL**。

## <a name="return-value"></a>傳回值

每個函式會傳回產生的名稱的指標或**NULL**失敗時。 如果沒有在 TMP 環境變數和指定了無效的目錄名稱，就會發生失敗*dir*參數。

> [!NOTE]
> **免費**(或**free_dbg**) 需要配置的指標呼叫 **_tempnam_dbg**並 **_wtempnam_dbg**。

## <a name="remarks"></a>備註

**_Tempnam_dbg**並 **_wtempnam_dbg**函式 **_tempnam**並 **_wtempnam**不同之處在於，當 **_DEBUG**是定義，這些函式使用的偵錯版本**malloc**並 **_malloc_dbg**來配置記憶體，如果**NULL**是作為第一個參數進行傳遞。 如需詳細資訊，請參閱 [_malloc_dbg](malloc-dbg.md)。

在大多數情況中，您不需要明確地呼叫這些函式。 相反地，您可以在其中定義的旗標 **_CRTDBG_MAP_ALLOC**。 當 **_CRTDBG_MAP_ALLOC**定義，呼叫 **_tempnam**並 **_wtempnam**重新對應至 **_tempnam_dbg**和 **_wtempnam_dbg**分別與*blockType*設定為 **_NORMAL_BLOCK**。 因此，您不需要明確呼叫這些函式，除非您想要將標示為堆積區塊 **_CLIENT_BLOCK**。 如需詳細資訊，請參閱[偵錯堆積上的區塊類型](/visualstudio/debugger/crt-debug-heap-details)。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_tempnam_dbg**， **_wtempnam_dbg**|\<crtdbg.h>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[資料流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[堆積配置函式的偵錯版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
