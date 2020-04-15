---
title: _get_doserrno
ms.date: 4/2/2020
api_name:
- _get_doserrno
- _o__get_doserrno
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_doserrno
- get_doserrno
helpviewer_keywords:
- get_doserrno function
- _get_doserrno function
ms.assetid: 7fec7be3-6e39-4181-846b-8ef24489361c
ms.openlocfilehash: 2d5d4e224b39e9fa597e12975d27fa5720fbfbc7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345250"
---
# <a name="_get_doserrno"></a>_get_doserrno

**errno** 값으로 변환되기 전에 운영 체제에서 반환되는 오류 값을 가져옵니다.

## <a name="syntax"></a>구문

```C
errno_t _get_doserrno(
   int * pValue
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
**_doserrno** 전역 매크로의 현재 값으로 채워질 정수에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

**_get_doserrno** 성공하면 0을 반환합니다. 오류가 발생하면 오류 코드를 반환합니다. *pValue가* **NULL이면** [매개 변수 유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL**을 반환합니다.

## <a name="remarks"></a>설명

**_doserrno** 전역 매크로는 프로세스 실행이 시작되기 전에 CRT 초기화 중에 0으로 설정됩니다. 운영 체제 오류를 반환하는 시스템 수준 함수 호출에 의해 반환되는 운영 체제 오류 값으로 설정되며, 실행 중 0으로 다시 설정되지 않습니다. 함수에서 반환되는 오류 값을 확인하기 위해 코드를 작성할 때 함수 호출 전에 [_set_doserrno](set-doserrno.md) 사용하여 항상 **_doserrno** 지웁니다. 다른 함수 호출이 **_doserrno**덮어쓸 수 있으므로 함수 호출 **직후에 _get_doserrno** 사용하여 값을 확인합니다.

휴대용 오류 코드에 대한 **_get_doserrno** 대신 [_get_errno](get-errno.md) 것이 좋습니다.

**_doserrno** 가능한 값은 \<errno.h> 정의됩니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|선택적 헤더|
|-------------|---------------------|---------------------|
|**_get_doserrno**|\<stdlib.h>, \<cstdlib>(C++)|\<errno.h>, \<cerrno>(C++)|

**_get_doserrno** 마이크로 소프트 확장이다. 호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[_set_doserrno](set-doserrno.md)<br/>
[errno, _doserrno, _sys_errlist 및 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
