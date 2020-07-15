---
title: outp, outp, _outp, _outpw, _outpd
description: Microsoft CRT (C 런타임 라이브러리)의 사용 되지 않는 및 제거 된 outp, outp, _outp, _outpw 및 _outpd 함수에 대해 설명 합니다.
ms.date: 12/09/2019
api_name:
- _outpd
- _outp
- _outpw
- outp
- outpw
api_location:
- msvcrt.dll
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _outpw
- _outpd
- _outp
- outp
- outpw
- outpd
helpviewer_keywords:
- outpw function
- words
- _outpd function
- outpd function
- outp function
- ports, writing bytes at
- bytes, writing to ports
- words, writing to ports
- double words
- double words, writing to ports
- _outpw function
- _outp function
ms.assetid: c200fe22-41f6-46fd-b0be-ebb805b35181
ms.openlocfilehash: 0d28511cdf7487226635c0317b7c0ba21ab1d1be
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373478"
---
# <a name="outp-outpw-_outp-_outpw-_outpd"></a>outp, outp, _outp, _outpw, _outpd

포트에서 바이트 ( `outp` , `_outp` ), 단어 ( `outpw` , `_outpw` ) 또는 더블 워드 ()를 출력 `_outpd` 합니다.

> [!IMPORTANT]
> 이러한 함수는 사용되지 않습니다. Visual Studio 2015부터 CRT에서 사용할 수 없습니다.
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```cpp
int _outp(
   unsigned short port,
   int databyte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short dataword
);
unsigned long _outpd(
   unsigned short port,
   unsigned long dataword
);
```

### <a name="parameters"></a>매개 변수

*포트인*\
포트 번호입니다.

*속한 임의의 dataword, dataword*\
출력 값입니다.

## <a name="return-value"></a>반환 값

함수는 데이터 출력을 반환합니다. 반환되는 오류가 없습니다.

## <a name="remarks"></a>설명

`_outp`, `_outpw`및 `_outpd` 함수는 바이트, 워드 및 2배 워드를 각각 지정된 출력 포트에 씁니다. *port* 인수는 0-65,535 범위에 속한 임의의 부호 없는 정수일 수 있고 *databyte*는 0–255 범위에 속한 임의의 정수일 수 있으며 *dataword*는 각각 정수, 부호 없는 정수(Short) 및 부호 없는 정수(Long) 범위에 속한 임의의 값일 수 있습니다.

이러한 함수는 i/o 포트에 직접 쓰기 때문에 사용자 모드 Windows 코드에서 사용할 수 없습니다. Windows 운영 체제에서 i/o 포트를 사용 하는 방법에 대 한 자세한 내용은 [직렬 통신](https://docs.microsoft.com/previous-versions/ff802693(v=msdn.10))을 참조 하세요.

및 `outp` `outpw` 이름은 이전 버전의 및 함수에 사용 되지 않는 이름입니다 `_outp` `_outpw` . 자세한 내용은 [POSIX 함수 이름](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md#posix-function-names)을 참조 하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|`_outp`|\<conio.h>|
|`_outpw`|\<conio.h>|
|`_outpd`|\<conio.h>|

호환성에 대한 자세한 내용은 [Compatibility](../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고 항목

[콘솔 및 포트 i/o](../c-runtime-library/console-and-port-i-o.md)\
[sct.inp, inpw, _inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)
