---
title: InterfaceList 구조체
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
ms.openlocfilehash: 7fd06f71bc4d8097366dc0e87d7ff92c5a12a790
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213865"
---
# <a name="interfacelist-structure"></a>InterfaceList 구조체

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.

## <a name="syntax"></a>구문

```cpp
template <typename T, typename U>
struct InterfaceList;
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인터페이스 이름입니다. 재귀 목록의 첫 번째 인터페이스입니다.

*U*<br/>
인터페이스 이름입니다. 재귀 목록의 나머지 인터페이스입니다.

## <a name="remarks"></a>주의

재귀 인터페이스 목록을 만드는 데 사용 됩니다.

## <a name="members"></a>멤버

### <a name="public-typedefs"></a>공용 형식 정의

|이름|설명|
|----------|-----------------|
|`FirstT`|템플릿 매개 변수 *T*의 동의어입니다.|
|`RestT`|템플릿 매개 변수 *U*의 동의어입니다.|

## <a name="inheritance-hierarchy"></a>상속 계층

`InterfaceList`

## <a name="requirements"></a>요구 사항

**헤더:** .h를 구현 합니다.

**네임 스페이스:** Microsoft:: WRL::D etails

## <a name="see-also"></a>참고 항목

[Microsoft::WRL::Details 네임스페이스](microsoft-wrl-details-namespace.md)
