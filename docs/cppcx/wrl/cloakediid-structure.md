---
title: CloakedIid 구조체
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 1cc9e79384bbf4aae44199c2f35331e3afd8fd8f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214112"
---
# <a name="cloakediid-structure"></a>CloakedIid 구조체

IID 목록에서 지정 된 인터페이스에 액세스할 수 없는 `RuntimeClass`, `Implements` 및 `ChainInterfaces` 템플릿을 나타냅니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
숨겨진 (숨겨짐) 인터페이스입니다.

## <a name="remarks"></a>주의

다음은 **CloakedIid** 를 사용 하는 방법의 예입니다. `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>상속 계층

`T`

`CloakedIid`

## <a name="requirements"></a>요구 사항

**헤더:** .h를 구현 합니다.

**네임스페이스:** Microsoft::WRL

## <a name="see-also"></a>참고 항목

[Microsoft::WRL 네임스페이스](microsoft-wrl-namespace.md)
