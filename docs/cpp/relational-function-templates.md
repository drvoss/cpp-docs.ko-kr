---
title: 관계형 함수 템플릿
ms.date: 11/04/2016
helpviewer_keywords:
- relational function templates
ms.assetid: 57893a51-9adb-41fc-941d-2ca97687db2a
ms.openlocfilehash: db5091ca8fd29235ea1a0f70410a05ffcb9d7a65
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188183"
---
# <a name="relational-function-templates"></a>관계형 함수 템플릿

**Microsoft 전용**

## <a name="syntax"></a>구문

```
template<typename _InterfaceType> bool operator==(
   int NULL,
   _com_ptr_t<_InterfaceType>& p
);
template<typename _Interface,
   typename _InterfacePtr> bool operator==(
   _Interface* i,
   _com_ptr_t<_InterfacePtr>& p
);
template<typename _Interface> bool operator!=(
   int NULL,
   _com_ptr_t<_Interface>& p
);
template<typename _Interface,
   typename _InterfacePtr> bool operator!=(
   _Interface* i,
   _com_ptr_t<_InterfacePtr>& p
);
template<typename _Interface> bool operator<(
   int NULL,
   _com_ptr_t<_Interface>& p
);
template<typename _Interface,
   typename _InterfacePtr> bool operator<(
   _Interface* i,
   _com_ptr_t<_InterfacePtr>& p
);
template<typename _Interface> bool operator>(
   int NULL,
   _com_ptr_t<_Interface>& p
);
template<typename _Interface,
   typename _InterfacePtr> bool operator>(
   _Interface* i,
   _com_ptr_t<_InterfacePtr>& p
);
template<typename _Interface> bool operator<=(
   int NULL,
   _com_ptr_t<_Interface>& p
);
template<typename _Interface,
   typename _InterfacePtr> bool operator<=(
   _Interface* i,
   _com_ptr_t<_InterfacePtr>& p
);
template<typename _Interface> bool operator>=(
   int NULL,
   _com_ptr_t<_Interface>& p
);
template<typename _Interface,
   typename _InterfacePtr> bool operator>=(
   _Interface* i,
   _com_ptr_t<_InterfacePtr>& p
);
```

### <a name="parameters"></a>매개 변수

*i*<br/>
원시 인터페이스 포인터입니다.

*p*<br/>
스마트 포인터입니다.

## <a name="remarks"></a>설명

이러한 함수 템플릿을 사용하면 비교 연산자 오른쪽에 있는 스마트 포인터와 비교할 수 있습니다. 이러한 템플릿은 `_com_ptr_t`의 멤버 함수가 아닙니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
