---
title: AsWeak 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: d11f55d57f4053fd6d46b727a8ed91b340d1764b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214177"
---
# <a name="asweak-function"></a>AsWeak 함수

지정된 인스턴스에 대한 약한 참조를 가져옵니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
매개 변수 *p*의 형식에 대 한 포인터입니다.

*p*<br/>
형식의 인스턴스입니다.

*pWeak*<br/>
이 작업이 완료 되 면 매개 변수 *p*에 대 한 약한 참조에 대 한 포인터입니다.

## <a name="return-value"></a>반환 값

S_OK이 작업이 성공 하면이 고, 그렇지 않으면입니다. 그렇지 않으면 실패의 원인을 나타내는 오류 HRESULT가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
