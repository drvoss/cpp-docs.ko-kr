---
title: _com_ptr_t Extractors
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::operatorInterface&
- _com_ptr_t::operatorbool
- _com_ptr_t::operator->
- _com_ptr_t::operator*
helpviewer_keywords:
- operator Interface& [C++]
- '* operator [C++], with specific objects'
- operator& [C++]
- operator* [C++]
- -> operator [C++], with specific objects
- '& operator [C++], with specific objects'
- operator Interface* [C++]
- operator * [C++]
- operator->
- operator bool
- extractors, _com_ptr_t class
- extractors [C++]
ms.assetid: 194b9e0e-123c-49ff-a187-0a7fcd68145a
ms.openlocfilehash: 31ac39104c041d1d119f6cd06de5f9c4a620dac0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190029"
---
# <a name="_com_ptr_t-extractors"></a>_com_ptr_t Extractors

**Microsoft 전용**

캡슐화된 COM 인터페이스 포인터를 추출합니다.

## <a name="syntax"></a>구문

```
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>주의

- **연산자 인터페이스** <strong>\*</strong> 은 NULL 일 수 있는 캡슐화 된 인터페이스 포인터를 반환 합니다.

- **연산자 인터페이스 &** 캡슐화 된 인터페이스 포인터에 대 한 참조를 반환 하 고 포인터가 NULL 인 경우 오류를 발생 시킵니다.

- **연산자** <strong>\*</strong> 를 사용 하면 스마트 포인터 개체가 역참조 시 실제 캡슐화 된 인터페이스인 것 처럼 동작할 수 있습니다.

- **연산자->** 스마트 포인터 개체가 역참조 시 실제로 캡슐화 된 인터페이스인 것 처럼 동작할 수 있습니다.

- **연산자 &** 캡슐화 된 인터페이스 포인터를 해제 하 여 NULL로 바꾸고 캡슐화 된 포인터의 주소를 반환 합니다. 이를 통해 스마트 포인터는 *out* 매개 변수를 사용 하 여 인터페이스 포인터를 반환 하는 함수에 주소로 전달 됩니다.

- **연산자 bool** 조건식에 스마트 포인터 개체를 사용할 수 있도록 합니다. 이 연산자는 포인터가 NULL이 아닌 경우 TRUE를 반환 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
