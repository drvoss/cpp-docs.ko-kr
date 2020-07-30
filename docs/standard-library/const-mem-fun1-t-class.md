---
title: const_mem_fun1_t 클래스
ms.date: 02/21/2019
f1_keywords:
- functional/std::const_mem_fun1_t
helpviewer_keywords:
- const_mem_fun1_t class
ms.assetid: 250fac30-9663-4133-9051-6303f76ea259
ms.openlocfilehash: 93d0e7a116c7c7ba7a2ed1cb46fd88585a99120d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228325"
---
# <a name="const_mem_fun1_t-class"></a>const_mem_fun1_t 클래스

**`const`** 포인터 인수를 사용 하 여 초기화할 때 단일 인수를 사용 하는 멤버 함수를 이항 함수 개체로 호출할 수 있도록 하는 어댑터 클래스입니다. C + + 11에서 사용 되지 않으며 c + + 17에서 제거 되었습니다.

## <a name="syntax"></a>구문

```cpp
template <class Result, class Type, class Arg>
class const_mem_fun1_t : public binary_function<const Type *, Arg, Result>
{
    explicit const_mem_fun1_t(Result (Type::* member_ptr)(Arg) const);
    Result operator()(const Type* left, Arg right) const;
};
```

### <a name="parameters"></a>매개 변수

*member_ptr*\
함수 개체로 변환할 `Type` 클래스의 멤버 함수 포인터입니다.

*비어*\
**`const`** *Member_ptr* 멤버 함수가 호출 되는 개체입니다.

*오른쪽*\
*Member_ptr*하는 데 지정 되는 인수입니다.

## <a name="return-value"></a>Return Value

조정 가능한 이항 함수입니다.

## <a name="remarks"></a>설명

클래스 템플릿은 *member_ptr* `Type` 전용 멤버 개체에서 클래스의 멤버 함수에 대 한 포인터 여야 하는 member_ptr의 복사본을 저장 합니다. 반환 하는 멤버 함수 `operator()` 를 정의 `(left->member_ptr)(right) const` 합니다.

## <a name="example"></a>예제

`const_mem_fun1_t`의 생성자는 직접 사용되는 경우가 거의 없습니다. `mem_fn`는 멤버 함수를 조정 하는 데 사용 됩니다. 멤버 함수 어댑터를 사용 하는 방법에 대 한 예제는 [mem_fn](../standard-library/functional-functions.md#mem_fn) 를 참조 하세요.
