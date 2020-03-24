---
title: Move 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
ms.openlocfilehash: 65fe85e95453165430c7ef3cfd4c4bb2babd9868
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213709"
---
# <a name="move-function"></a>Move 함수

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template<class T>
inline typename RemoveReference<T>::Type&& Move(
   _Inout_ T&& arg
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인수 형식입니다.

*arg*<br/>
이동할 인수입니다.

## <a name="return-value"></a>반환 값

참조 또는 rvalue 참조 특성 (있는 경우)에 대 한 매개 변수 *인수가* 제거 되었습니다.

## <a name="remarks"></a>주의

지정 된 인수를 한 위치에서 다른 위치로 이동 합니다.

자세한 내용은 [Rvalue 참조 선언 자: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)의 **의미 체계 이동** 섹션을 참조 하세요.

## <a name="requirements"></a>요구 사항

**헤더:** internal. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
