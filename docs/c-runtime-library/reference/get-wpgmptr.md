---
title: _get_wpgmptr
ms.date: 4/2/2020
api_name:
- _get_wpgmptr
- _o__get_wpgmptr
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
- get_wpgmptr
- _get_wpgmptr
helpviewer_keywords:
- _wpgmptr global variable
- get_wpgmptr function
- wpgmptr global variable
- _get_wpgmptr function
ms.assetid: a77cdd13-2303-4b7c-9a60-8debdbef2011
ms.openlocfilehash: 1e54d3dbdc837c491f5b39d33a9b8197094ac60b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344861"
---
# <a name="_get_wpgmptr"></a>_get_wpgmptr

**_wpgmptr** 전역 변수의 현재 값을 가져옵니다.

## <a name="syntax"></a>구문

```C
errno_t _get_wpgmptr(
   wchar_t **pValue
);
```

### <a name="parameters"></a>매개 변수

*pValue*<br/>
**_wpgmptr** 변수의 현재 값으로 채워질 문자열에 대한 포인터입니다.

## <a name="return-value"></a>Return Value

성공하는 경우 0을 반환하고, 실패하는 경우 오류 코드를 반환합니다. *pValue가* **NULL이면**매개 변수 [유효성 검사에](../../c-runtime-library/parameter-validation.md)설명된 대로 잘못된 매개 변수 처리기가 호출됩니다. 실행을 계속할 수 있는 경우 이 함수는 **errno를** **EINVAL로** 설정하고 **EINVAL**을 반환합니다.

## <a name="remarks"></a>설명

프로그램에 **wmain()** 또는 **wWinMain()과**같은 넓은 진입점이 있는 경우에만 **_get_wpgmptr** 호출합니다. **_wpgmptr** 전역 변수에는 와이드 문자 문자열로 프로세스와 연관된 실행 프로세스에 대한 전체 경로가 포함됩니다. 자세한 내용은 [_pgmptr, _wpgmptr](../../c-runtime-library/pgmptr-wpgmptr.md)를 참조하세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_get_wpgmptr**|\<stdlib.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[_get_pgmptr](get-pgmptr.md)<br/>
