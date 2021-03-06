---
title: _strtime_s、_wstrtime_s
ms.date: 11/04/2016
apiname:
- _wstrtime_s
- _strtime_s
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wstrtime_s
- strtime_s
- wstrtime_s
- _strtime_s
helpviewer_keywords:
- wstrtime_s function
- copying time to buffers
- strtime_s function
- _wstrtime_s function
- time, copying
- _strtime_s function
ms.assetid: 42acf013-c334-485d-b610-84c0af8a46ec
ms.openlocfilehash: 579c4a99b52c66bd14cea947eaa1f301cc1127e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642360"
---
# <a name="strtimes-wstrtimes"></a>_strtime_s、_wstrtime_s

將目前的時間複製到緩衝區。 這些版本的 [_strtime、_wstrtime](strtime-wstrtime.md) 具有 [CRT 的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述的安全性增強功能。

## <a name="syntax"></a>語法

```C
errno_t _strtime_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrtime_s(
   wchar_t *buffer,
   size_t numberOfElements
);
template <size_t size>
errno_t _strtime_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrtime_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>參數

*buffer*<br/>
長度至少為 10 個位元組的緩衝區內會寫入時間。

*numberOfElements*<br/>
緩衝區的大小。

## <a name="return-value"></a>傳回值

如果成功，則為零。

如果發生錯誤，會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果失敗，傳回的值會是錯誤碼。 錯誤碼在 EERRNO.H 中定義，請參閱下表查看此函式產生的確切錯誤。 如需錯誤碼的詳細資訊，請參閱 [errno 常數](../../c-runtime-library/errno-constants.md)。

### <a name="error-conditions"></a>錯誤狀況

|*buffer*|*numberOfElements*|Return|內容*緩衝區*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(任何)|**EINVAL**|未修改|
|不**NULL** （指向有效的緩衝區）|0|**EINVAL**|未修改|
|不**NULL** （指向有效的緩衝區）|0 < 大小 < 9|**EINVAL**|空字串|
|不**NULL** （指向有效的緩衝區）|大小 > 9|0|目前的時間格式一如＜備註＞所指定|

## <a name="security-issues"></a>安全性問題

傳入無效的非**NULL**值，如果緩衝區會造成存取違規*numberOfElements*參數大於 9。

傳遞的值*numberOfElements*大於緩衝區的實際大小會導致緩衝區溢位。

## <a name="remarks"></a>備註

這些函式提供更安全的版本[_strtime](strtime-wstrtime.md)並[_wstrtime](strtime-wstrtime.md)。 **_Strtime_s**函式會將目前的當地時間複製到所指向的緩衝區*timestr*。 時間格式為**hh: mm:** 其中**hh**是代表小時以 24 小時制標記法中，兩位數**mm**是兩位數表示過去與小時、分鐘**ss**是兩位數表示秒數。 例如，字串**18:23:44**代表 23 分 44 秒下午 6 點 緩衝區必須至少有 9 個位元組長，實際大小由第二個參數指定。

**_wstrtime**是寬字元版本的 **_strtime**; 的引數和傳回值 **_wstrtime**是寬字元字串。 除此之外，這些函式的行為相同。

C++ 利用多載樣板簡化了這些函式的使用方式。多載可自動推斷緩衝區長度 (因而不須指定大小引數)，也可以將不安全的舊函式自動取代成較新且安全的對應函式。 如需詳細資訊，請參閱 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)。

### <a name="generic-text-routine-mapping"></a>一般文字常式對應

|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrtime_s**|**_strtime_s**|**_strtime_s**|**_wstrtime_s**|

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_strtime_s**|\<time.h>|
|**_wstrtime_s**|\<time.h> 或 \<wchar.h>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

```C
// strtime_s.c

#include <time.h>
#include <stdio.h>

int main()
{
    char tmpbuf[9];
    errno_t err;

    // Set time zone from TZ environment variable. If TZ is not set,
    // the operating system is queried to obtain the default value
    // for the variable.
    //
    _tzset();

    // Display operating system-style date and time.
    err = _strtime_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
      exit(1);
    }
    printf( "OS time:\t\t\t\t%s\n", tmpbuf );
    err = _strdate_s( tmpbuf, 9 );
    if (err)
    {
       printf("_strdate_s failed due to an invalid argument.");
       exit(1);
    }
    printf( "OS date:\t\t\t\t%s\n", tmpbuf );

}
```

```Output
OS time:            14:37:49
OS date:            04/25/03
```

## <a name="see-also"></a>另請參閱

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime、_mktime32、_mktime64](mktime-mktime32-mktime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
