---
title: _purecall
ms.date: 4/2/2020
api_name:
- _purecall
- _o__purecall
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- purecall
- _purecall
helpviewer_keywords:
- _purecall function
- purecall function
ms.assetid: 56135d9b-3403-4e22-822d-e714523801cc
ms.openlocfilehash: f841bc70a4a5365bb9cc6086dd752bd2a1b583ed
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338478"
---
# <a name="_purecall"></a>_purecall

기본 순수 가상 함수 호출 오류 처리기입니다. 순수 가상 구성원 함수를 호출하면 컴파일러가 이 함수를 호출하는 코드를 생성합니다.

## <a name="syntax"></a>구문

```C
extern "C" int __cdecl _purecall();
```

## <a name="remarks"></a>설명

**_purecall** 함수는 Microsoft C++ 컴파일러의 Microsoft 특정 구현 세부 정보입니다. 이 함수는 코드에서 직접 호출할 수는 없으며 공용 헤더 선언을 포함하지 않습니다. 하지만 C 런타임 라이브러리의 공용 내보내기이므로 이 문서에 포함되어 있습니다.

순수 가상 함수에 대한 호출은 구현이 없으므로 오류입니다. 컴파일러는 순수 가상 함수가 호출될 때 **_purecall** 오류 처리기 함수를 호출하는 코드를 생성합니다. 기본적으로 **_purecall** 프로그램을 종료합니다. 종료하기 전에 **_purecall** 함수는 프로세스에 대해 설정된 경우 **_purecall_handler** 함수를 호출합니다. 순수 가상 함수 호출을 위해 고유한 오류 처리기 함수를 설치하여 디버깅 또는 보고용으로 이러한 호출을 catch할 수 있습니다. 고유한 오류 처리기를 사용하려면 **_purecall_handler** 서명이 있는 함수를 만든 다음 [_set_purecall_handler](get-purecall-handler-set-purecall-handler.md) 사용하여 현재 처리기로 만듭니다.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

**_purecall** 함수에는 헤더 선언이 없습니다. **_purecall_handler** 타입def는 \<stdlib.h> 정의됩니다.

## <a name="see-also"></a>참고 항목

[사전순 함수 참조](crt-alphabetical-function-reference.md)<br/>
[_get_purecall_handler, _set_purecall_handler](get-purecall-handler-set-purecall-handler.md)<br/>
