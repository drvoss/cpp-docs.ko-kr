---
title: RaiseException 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 3270057bf5b1b27a98bef1ab236291eab15d27ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213631"
---
# <a name="raiseexception-function"></a>RaiseException 함수

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>매개 변수

*hr*<br/>
발생 하는 예외의 예외 코드입니다. 즉, 실패 한 작업의 HRESULT입니다.

*dwExceptionFlags*<br/>
비연속적 예외 (플래그 값이 0)를 나타내는 플래그 이거나, 계속할 수 없는 exception (플래그 값이 0이 아닌 경우)입니다. 기본적으로 예외는 계속할 수 없는입니다.

## <a name="remarks"></a>주의

호출 스레드에서 예외를 발생 시킵니다.

자세한 내용은 Windows `RaiseException` 함수를 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:** internal. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
