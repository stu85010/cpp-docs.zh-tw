---
title: _chsize_s
ms.date: 11/04/2016
apiname:
- _chsize_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- chsize_s
- _chsize_s
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
ms.openlocfilehash: a56efe826d43c80dc2cdee295e58872e7dd3c9ea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597596"
---
# <a name="chsizes"></a>_chsize_s

變更檔案大小。 這是具有 [CRT 中的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述之安全性增強功能的 [_chsize](chsize.md) 版本。

## <a name="syntax"></a>語法

```C
errno_t _chsize_s(
   int fd,
   __int64 size
);
```

### <a name="parameters"></a>參數

*fd*<br/>
參考已開啟檔案的檔案描述項。

*size*<br/>
檔案的新長度 (位元組)。

## <a name="return-value"></a>傳回值

**_chsize_s**傳回值為 0，如果已成功變更檔案大小。 非零的傳回值表示發生錯誤： 傳回的值是**EACCES**指定的檔案鎖定的存取，如果**EBADF**如果指定的檔案是唯讀或描述元無效**ENOSPC**如果沒有空間保留在裝置上，或**EINVAL**如果大小小於零。 **errno**設為相同的值。

如需有關這些傳回碼和其他傳回碼的詳細資訊，請參閱 [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>備註

**_Chsize_s**函式擴充或截斷與相關聯的檔案*fd*所指定的長度*大小*。 檔案必須以允許寫入的模式開啟。 如果擴充檔案，則會附加 Null 字元 ('\0')。 如果檔案遭到截斷，則會遺失從縮短檔案結尾到檔案原始長度的所有資料。

**_chsize_s**採用 64 位元整數，與檔案大小，並因此可以處理大於 4 GB 檔案大小。 **_chsize**限制為 32 位元檔案大小。

這個函式會驗證它的參數。 如果*fd*不是有效的檔案描述項或大小小於零，會叫用無效參數處理常式，如中所述[參數驗證](../../c-runtime-library/parameter-validation.md)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|選擇性標頭|
|-------------|---------------------|---------------------|
|**_chsize_s**|\<io.h>|\<errno.h>|

如需相容性的詳細資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[檔案處理](../../c-runtime-library/file-handling.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
