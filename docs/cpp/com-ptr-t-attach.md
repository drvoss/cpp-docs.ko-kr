---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 057d784bb495aefaeec1b86697a7421f6464cbd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745076"
---
# <a name="_com_ptr_tattach"></a>_com_ptr_t::Attach

**마이크로소프트 특정**

이 스마트 포인터 형식의 원시 인터페이스 포인터를 캡슐화합니다.

## <a name="syntax"></a>구문

```cpp
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>매개 변수

*p인터페이스*<br/>
원시 인터페이스 포인터입니다.

*fAddRef*<br/>
TRUE인 경우 `AddRef` 호출됩니다. FALSE인 경우 개체는 `_com_ptr_t` 호출하지 `AddRef`않고 원시 인터페이스 포인터의 소유권을 사용합니다.

## <a name="remarks"></a>설명

- **연결(pInterface)은***pInterface***)** `AddRef` 호출되지 않습니다.     인터페이스 소유권이 이 `_com_ptr_t` 개체에 전달됩니다. `Release`이전에 캡슐화된 포인터에 대한 참조 수를 감소시키기 위해 호출됩니다.

- *첨부(pInterface,* **,** **Attach(***fAddRef)***)** *fAddRef가* `AddRef` TRUE이면 캡슐화된 인터페이스 포인터에 대한 참조 수를 증가시키기 위해 호출됩니다.       *fAddRef가* FALSE이면 `_com_ptr_t` 이 개체는 호출하지 `AddRef`않고 원시 인터페이스 포인터의 소유권을 차지합니다. `Release`이전에 캡슐화된 포인터에 대한 참조 수를 감소시키기 위해 호출됩니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참조

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
