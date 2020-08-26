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
ms.openlocfilehash: c66710fe31b5a657a4976bea7f0aa52aac3e3825
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88837088"
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
   int data_byte
);
unsigned short _outpw(
   unsigned short port,
   unsigned short data_word
);
unsigned long _outpd(
   unsigned short port,
   unsigned long data_word
);
```

### <a name="parameters"></a>매개 변수

*포트인*\
포트 번호입니다.

*data_byte, data_word*\
출력 값입니다.

## <a name="return-value"></a>반환 값

함수는 데이터 출력을 반환합니다. 오류가 반환 되지 않습니다.

## <a name="remarks"></a>설명

`_outp`, `_outpw`및 `_outpd` 함수는 바이트, 워드 및 2배 워드를 각각 지정된 출력 포트에 씁니다. *Port* 인수는 0-65535 범위의 부호 없는 정수 일 수 있습니다. 0-255 범위의 정수 *data_byte* 수 있습니다. *data_word* 정수, 부호 없는 short 정수 및 부호 없는 정수 (정수)의 범위에 있는 임의의 값일 수 있습니다.

이러한 함수는 i/o 포트에 직접 쓰기 때문에 사용자 모드 Windows 코드에서 사용할 수 없습니다.

Windows 운영 체제에서 i/o 포트를 사용 하는 방법에 대 한 자세한 내용은 [직렬 통신](/previous-versions/ff802693(v=msdn.10))을 참조 하세요.

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
[`inp`, `inpw`, `_inp`, `_inpw`, `_inpd`](../c-runtime-library/inp-inpw-inpd.md)
