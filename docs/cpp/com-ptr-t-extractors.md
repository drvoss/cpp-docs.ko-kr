---
title: _com_ptr_t Extractors
description: _Com_ptr_t 클래스에 대 한 추출 연산자를 설명 합니다.
ms.date: 07/07/2020
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
ms.openlocfilehash: e7b06bb11ab34a1a1a7f6fab98d177821f60b20c
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127859"
---
# <a name="_com_ptr_t-extractors"></a>`_com_ptr_t`추출기

**Microsoft 전용**

캡슐화된 COM 인터페이스 포인터를 추출합니다.

## <a name="syntax"></a>구문

```c++
operator Interface*( ) const throw( );
operator Interface&( ) const;
Interface& operator*( ) const;
Interface* operator->( ) const;
Interface** operator&( ) throw( );
operator bool( ) const throw( );
```

## <a name="remarks"></a>설명

- **`operator Interface*`** 캡슐화 된 인터페이스 포인터를 반환 합니다 .이는 NULL 일 수 있습니다.

- **`operator Interface&`** 캡슐화 된 인터페이스 포인터에 대 한 참조를 반환 하 고 포인터가 NULL 인 경우 오류를 발생 시킵니다.

- **`operator*`** 스마트 포인터 개체가 역참조 시 실제로 캡슐화 된 인터페이스인 것 처럼 동작할 수 있습니다.

- **`operator->`** 스마트 포인터 개체가 역참조 시 실제로 캡슐화 된 인터페이스인 것 처럼 동작할 수 있습니다.

- **`operator&`** 캡슐화 된 인터페이스 포인터를 해제 하 여 NULL로 바꾸고 캡슐화 된 포인터의 주소를 반환 합니다. 이 연산자를 사용 하면 *out* 매개 변수를 사용 하 여 인터페이스 포인터를 반환 하는 함수에 주소를 사용 하 여 스마트 포인터를 전달할 수 있습니다.

- **`operator bool`** 조건식에 스마트 포인터 개체를 사용할 수 있도록 합니다. 이 연산자는 포인터가 NULL이 아닌 경우 TRUE를 반환 합니다.

  > [!NOTE]
  > **`operator bool`** 는로 선언 되지 않으므로 **`explicit`** `_com_ptr_t` 는 **`bool`** 스칼라 형식으로 변환할 수 있는로 암시적으로 변환할 수 있습니다. 이 경우 코드에서 예기치 않은 결과가 발생할 수 있습니다. [컴파일러 경고 (수준 4) C4800](../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md) 를 사용 하도록 설정 하 여 의도 하지 않은 변환을 방지 합니다.

## <a name="see-also"></a>참고 항목

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
