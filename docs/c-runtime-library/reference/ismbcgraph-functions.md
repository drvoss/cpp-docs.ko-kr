---
title: _ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l
ms.date: 4/2/2020
api_name:
- _ismbcpunct_l
- _ismbcblank
- _ismbcprint
- _ismbcgraph_l
- _ismbcblank_l
- _ismbcpunct
- _ismbcprint_l
- _ismbcspace_l
- _ismbcspace
- _ismbcgraph
- _o__ismbcblank
- _o__ismbcblank_l
- _o__ismbcgraph
- _o__ismbcgraph_l
- _o__ismbcprint
- _o__ismbcprint_l
- _o__ismbcpunct
- _o__ismbcpunct_l
- _o__ismbcspace
- _o__ismbcspace_l
api_location:
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbcspace
- _ismbcgraph
- _ismbcpunct
- ismbcspace_l
- ismbcgraph
- _ismbcgraph_l
- _ismbcprint
- _ismbcspace_l
- ismbcprint
- ismbcgraph_l
- ismbcspace
- ismbcpunct
helpviewer_keywords:
- ismbcspace_l function
- _ismbcprint_l function
- ismbcspace function
- ismbcpunct function
- _ismbcspace_l function
- _ismbcprint function
- ismbcprint function
- _ismbcgraph function
- ismbcgraph_l function
- _ismbcpunct_l function
- ismbcpunct_l function
- ismbcprint_l function
- _ismbcpunct function
- ismbcgraph function
- _ismbcgraph_l function
- _ismbcspace function
ms.assetid: 8e0a5f47-ba64-4411-92a3-3c525d16e3be
ms.openlocfilehash: eb76b6ebdbe4b27ce5a7368ad1b8c2dd8f858d85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343236"
---
# <a name="_ismbcgraph-_ismbcgraph_l-_ismbcprint-_ismbcprint_l-_ismbcpunct-_ismbcpunct_l-_ismbcblank-_ismbcblank_l-_ismbcspace-_ismbcspace_l"></a>_ismbcgraph, _ismbcgraph_l, _ismbcprint, _ismbcprint_l, _ismbcpunct, _ismbcpunct_l, _ismbcblank, _ismbcblank_l, _ismbcspace, _ismbcspace_l

문자가 그래픽 문자, 표시 문자, 문장 부호 문자 또는 공백 문자인지 여부를 확인합니다.

> [!IMPORTANT]
> 이 API는 Windows 런타임에서 실행되는 애플리케이션에서 사용할 수 없습니다. 자세한 내용은 [유니버설 Windows 플랫폼 앱에서 지원되지 않는 CRT 함수](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _ismbcgraph(
   unsigned int c
);
int _ismbcgraph_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcprint(
   unsigned int c
);
int _ismbcprint_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcpunct(
   unsigned int c
);
int _ismbcpunct_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcblank(
   unsigned int c
);
int _ismbcblank_l(
   unsigned int c,
   _locale_t locale
);
int _ismbcspace(
   unsigned int c
);
int _ismbcspace_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>매개 변수

*C*<br/>
확인할 문자입니다.

*로캘*<br/>
사용할 로캘입니다.

## <a name="return-value"></a>Return Value

이러한 각 루틴은 문자가 테스트 조건을 만족하는 경우 0이 아닌 값을 반환하고, 그렇지 않으면 0을 반환합니다. *c* <= 255이고 해당 **_ismbb** 루틴이 있는 경우(예: **_ismbcalnum** **_ismbbalnum**해당 루틴에 해당 **_ismbb** 루틴의 반환 값) 결과입니다.

이러한 함수의 버전은 **동일하지만 _l** 접미사가 있는 함수는 현재 로캘 대신 로캘 종속 동작에 대해 전달된 로캘을 사용합니다. 자세한 내용은 [Locale](../../c-runtime-library/locale.md)을 참조하세요.

## <a name="remarks"></a>설명

이러한 각 함수는 지정한 조건에 대해 주어진 멀티바이트 문자를 테스트합니다.

|루틴에서 반환된 값|테스트 조건|932 코드 페이지 예제|
|-------------|--------------------|---------------------------|
|**_ismbcgraph**|Graphic|*c가* 공백()을 제외한 ASCII 또는 카타카나 인쇄 가능한 문자의 단일 바이트 표현인 경우에만 비영점을 반환합니다.|
|**_ismbcprint**|인쇄 가능|*c가* 공백()을 포함한 ASCII 또는 카타카나 인쇄 가능한 문자의 단일 바이트 표현인 경우에만 비영도반환합니다.|
|**_ismbcpunct**|문장 부호|*c가* ASCII 또는 katakana 문장 부호 문자의 단일 바이트 표현인 경우에만 비영점을 반환합니다.|
|**_ismbcblank**|공백 또는 가로 탭|*c가* 공백 또는 가로 탭 문자인 경우에만 0이 아닌 경우 를 반환합니다: *c*=0x20 또는 *c*=0x09.|
|**_ismbcspace**|공백|*c가* 공백 문자인 경우에만 비영도를 반환합니다: *c*=0x20 또는 0x09<=*c*<=0x0D입니다.|

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_ismbcgraph**|\<mbstring.h>|
|**_ismbcgraph_l**|\<mbstring.h>|
|**_ismbcprint**|\<mbstring.h>|
|**_ismbcprint_l**|\<mbstring.h>|
|**_ismbcpunct**|\<mbstring.h>|
|**_ismbcpunct_l**|\<mbstring.h>|
|**_ismbcblank**|\<mbstring.h>|
|**_ismbcblank_l**|\<mbstring.h>|
|**_ismbcspace**|\<mbstring.h>|
|**_ismbcspace_l**|\<mbstring.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="libraries"></a>라이브러리

모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.

## <a name="see-also"></a>참고 항목

[문자 분류](../../c-runtime-library/character-classification.md)<br/>
[로캘](../../c-runtime-library/locale.md)<br/>
[다중 바이트 문자 시퀀스의 해석](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_ismbc 루틴](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw 루틴](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb 루틴](../../c-runtime-library/ismbb-routines.md)<br/>
