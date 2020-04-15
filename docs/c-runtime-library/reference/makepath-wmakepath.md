---
title: _makepath, _wmakepath
ms.date: 4/2/2020
api_name:
- _makepath
- _wmakepath
- _o__makepath
- _o__wmakepath
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
ms.openlocfilehash: b92e056816183b4bbb07edb3efec4415655d655e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341588"
---
# <a name="_makepath-_wmakepath"></a>_makepath, _wmakepath

구성 요소에서 경로 이름을 만듭니다. 이러한 함수의 더 안전한 버전을 사용할 수 있습니다. [_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
void _makepath(
   char *path,
   const char *drive,
   const char *dir,
   const char *fname,
   const char *ext
);
void _wmakepath(
   wchar_t *path,
   const wchar_t *drive,
   const wchar_t *dir,
   const wchar_t *fname,
   const wchar_t *ext
);
```

### <a name="parameters"></a>매개 변수

*경로*<br/>
전체 경로 버퍼입니다.

*드라이브*<br/>
원하는 드라이브에 따른 문자(A, B 등) 및 후행 콜론(선택 사항)을 포함합니다. **_makepath** 콜론이 누락된 경우 복합 경로에 콜론을 자동으로 삽입합니다. *드라이브가* **NULL이거나** 빈 문자열을 가리키는 경우 복합 *경로* 문자열에 드라이브 문자가 나타나지 않습니다.

*dir*<br/>
드라이브 지정자 또는 실제 파일 이름을 제외한 디렉터리의 경로를 포함합니다. 후행 슬래시는 선택 사항이며 정방향 슬래시(/) 또는\\백슬래시() 또는 둘 다 단일 *dir* 인수에서 사용될 수 있습니다. 후행 슬래시(/ 또는 \\)가 지정되지 않은 경우 자동으로 삽입됩니다. *dir이* **NULL이거나** 빈 문자열을 가리키는 경우 복합 *경로* 문자열에 디렉터리 경로가 삽입되지 않습니다.

*fname*<br/>
파일 확장명 없이 기본 파일 이름을 포함합니다. *fname이* **NULL이거나** 빈 문자열을 가리키는 경우 복합 *경로 문자열에* 파일 이름이 삽입되지 않습니다.

*내선*<br/>
앞에 마침표(.)가 있거나 없는 실제 파일 확장명을 포함합니다. **_makepath** *내스트에*나타나지 않으면 마침표가 자동으로 삽입됩니다. *내선이* **NULL이거나** 빈 문자열을 가리키는 경우 복합 경로 *문자열에* 확장이 삽입되지 않습니다.

## <a name="remarks"></a>설명

**_makepath** 함수는 개별 구성 요소에서 복합 경로 문자열을 만들어 결과를 *경로에*저장합니다. *경로에는* 드라이브 문자, 디렉터리 경로, 파일 이름 및 파일 이름 확장이 포함될 수 있습니다. **_wmakepath** **_makepath**와이드 문자 버전입니다. **_wmakepath** 인수는 와이드 문자 문자열입니다. **_wmakepath** **_makepath** 달리 동일하게 행동합니다.

**보안 정보** null로 끝나는 문자열을 사용하세요. 버퍼 오버런을 방지하려면 null-종료된 문자열이 *경로* 버퍼의 크기를 초과해서는 안 됩니다. **_makepath** 복합 경로 문자열의 길이가 **_MAX_PATH**초과하지 않도록 하지 않습니다. 자세한 내용은 [버퍼 오버런 방지](/windows/win32/SecBP/avoiding-buffer-overruns)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmakepath**|**_makepath**|**_makepath**|**_wmakepath**|

*경로* 인수는 전체 경로를 보유할 수 있을 만큼 큰 빈 버퍼를 가리키야 합니다. 복합 *경로는* Stdlib.h에 정의된 **_MAX_PATH** 상수보다 커야 합니다.

경로가 **NULL인**경우 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 또한 **errno는** **EINVAL로**설정됩니다. **NULL** 값은 다른 모든 매개 변수에 대해 허용됩니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_makepath**|\<stdlib.h>|
|**_wmakepath**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

```C
// crt_makepath.c
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char path_buffer[_MAX_PATH];
   char drive[_MAX_DRIVE];
   char dir[_MAX_DIR];
   char fname[_MAX_FNAME];
   char ext[_MAX_EXT];

   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996
   // Note: _makepath is deprecated; consider using _makepath_s instead
   printf( "Path created with _makepath: %s\n\n", path_buffer );
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996
   // Note: _splitpath is deprecated; consider using _splitpath_s instead
   printf( "Path extracted with _splitpath:\n" );
   printf( "   Drive: %s\n", drive );
   printf( "   Dir: %s\n", dir );
   printf( "   Filename: %s\n", fname );
   printf( "   Ext: %s\n", ext );
}
```

```Output
Path created with _makepath: c:\sample\crt\makepath.c

Path extracted with _splitpath:
   Drive: c:
   Dir: \sample\crt\
   Filename: makepath
   Ext: .c
```

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)<br/>
