---
title: _com_ptr_t::QueryInterface
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::QueryInterface
- _com_ptr_t.QueryInterface
helpviewer_keywords:
- QueryInterface method [C++]
ms.assetid: d03292f1-6b02-40db-9756-8b0837a97319
ms.openlocfilehash: 26dda2dff83ff0adbb7ef05c5e75f64b44138bd8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170673"
---
# <a name="_com_ptr_tqueryinterface"></a>_com_ptr_t::QueryInterface

**Microsoft 전용**

캡슐화 된 인터페이스 포인터에 `IUnknown`의 **QueryInterface** 멤버 함수를 호출 합니다.

## <a name="syntax"></a>구문

```
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType*& p
) throw ( );
template<typename _InterfaceType> HRESULT QueryInterface (
   const IID& iid,
   _InterfaceType** p
) throw( );
```

#### <a name="parameters"></a>매개 변수

*iid*<br/>
인터페이스 포인터의 `IID`입니다.

*p*<br/>
원시 인터페이스 포인터입니다.

## <a name="remarks"></a>주의

지정 된 `IID`를 사용 하 여 캡슐화 된 인터페이스 포인터에 대 한 `IUnknown::QueryInterface`를 호출 하 고 *p*에서 결과 원시 인터페이스 포인터를 반환 합니다. 이 루틴은 성공 또는 실패를 나타내는 HRESULT를 반환 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
