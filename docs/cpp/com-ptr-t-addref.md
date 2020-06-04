---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 4dcf643357c9b368d4b2ea3bc51e6567acf45a44
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745097"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**마이크로소프트 특정**

캡슐화된 `AddRef` 인터페이스 `IUnknown` 포인터의 멤버 함수를 호출합니다.

## <a name="syntax"></a>구문

```cpp
void AddRef( );
```

## <a name="remarks"></a>설명

캡슐화된 인터페이스 포인터를 호출하여 `IUnknown::AddRef` 포인터가 NULL인 `E_POINTER` 경우 오류를 발생시입니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
