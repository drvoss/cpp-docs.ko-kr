---
title: _access, _waccess
ms.date: 4/2/2020
api_name:
- _access
- _waccess
- _o__access
- _o__waccess
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
- _waccess
- _access
- taccess
- waccess
- _taccess
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
ms.openlocfilehash: 98726726e14aacec75ed99adfa33016b40affd17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350869"
---
# <a name="_access-_waccess"></a>_access, _waccess

파일이 읽기 전용인지 아닌지를 확인합니다. 더 안전한 버전을 사용할 수 있습니다. [_access_s, _waccess_s](access-s-waccess-s.md)를 참조하세요.

## <a name="syntax"></a>구문

```C
int _access(
   const char *path,
   int mode
);
int _waccess(
   const wchar_t *path,
   int mode
);
```

### <a name="parameters"></a>매개 변수

*경로*<br/>
파일 또는 디렉터리 경로입니다.

*모드*<br/>
읽기/쓰기 특성입니다.

## <a name="return-value"></a>Return Value

파일에 지정된 모드가 있으면 각 함수는 0을 반환합니다. 명명된 파일이 없거나 지정된 모드가 없는 경우 함수는 -1을 반환합니다. 이 경우 `errno` 다음 표와 같이 설정됩니다.

|||
|-|-|
`EACCES`|액세스 거부됨: 파일의 권한 설정이 지정된 액세스를 허용하지 않습니다.
`ENOENT`|파일 이름 또는 경로를 찾을 수 없습니다.
`EINVAL`|잘못된 매개 변수입니다.

이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [_doserrno, errno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)를 참조하세요.

## <a name="remarks"></a>설명

파일과 함께 사용할 경우 **_access** 함수는 지정된 파일 또는 디렉터리존재 여부를 결정하고 *모드*값으로 지정된 특성을 가시고 있습니다. 디렉터리와 함께 사용할 경우 **_access** 지정된 디렉터리가 있는지 여부만 결정합니다. Windows 2000 및 이후 운영 체제에서는 모든 디렉터리에서 읽기 및 쓰기 액세스 권한을 갖습니다.

|*모드* 값|파일 검사|
|------------------|---------------------|
|00|존재만|
|02|쓰기 전용|
|04|읽기 전용|
|06|읽기 및 쓰기|

이 함수는 파일과 디렉터리가 읽기 전용인지 아닌지만 확인하고, 파일 시스템 보안 설정은 확인하지 않습니다. 이를 확인하려면 액세스 토큰이 필요합니다. 파일 시스템 보안에 대한 자세한 내용은 [액세스 토큰](/windows/win32/SecAuthZ/access-tokens)을 참조하세요. 이 기능을 제공하기 위해 ATL 클래스가 존재합니다. [CAccessToken 클래스](../../atl/reference/caccesstoken-class.md)를 참조하세요.

**_waccess** **_access**와이드 문자 버전입니다. **_waccess** *경로* 인수는 와이드 문자 문자열입니다. **_waccess** **_access** 다르게 행동합니다.

이 함수는 해당 매개 변수의 유효성을 검사합니다. *경로가* NULL이거나 *모드가* 유효한 모드를 지정하지 않으면 [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 계속해서 실행하도록 허용된 경우 함수가 `errno`를 `EINVAL`로 설정하고 -1을 반환합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|Tchar.h 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|--------------------------------------|--------------------|-----------------------|
|`_taccess`|**_access**|**_access**|**_waccess**|

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|----------------------|
|**_access**|\<io.h>|\<errno.h>|
|**_waccess**|\<wchar.h> 또는 \<io.h>|\<errno.h>|

## <a name="example"></a>예제

다음 예제에서는 **_access** 사용하여 crt_ACCESS 라는 파일을 확인합니다. C는 그것이 존재하는지 여부와 쓰기가 허용되는지 여부를 확인합니다.

```C
// crt_access.c
// compile with: /W1
// This example uses _access to check the file named
// crt_ACCESS.C to see if it exists and if writing is allowed.

#include  <io.h>
#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    // Check for existence.
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )
    {
        printf_s( "File crt_ACCESS.C exists.\n" );

        // Check for write permission.
        // Assume file is read-only.
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );
    }
}
```

```Output
File crt_ACCESS.C exists.
File crt_ACCESS.C does not have write permission.
```

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat 함수](stat-functions.md)
