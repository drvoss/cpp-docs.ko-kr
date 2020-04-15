---
title: gets_s, _getws_s
ms.date: 4/2/2020
api_name:
- _getws_s
- gets_s
- _o__getws_s
- _o_gets_s
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getws_s
- gets_s
helpviewer_keywords:
- getws_s function
- _getws_s function
- lines, getting
- streams, getting lines
- buffers, avoiding overruns
- buffer overruns
- buffers, buffer overruns
- gets_s function
- standard input, reading from
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
ms.openlocfilehash: aac64a42a2979623f4314f7bf28d7e4917eaee18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344211"
---
# <a name="gets_s-_getws_s"></a>gets_s, _getws_s

**stdin** 스트림에서 선을 가져옵니다. 이러한 버전의 [gets, _getws](../../c-runtime-library/gets-getws.md)에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 포함되어 있습니다.

## <a name="syntax"></a>구문

```C
char *gets_s(
   char *buffer,
   size_t sizeInCharacters
);
wchar_t *_getws_s(
   wchar_t *buffer,
   size_t sizeInCharacters
);
```

```cpp
template <size_t size>
char *gets_s( char (&buffer)[size] ); // C++ only

template <size_t size>
wchar_t *_getws_s( wchar_t (&buffer)[size] ); // C++ only
```

### <a name="parameters"></a>매개 변수

*버퍼*<br/>
입력 문자열에 대한 스토리지 위치입니다.

*sizeInCharacters*<br/>
버퍼의 크기입니다.

## <a name="return-value"></a>Return Value

성공하면 *버퍼를* 반환합니다. **NULL** 포인터는 오류 또는 파일 끝 조건을 나타냅니다. 어떤 것이 발생했는지 확인하려면 [ferror](ferror.md) 또는 [feof](feof.md) 를 사용하십시오.

## <a name="remarks"></a>설명

**gets_s** 함수는 표준 입력 스트림 **stdin에서** 선을 읽고 *버퍼에*저장합니다. 줄은 첫 번째 줄 바꿈 문자('\n')까지 모든 문자로 구성됩니다. **그런** 다음 gets_s 줄을 반환하기 전에 줄 바호 문자를 null 문자('\0')로 바꿉니다. 반대로 **fgets_s** 함수는 줄 바선 문자를 유지합니다.

첫 번째 문자 읽기가 파일 끝 문자인 경우 null 문자는 *버퍼의* 시작 부분에 저장되고 **NULL이** 반환됩니다.

**_getws_s** **gets_s**와이드 문자 버전입니다. 인수 및 반환 값은 와이드 문자 문자열입니다.

*버퍼가* **NULL** 또는 *sizeInCharacters가* 0보다 작거나 같거나 버퍼가 너무 작아서 입력 줄과 null 종단자를 포함하지 않는 경우 이러한 함수는 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 이러한 함수는 **NULL을** 반환하고 errno를 **ERANGE로**설정합니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_getts_s**|**gets_s**|**gets_s**|**_getws_s**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**gets_s**|\<stdio.h>|
|**_getws_s**|\<stdio.h> 또는 \<wchar.h>|

콘솔은 UWP(유니버설 Windows 플랫폼) 앱에서 지원되지 않습니다. 콘솔, **stdin,** **stdout**및 **stderr와**연결된 표준 스트림 핸들은 C 런타임 함수가 UWP 앱에서 사용하기 전에 리디렉션되어야 합니다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_gets_s.c
// This program retrieves a string from the stdin and
// prints the same string to the console.

#include <stdio.h>

int main( void )
{
   char line[21]; // room for 20 chars + '\0'
   gets_s( line, 20 );
   printf( "The line entered was: %s\n", line );
}
```

```Input
Hello there!
```

```Output
The line entered was: Hello there!
```

## <a name="see-also"></a>참고 항목

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[도착, _getws](../../c-runtime-library/gets-getws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[puts, _putws](puts-putws.md)<br/>
