---
title: __getmainargs、__wgetmainargs
ms.date: 11/04/2016
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
ms.openlocfilehash: 6e2bf21f2ac50d3486af56f9581ff6c8d0e0c309
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523334"
---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs、__wgetmainargs

叫用命令列剖析，並將 `main()` 的引數複製回傳入的指標。

## <a name="syntax"></a>語法

```cpp
int __getmainargs(
    int * _Argc,
   char *** _Argv,
   char *** _Env,
   int _DoWildCard,
_startupinfo * _StartInfo);

int __wgetmainargs (
   int *_Argc,
   wchar_t ***_Argv,
   wchar_t ***_Env,
   int _DoWildCard,
   _startupinfo * _StartInfo)
```

#### <a name="parameters"></a>參數

`_Argc`<br/>
包含 `argv` 之後引數數目的整數。 `argc` 參數永遠會大於或等於 1。

`_Argv`<br/>
以 null 終止之字串的陣列，表示由程式的使用者所輸入的命令列引數。 依照慣例，`argv[0]` 是對程式叫用的命令，argv[1] 是第一個命令列引數，依此類推，直到 argv[argc]，其永遠為 **NULL**。 第一個命令列引數一定是 `argv[1]`，而最後一個是 `argv[argc - 1]`。

`_Env`<br/>
字串陣列，表示在使用者環境中設定的變數。 這個陣列由 **NULL** 項目終止。

`_DoWildCard`<br/>
整數，如果設定為 1 會在命令列引數中展開萬用字元，或設為 0 不執行任何動作。

`_StartInfo`<br/>
要傳遞給 CRT DLL 的其他資訊。

## <a name="return-value"></a>傳回值

如果成功則傳回 0，如果失敗則為負值。

## <a name="remarks"></a>備註

在非寬字元的平台上使用 `__getmainargs`，在寬字元 (Unicode) 平台上使用 `__wgetmainargs`。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|__getmainargs|internal.h|
|__wgetmainargs|internal.h|