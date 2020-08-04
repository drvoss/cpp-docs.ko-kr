---
title: domain_error 클래스
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::domain_error
helpviewer_keywords:
- domain_error class
ms.assetid: a1d8245d-61c2-4d1e-973f-073bd5dd5fa3
ms.openlocfilehash: 850615f07af022aff3ed209d9142823b0f038134
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87521241"
---
# <a name="domain_error-class"></a>domain_error 클래스

이 클래스는 도메인 오류를 보고하기 위해 발생하는 모든 예외에 대한 기본 클래스로 사용됩니다.

## <a name="syntax"></a>구문

```cpp
class domain_error : public logic_error {
public:
    explicit domain_error(const string& message);

    explicit domain_error(const char *message);

};
```

## <a name="remarks"></a>설명

에서 반환 하는 값은 `what()` 의 복사본입니다 `message.data()` . 자세한 내용은 [`what`](../standard-library/exception-class.md) 및 [`data`](../standard-library/basic-string-class.md#data)을 참조하세요.

## <a name="example"></a>예제

```cpp
// domain_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
   try
   {
      throw domain_error( "Your domain is in error!" );
   }
   catch (exception &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid(e).name( ) << endl;
   };
}
/* Output:
Caught: Your domain is in error!
Type: class std::domain_error
*/
```

## <a name="requirements"></a>요구 사항

**헤더:**\<stdexcept>

**네임스페이스:** std

## <a name="see-also"></a>참조

[logic_error 클래스](../standard-library/logic-error-class.md)\
[C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)
