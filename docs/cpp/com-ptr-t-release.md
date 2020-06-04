---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: 73de3c2d19063f0738b8b0a3c510ea520f58de0b
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745064"
---
# <a name="_com_ptr_trelease"></a>_com_ptr_t::Release

**마이크로소프트 특정**

캡슐화된 **Release** 인터페이스 포인터의 `IUnknown` 릴리스 멤버 함수를 호출합니다.

## <a name="syntax"></a>구문

```cpp
void Release( );
```

## <a name="remarks"></a>설명

캡슐화된 인터페이스 포인터를 호출하여 `IUnknown::Release` 이 `E_POINTER` 인터페이스 포인터가 NULL인 경우 오류가 발생합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
