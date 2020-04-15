---
title: _open_osfhandle
ms.date: 4/2/2020
api_name:
- _open_osfhandle
- _o__open_osfhandle
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
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 16966bedd80dc90eaa89ee46e6b633a9cf7af74f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338554"
---
# <a name="_open_osfhandle"></a>_open_osfhandle

C 런타임 파일 설명자는 기존 운영 체제 파일 핸들과 연결됩니다.

## <a name="syntax"></a>구문

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>매개 변수

*osfhandle*<br/>
운영 체제 파일 핸들입니다.

*플래그*<br/>
허용되는 연산의 유형입니다.

## <a name="return-value"></a>Return Value

정상적으로 실행되면 **_open_osfhandle**은 C 런타임 파일 설명자를 반환합니다. 그렇지 않으면 -1을 반환합니다.

## <a name="remarks"></a>설명

**_open_osfhandle** 함수는 C 런타임 파일 설명자가 할당됩니다. 이 파일 설명자는 *osfhandle*에서 지정한 운영 체제 파일 핸들과 연결됩니다. 컴파일러 경고를 방지하려면 *osfhandle* 인수를 **HANDLE**에서 **intptr_t**로 캐스팅합니다. *플래그* 인수는 \<fcntl.h>에 정의된 매니페스트 상수 중 하나 이상으로 구성된 정수 식입니다. 비트-OR 연산자(&#124;)를 사용하여 두 개 이상의 매니페스트 상수를 결합하여 *플래그* 인수를 형성할 수 있습니다. **&#124;**

매니페스트 상수는 \<fcntl.h>에 정의되어 있습니다.

|||
|-|-|
| **\_O\_부속** | 모든 쓰기 작업 전에 파일 포인터를 파일 끝에 배치합니다. |
| **\_O\_RDONLY** | 읽기 전용으로 파일을 엽니다. |
| **\_O\_텍스트** | 파일을 텍스트(변환됨) 모드에서 엽니다. |
| **\_O\_WTEXT** | 파일을 유니코드(변환된 UTF-16) 모드에서 엽니다. |

**_open_osfhandle** 호출이 Win32 파일 핸들의 소유권을 파일 설명자로 전송합니다. **_open_osfhandle**을 사용하여 열린 파일을 닫으려면 [\_닫기](close.md)를 호출합니다. 기본 OS 파일 핸들도 **_close**에 대한 호출에 의해 닫힙니다. 원래 핸들에 있는 Win32 함수 **CloseHandle**을 호출하지 마세요. FILE &#42;**스트림에서** 파일 설명자가 소유인 경우 파일 설명자와 기본 핸들을 모두 [닫습니다.](fclose-fcloseall.md) 이 경우 파일 설명자의 **_close** 또는 원래 핸들의 **CloseHandle**을 호출하지 마세요.

기본적으로 이 함수의 전역 상태는 응용 프로그램에 대한 범위가 조정됩니다. 이를 변경하려면 [CRT의 전역 상태를](../global-state.md)참조하십시오.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

호환성에 대한 자세한 내용은 [Compatibility](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)
