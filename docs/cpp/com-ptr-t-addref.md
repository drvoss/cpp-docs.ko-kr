---
title: _com_ptr_t::AddRef
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::AddRef
helpviewer_keywords:
- AddRef method [C++], interface pointers
ms.assetid: c104dac3-aad3-40bb-a298-75c6cd0e63a2
ms.openlocfilehash: 51182b461aeac83c12bb18a573a49b2d4347a190
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189935"
---
# <a name="_com_ptr_taddref"></a>_com_ptr_t::AddRef

**Microsoft 전용**

캡슐화 된 인터페이스 포인터에서 `IUnknown`의 `AddRef` 멤버 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
void AddRef( );
```

## <a name="remarks"></a>주의

캡슐화 된 인터페이스 포인터에 대 한 `IUnknown::AddRef`를 호출 하면 포인터가 NULL 인 경우 `E_POINTER` 오류가 발생 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
