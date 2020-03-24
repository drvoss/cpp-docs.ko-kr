---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: 8ba42f19e3474cc4a3199771f761b021221f430e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190016"
---
# <a name="_com_ptr_tdetach"></a>_com_ptr_t::Detach

**Microsoft 전용**

캡슐화된 인터페이스 포인터를 추출하고 반환합니다.

## <a name="syntax"></a>구문

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>주의

캡슐화된 인터페이스 포인터를 추출하여 반환한 다음 캡슐화된 포인터 저장소를 NULL로 지웁니다. 이 작업을 통해 인터페이스 포인터의 캡슐화를 제거합니다. 반환 된 인터페이스 포인터에 대 한 `Release`를 호출 하는 것은 사용자에 게 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
