---
title: strtol、wcstol、_strtol_l、_wcstol_l
ms.date: 11/04/2016
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
ms.openlocfilehash: 73df5dd3ffcd4a9b2fca8b6b713b645ef94addb5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326715"
---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol、wcstol、_strtol_l、_wcstol_l

將字串轉換為長整數值。

## <a name="syntax"></a>語法

```C
long strtol(
   const char *strSource,
   char **endptr,
   int base
);
long wcstol(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long _strtol_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>參數

*strSource*<br/>
以 Null 終止的待轉換字串。

*endptr*<br/>
停止掃描的字元指標。

*base*<br/>
要使用的數字基底。

*locale*<br/>
要使用的地區設定。

## <a name="return-value"></a>傳回值

**strtol**會傳回代表字串中的值*strSource*，但表示法可能造成溢位，當在此情況下它會傳回**LONG_MAX**或**LONG_最小**。 **strtol**會傳回 0，如果可以不執行任何轉換。 **wcstol**傳回值類似**strtol**。 這兩個函式中， **errno**設為**ERANGE**發生溢位或反向溢位。

如需這些傳回碼和其他傳回碼的詳細資訊，請參閱 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>備註

**Strtol**函式會將*strSource*來**長**。 **strtol**停止讀取字串*strSource*它無法辨識為數字一部分的第一個字元。 這可能是終止的 null 字元，或是它可能會大於或等於第一個數字字元*基底*。

**wcstol**是寬字元版本的**strtol**; 其*strSource*引數是寬字元字串。 除此之外，這些函式的行為相同。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

目前的地區設定**LC_NUMERIC**類別設定會決定在基底字元辨識*strSource*; 如需詳細資訊，請參閱[setlocale](setlocale-wsetlocale.md)。 沒有函式 **_l**後置詞使用目前的地區設定，**_strtol_l**並 **_wcstol_l**等於對應的函式，而不需要 **_l**後置詞，只不過它們改用傳入的地區設定。 如需詳細資訊，請參閱 [Locale](../../c-runtime-library/locale.md)。

如果*endptr*不是**NULL**，則停止掃描的字元指標會儲存在所指向位置*endptr*。 如果可以不執行任何轉換 （找不到任何有效的數字或指定無效的基底） 的值*strSource*所指向的位置會儲存*endptr*。

**strtol**預期*strSource*指向下列格式的字串：

> [*空白字元*] [{**+** &#124; **-**}] [**0** [{ **x**&#124; **X** }]] [*位數*&#124; *字母*]  

A*空白字元*可能包含空格和定位字元字元，則會忽略;*數字*是一或多個十進位數字;*字母*是一或多個字母 'a' 到 'z' （或 'A' 到 'Z'）。  不符合此格式的第一個字元會停止掃描。 如果*基底*是介於 2 到 36，則當成基底的數目。 如果*基底*為 0，所指向的字串起始字元*strSource*用來判斷基底。 如果第一個字元為 0，而第二個字元不是 'x' 或 X'，則字串會解譯為八進位整數。 如果第一個字元為 '0'，而第二個字元是 'x' 或 X'，則字串會解譯為十六進位整數。 如果第一個字元為 '1' 到 '9'，則字串會解譯為十進位整數。 字母 'a' 到 'z' (或 'A' 到 'Z') 被指派值 10 到 35，只允許指派值小於 *base* 的字母。 基底範圍外的第一個字元會停止掃描。 例如，如果*基底*為 0 和掃描的第一個字元是 '0'，假設為八進位整數，且 '8' 或 '9' 字元會停止掃描。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> 或 \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>範例

請參閱 [strtod](strtod-strtod-l-wcstod-wcstod-l.md) 的範例。

## <a name="see-also"></a>另請參閱

[資料轉換](../../c-runtime-library/data-conversion.md)<br/>
[地區設定](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[字串轉換為數值函式](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
