---
title: _splitpath_s, _wsplitpath_s
ms.date: 4/2/2020
api_name:
- _wsplitpath_s
- _splitpath_s
- _o__splitpath_s
- _o__wsplitpath_s
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
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
ms.openlocfilehash: 364544a9423668494747405e801d59b73de4e6c6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355627"
---
# <a name="_splitpath_s-_wsplitpath_s"></a>_splitpath_s, _wsplitpath_s

경로 이름을 구성 요소로 분해합니다. 이러한 함수는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에 설명된 대로 강화된 보안 기능이 있는 [_splitpath, _wsplitpath](splitpath-wsplitpath.md)의 버전입니다.

## <a name="syntax"></a>구문

```C
errno_t _splitpath_s(
   const char * path,
   char * drive,
   size_t driveNumberOfElements,
   char * dir,
   size_t dirNumberOfElements,
   char * fname,
   size_t nameNumberOfElements,
   char * ext,
   size_t extNumberOfElements
);
errno_t _wsplitpath_s(
   const wchar_t * path,
   wchar_t * drive,
   size_t driveNumberOfElements,
   wchar_t *dir,
   size_t dirNumberOfElements,
   wchar_t * fname,
   size_t nameNumberOfElements,
   wchar_t * ext,
   size_t extNumberOfElements
);
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _splitpath_s(
   const char *path,
   char (&drive)[drivesize],
   char (&dir)[dirsize],
   char (&fname)[fnamesize],
   char (&ext)[extsize]
); // C++ only
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>
errno_t _wsplitpath_s(
   const wchar_t *path,
   wchar_t (&drive)[drivesize],
   wchar_t (&dir)[dirsize],
   wchar_t (&fname)[fnamesize],
   wchar_t (&ext)[extsize]
); // C++ only
```

### <a name="parameters"></a>매개 변수

*경로*<br/>
전체 경로입니다.

*드라이브*<br/>
드라이브 문자, 콜론 **(:**). 드라이브 문자가 필요하지 않은 경우 이 매개 변수에 대해 **NULL을** 전달할 수 있습니다.

*드라이브번호원엘리먼트*<br/>
단일 바이트 또는 넓은 문자의 *드라이브* 버퍼 크기입니다. *드라이브가* **NULL이면**이 값은 0이어야 합니다.

*dir*<br/>
후행 슬래시를 포함한 디렉터리 경로입니다. 앞으로 슬래시 **/** (), 백 **\\** 래쉬 (), 또는 둘 다 사용할 수 있습니다. 디렉터리 경로가 필요하지 않은 경우 이 매개 변수에 대해 **NULL을** 전달할 수 있습니다.

*디르넘원엘리먼트*<br/>
단일 바이트 또는 넓은 문자의 *dir* 버퍼 크기입니다. *dir이* **NULL인**경우 이 값은 0이어야 합니다.

*fname*<br/>
확장명이 없는 기본 파일 이름입니다. 파일 이름이 필요하지 않은 경우 이 매개 변수에 대해 **NULL을** 전달할 수 있습니다.

*이름번호원엘리먼트*<br/>
단일 바이트 또는 넓은 문자의 *fname* 버퍼 크기입니다. *fname이* **NULL이면**이 값은 0이어야 합니다.

*내선*<br/>
선행 기간 **(.**.)을 포함한 파일 이름 확장자. 파일 이름 확장명을 필요로 하지 않는 경우 이 매개 변수에 대해 **NULL을** 전달할 수 있습니다.

*내스트 넘버오브엘리먼트*<br/>
단일 바이트 또는 넓은 문자의 *내선* 버퍼 크기입니다. *내전이* **NULL이면**이 값은 0이어야 합니다.

## <a name="return-value"></a>Return Value

성공 시 0이고, 실패 시 오류 코드입니다.

### <a name="error-conditions"></a>오류 조건

|조건|Return Value|
|---------------|------------------|
|*경로가* **NULL입니다.**|**아인발 ()에인발 (것)**|
|*드라이브는* **NULL,** *드라이브번호OfElements는* 0이 아닙니다.|**아인발 ()에인발 (것)**|
|*드라이브가* **null이**아닌 *드라이브번호OfElements는* 0입니다.|**아인발 ()에인발 (것)**|
|*dir은* **NULL,** *dirNumberOfElements는* 0이 아닙니다.|**아인발 ()에인발 (것)**|
|*dir은* **null이**아닌, *dirNumberOfElements는* 0입니다.|**아인발 ()에인발 (것)**|
|*fname은* **NULL,** *nameNumberOfElements는* 0이 아닙니다.|**아인발 ()에인발 (것)**|
|*fname은* **null이**아닌 *이름, nameNumberOfElements는* 0입니다.|**아인발 ()에인발 (것)**|
|*내선 번호는* **NULL,** *내선 번호OfElements는* 0이 아닙니다.|**아인발 ()에인발 (것)**|
|*내선 번호는* **null이**아닌, *내선 번호OfElements는* 0입니다.|**아인발 ()에인발 (것)**|

이러한 조건 중 하나라도 발생하는 경우, [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이러한 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL을**반환합니다.

버퍼 중 어느 것도 결과를 보유하기에 너무 짧으면 이러한 함수는 모든 버퍼를 빈 문자열로 지우고 **errno를** **ERANGE로**설정하고 **ERANGE를**반환합니다.

## <a name="remarks"></a>설명

**_splitpath_s** 함수는 경로를 네 개의 구성 요소로 나눕습니다. **_splitpath_s** 현재 사용 중인 다중 바이트 코드 페이지에 따라 다중 바이트 문자 시퀀스를 인식하여 적절한 다중 바이트 문자열 인수를 자동으로 처리합니다. **_wsplitpath_s** **_splitpath_s**와이드 문자 버전입니다. **_wsplitpath_s** 인수는 와이드 문자 문자열입니다. 그 외의 경우에는 이들 함수가 동일하게 동작합니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

### <a name="generic-text-routine-mappings"></a>제네릭 텍스트 라우팅 매핑

|TCHAR.H 루틴|_UNICODE 및 _MBCS 정의되지 않음|_MBCS 정의됨|_UNICODE 정의됨|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsplitpath_s**|**_splitpath_s**|**_splitpath_s**|**_wsplitpath_s**|

전체 경로의 각 구성 요소는 별도의 버퍼에 저장됩니다. 매니페스트 상수는 **_MAX_DRIVE,** **_MAX_DIR,** **_MAX_FNAME**및 _MAX_EXT(STDLIB에 정의됩니다. **_MAX_EXT** H) 각 파일 구성 요소에 대해 허용되는 최대 크기를 지정합니다. 해당 매니페스트 상수보다 큰 파일 구성 요소가 있으면 힙이 손상됩니다.

다음 표에는 매니페스트 상수의 값이 나와 있습니다.

|이름|값|
|----------|-----------|
|_MAX_DRIVE|3|
|_MAX_DIR|256|
|_MAX_FNAME|256|
|_MAX_EXT|256|

전체 경로에 구성 요소(예: 파일 이름)가 포함되어 있지 않으면 해당 버퍼에 빈 문자열을 할당할 **_splitpath_s** 있습니다.

C++에서는 템플릿 오버로드를 통해 이러한 함수를 사용하는 것이 더욱 간단해집니다. 오버로드는 버퍼 길이를 자동으로 유추할 수 있으므로 크기 인수를 지정할 필요가 없습니다. 자세한 내용은 [안전한 템플릿 오버로드](../../c-runtime-library/secure-template-overloads.md)를 참조하세요.

이러한 함수의 디버그 라이브러리 버전은 먼저 버퍼를 0xFE로 채웁니다. 이 동작을 사용하지 않으려면 [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)를 사용하세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_splitpath_s**|\<stdlib.h>|
|**_wsplitpath_s**|\<stdlib.h> 또는 \<wchar.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[_makepath_s, _wmakepath_s](makepath-s-wmakepath-s.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[_splitpath, _wsplitpath](splitpath-wsplitpath.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_makepath, _wmakepath](makepath-wmakepath.md)<br/>
[_setmbcp](setmbcp.md)<br/>
