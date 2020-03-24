---
title: noexcept(C++)
ms.date: 11/19/2019
f1_keywords:
- noexcept_cpp
ms.assetid: df24edb9-c6a6-4e37-9914-fd5c0c3716a8
ms.openlocfilehash: cc669a43ff9acbb98ce970c21cba5ac9cdc5b732
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161050"
---
# <a name="noexcept-c"></a>noexcept(C++)

**C + + 11:** 함수에서 예외를 throw 할 수 있는지 여부를 지정 합니다.

## <a name="syntax"></a>구문

> *noexcept*&nbsp;&nbsp;&nbsp;&nbsp;**noexcept** &nbsp;&nbsp;&nbsp;&nbsp;**noexcept (** *상수 식* **)**

### <a name="parameters"></a>매개 변수

*상수 식*<br/>
잠재적 예외 형식 집합이 비어 있는지 여부를 나타내는 **bool** 형식의 상수 식입니다. 비 조건부 버전은 `noexcept(true)`와 동일 합니다.

## <a name="remarks"></a>설명

*Noexcept 식은* 함수를 종료 하는 모든 예외에 대 한 예외 처리기에 의해 일치 될 수 있는 형식 집합을 나타내는 함수 선언에 대 한 접미사 인 *예외 사양의*일종입니다. 단항 조건 연산자 `noexcept(`*constant_expression*`)`에서 *constant_expression* 를 **생성 하 고, 무조건**동의어 **noexcept**함수를 종료할 수 있는 잠재적인 예외 형식 집합이 비어 있음을 지정 합니다. 즉, 함수는 예외를 throw 하지 않으며 예외를 범위 외부에서 전파 하지 않습니다. 연산자는 *constant_expression* **false**를 생성 하거나, 예외 사양이 소멸자 또는 할당 취소 함수를 제외 하는`)` *constant_expression* `noexcept(`함수를 종료할 수 있는 잠재적인 예외 집합이 모든 형식의 집합 임을 나타냅니다.

직접 또는 간접적으로 호출 하는 모든 함수가 **noexcept** 또는 **const**인 경우에만 함수를 **noexcept** 로 표시 합니다. 컴파일러는 **noexcept** 함수로 버블링 될 수 있는 예외에 대 한 모든 코드 경로를 반드시 확인 하지는 않습니다. 예외가 `noexcept`표시 된 함수의 외부 범위를 종료 하는 경우 [std:: terminate](../standard-library/exception-functions.md#terminate) 가 즉시 호출 되 고 범위 내 개체의 소멸자가 호출 되는 것을 보장할 수 없습니다. `throw()`동적 예외 지정자 대신 **noexcept** 를 사용 합니다 .이는 이제 표준에서 더 이상 사용 되지 않습니다. 예외가 호출 스택을 전파 하는 것을 허용 하지 않는 함수에 `noexcept`를 적용 하는 것이 좋습니다. 함수가 **noexcept**로 선언 되 면 컴파일러는 여러 컨텍스트에서 더 효율적인 코드를 생성할 수 있습니다. 자세한 내용은 [예외 사양](exception-specifications-throw-cpp.md)을 참조 하세요.

## <a name="example"></a>예제

해당 인수를 복사 하는 템플릿 함수는 복사 되는 개체가 일반 이전 데이터 형식 (POD) 인 조건에서 **noexcept** 로 선언할 수 있습니다. 이러한 함수는 다음과 같이 선언될 수 있습니다.

```cpp
#include <type_traits>

template <typename T>
T copy_object(const T& obj) noexcept(std::is_pod<T>)
{
   // ...
}
```

## <a name="see-also"></a>참고 항목

[예외 C++ 및 오류 처리에 대 한 최신 모범 사례](errors-and-exception-handling-modern-cpp.md)<br/>
[예외 사양 (throw, noexcept)](exception-specifications-throw-cpp.md)
