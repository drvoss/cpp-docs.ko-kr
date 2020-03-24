---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 870e3580ed23ce994d832f7c59b951680d725e41
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180500"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**Microsoft 전용**

이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.

## <a name="syntax"></a>구문

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>매개 변수

*pInterface*<br/>
원시 인터페이스 포인터입니다.

*fAddRef*<br/>
TRUE 이면 `AddRef`가 호출 됩니다. FALSE 인 경우 `_com_ptr_t` 개체는 `AddRef`를 호출 하지 않고 원시 인터페이스 포인터의 소유권을 갖습니다.

## <a name="remarks"></a>설명

- **Attach (**  *pinterface*  **)** `AddRef`가 호출 되지 않습니다. 인터페이스 소유권이 이 `_com_ptr_t` 개체에 전달됩니다. `Release`를 호출 하 여 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시킵니다.

- **Attach (**  *pinterface* **,**  *fAddRef*  **)** *FAddRef* 가 TRUE 이면 캡슐화 된 인터페이스 포인터의 참조 횟수를 증가 시키기 위해 `AddRef`가 호출 됩니다. *FAddRef* 가 FALSE 인 경우이 `_com_ptr_t` 개체는 `AddRef`를 호출 하지 않고 원시 인터페이스 포인터의 소유권을 갖습니다. `Release`를 호출 하 여 이전에 캡슐화 된 포인터에 대 한 참조 횟수를 감소 시킵니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
