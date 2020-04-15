---
title: _makepath_s, _wmakepath_s
ms.date: 4/2/2020
api_name:
- _wmakepath_s
- _makepath_s
- _o__makepath_s
- _o__wmakepath_s
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath_s
- makepath_s
- _makepath_s
- wmakepath_s
helpviewer_keywords:
- _makepath_s function
- wmakepath_s function
- paths
- _wmakepath_s function
- makepath_s function
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
ms.openlocfilehash: 3a44651cb9ff8be806c45c6b6c5f41f810319a85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341596"
---
# <a name="_makepath_s-_wmakepath_s"></a>_makepath_s, _wmakepath_s

구성 요소에서 경로 이름을 만듭니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_makepath, _wmakepath](makepath-wmakepath.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _makepath_s(
   char *path,
   size_t sizeInBytes,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
errno_t _wmakepath_s(
   wchar_t *path,
   size_t sizeInWords,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
template <size_t size>
errno_t _makepath_s(
   char (&path)[size],
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
); // C++ only
template <size_t size>
errno_t _wmakepath_s(
   wchar_t (&path)[size],
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
); // C++ only
```

### <a name="parameters"></a>매개 변수

*경로*<br/>
전체 경로 버퍼입니다.

*크기인검*<br/>
버퍼의 크기(워드)입니다.

*sizeInBytes*<br/>
버퍼의 크기(바이트)입니다.

*드라이브*<br/>
원하는 드라이브에 따른 문자(A, B 등) 및 후행 콜론(선택 사항)을 포함합니다. **_makepath_s** 콜론이 누락된 경우 복합 경로에 콜론을 자동으로 삽입합니다. *드라이브가* **NULL이거나** 빈 문자열을 가리키는 경우 복합 *경로* 문자열에 드라이브 문자가 나타나지 않습니다.

*dir*<br/>
드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다. 후행 슬래시는 선택 사항이며 정방향 슬래시(/) 또는\\백슬래시() 또는 둘 다 단일 *dir* 인수에서 사용될 수 있습니다. 후행 슬래시(/ 또는 \\)가 지정되지 않은 경우 자동으로 삽입됩니다. *dir이* **NULL이거나** 빈 문자열을 가리키는 경우 복합 *경로* 문자열에 디렉터리 경로가 삽입되지 않습니다.

*fname*<br/>
파일 확장명 없이 기본 파일 이름을 포함합니다. *fname이* **NULL이거나** 빈 문자열을 가리키는 경우 복합 *경로 문자열에* 파일 이름이 삽입되지 않습니다.

*내선*<br/>
앞에 마침표(.)가 있거나 없는 실제 파일 확장명을 포함합니다. **_makepath_s** *내스트에*나타나지 않으면 마침표가 자동으로 삽입됩니다. *내선이* **NULL이거나** 빈 문자열을 가리키는 경우 복합 경로 *문자열에* 확장이 삽입되지 않습니다.

## <a name="return-value"></a>Return Value

성공 시 0이고, 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|*경로*|*크기인단어* / *크기인바이트*|반환 값|*경로의* 내용|
|------------|------------------------------------|------------|------------------------|
|**Null**|any|**아인발 ()에인발 (것)**|수정 안 됨|
|any|<= 0|**아인발 ()에인발 (것)**|수정 안 됨|

위의 오류 조건이 발생하는 경우 이러한 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기를 호출합니다. 실행을 계속할 수 있는 경우 **errno는** **EINVAL로** 설정되고 함수는 **EINVAL을**반환합니다. **NULL은** 매개 변수 *드라이브,* *fname*및 *내면에*대해 허용됩니다. 이러한 매개 변수가 null 포인터 또는 빈 문자열인 동작에 대한 자세한 내용은 설명 섹션을 참조하십시오.

## <a name="remarks"></a>설명

**_makepath_s** 함수는 개별 구성 요소에서 복합 경로 문자열을 만들어 결과를 *경로에*저장합니다. *경로에는* 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장이 포함될 수 있습니다. **_wmakepath_s** **_makepath_s**넓은 문자 버전입니다; **_wmakepath_s** 인수는 와이드 문자 문자열입니다. **_wmakepath_s** **_makepath_s** 다르게 동일하게 행동합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath_s**|**_makepath_s**|**_makepath_s**|**_wmakepath_s**|

*경로* 인수는 전체 경로를 보유할 수 있을 만큼 큰 빈 버퍼를 가리키야 합니다. 복합 *경로는* Stdlib.h에 정의된 **_MAX_PATH** 상수보다 커야 합니다.

경로가 **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 또한 **errno는** **EINVAL로**설정됩니다. **NULL** 값은 다른 모든 매개 변수에 대해 허용됩니다.

C++에서는 템플릿 오버로드로 인해 이러한 함수를 사용하는 것이 보다 간단해 집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으며(크기 인수를 지정할 필요가 없어짐), 기존의 비보안 함수를 보다 최신의 보안 대응 함수로 자동으로 바꿀 수 있습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 먼저 버퍼를 0xFE로 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_makepath_s**|\<stdlib.h>|
|**_wmakepath_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_makepath_s.c

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];
   errno_t err;

   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",
                      "crt_makepath_s", "c" );
   if (err != 0)
   {
      printf("Error creating path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,
                       _MAX_FNAME, ext, _MAX_EXT );
   if (err != 0)
   {
      printf("Error splitting the path. Error code %d.\n", err);
      exit(1);
   }
   printf( "Path extracted with _splitpath_s:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c

Path extracted with _splitpath_s:
   Drive: c:
   Dir: \sample\crt\
   Filename: crt_makepath_s
   Ext: .c
```

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath_s, _wsplitpath_s](splitpath-s-wsplitpath-s.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
