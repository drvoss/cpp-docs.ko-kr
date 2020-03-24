---
title: EnableIf 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: 44c6293b56e9e03c23d0d8cebf2a112e6fcf3664
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214034"
---
# <a name="enableif-structure"></a>EnableIf 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
형식입니다.

*b*<br/>
부울 식입니다.

## <a name="remarks"></a>주의

첫 번째 템플릿 매개 변수가 **true**로 평가 되는 경우 두 번째 템플릿 매개 변수로 지정 된 형식의 데이터 멤버를 정의 합니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 형식 정의

|이름|설명|
|----------|-----------------|
|`type`|템플릿 매개 변수 *b* 가 **true**로 평가 되는 경우 부분 특수화는 `T`형식으로 `type` 데이터 멤버를 정의 합니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`EnableIf`

## <a name="requirements"></a>요구 사항

**헤더:** internal. h

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
