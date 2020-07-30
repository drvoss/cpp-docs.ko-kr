---
title: C++에서 구조적 예외 처리
description: C + + 예외 처리 모델을 사용 하 여 구조적 예외를 처리 하는 방법입니다.
ms.date: 09/19/2019
helpviewer_keywords:
- structured exception handling [C++], vs. C++ exception handling
- structured exception handling [C++], vs. unstructured
- exceptions [C++], wrapper class
- C++ exception handling [C++], vs. structured exception handling
- wrapper classes [C++], C exception
ms.assetid: f21d1944-4810-468e-b02a-9f77da4138c9
ms.openlocfilehash: 0f92bbe64db028ec6a7fd6ae2cc217c707d3e2c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221590"
---
# <a name="handle-structured-exceptions-in-c"></a>C++에서 구조적 예외 처리

C SEH (구조적 예외 처리)와 c + + 예외 처리의 주요 차이점은 c + + 예외 처리 모델이 형식을 처리 하는 반면, C 구조적 예외 처리 모델은 한 형식의 예외를 처리 한다는 것입니다. 특히 **`unsigned int`** 입니다. 즉, C 예외는 부호 없는 정수 값으로 식별되지만 C++ 예외는 데이터 형식으로 식별됩니다. C에서 구조화 된 예외가 발생할 경우 가능한 각 처리기는 C 예외 컨텍스트를 검사 하 고 예외를 수락할지, 다른 처리기에 전달 하거나, 무시 하는지 여부를 결정 하는 필터를 실행 합니다. C++에서 예외가 발생하는 경우 예외는 어떤 형식이든 가능합니다.

두 번째 차이점은 일반적인 제어 흐름에 대 한 예외가 발생 하기 때문에 C 구조적 예외 처리 모델을 *비동기*이라고 합니다. C + + 예외 처리 메커니즘은 완전히 *동기화*됩니다. 즉, 예외가 throw 되는 경우에만 예외가 발생 합니다.

[/EHs 또는/ehsc](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션을 사용 하는 경우 c + + 예외 처리기가 구조화 된 예외를 처리 하지 않습니다. 이러한 예외는 **`__except`** 구조적 예외 처리기 또는 **`__finally`** 구조적 종료 처리기 에서만 처리 됩니다. 자세한 내용은 [구조적 예외 처리 (C/c + +)](structured-exception-handling-c-cpp.md)를 참조 하세요.

[/Eha](../build/reference/eh-exception-handling-model.md) 컴파일러 옵션에서 c 예외가 c + + 프로그램에서 발생 하는 경우이 예외는 연결 된 필터 또는 c + + 처리기를 사용 하 여 구조적 예외 처리기에 의해 처리 될 수 있으며 **`catch`** ,이는 예외 컨텍스트에 동적으로 더 가까운 것입니다. 예를 들어이 샘플 c + + 프로그램은 c + + 컨텍스트 내에서 C 예외를 발생 시킵니다 **`try`** .

## <a name="example---catch-a-c-exception-in-a-c-catch-block"></a>예제-c + + catch 블록에서 C 예외 Catch

```cpp
// exceptions_Exception_Handling_Differences.cpp
// compile with: /EHa
#include <iostream>

using namespace std;
void SEHFunc( void );

int main() {
   try {
      SEHFunc();
   }
   catch( ... ) {
      cout << "Caught a C exception."<< endl;
   }
}

void SEHFunc() {
   __try {
      int x, y = 0;
      x = 5 / y;
   }
   __finally {
      cout << "In finally." << endl;
   }
}
```

```Output
In finally.
Caught a C exception.
```

## <a name="c-exception-wrapper-classes"></a>C 예외 래퍼 클래스

위의 간단한 예제에서 C 예외는 줄임표 (**...**) **`catch`** 로만 catch 할 수 있습니다. 핸들러. 예외의 형식이나 특성에 대한 정보가 처리기로 전달되지 않습니다. 이 메서드가 작동 하는 동안 각 C 예외가 특정 클래스에 연결 되도록 두 가지 예외 처리 모델 간의 변환을 정의할 수 있습니다. 변환을 위해 특정 클래스 형식의 특성을 C 예외로 지정 하기 위해 사용 하거나 파생 시킬 수 있는 C 예외 "래퍼" 클래스를 정의할 수 있습니다. 이렇게 하면 각 C 예외를 단일 처리기에서 수행 하는 것이 아니라 특정 c + + 처리기를 통해 개별적으로 처리할 수 있습니다 **`catch`** .

래퍼 클래스에는 예외 값을 결정하는 멤버 함수로 구성되며 C 예외 모델에서 제공하는 확장된 예외 컨텍스트 정보에 액세스하는 인터페이스가 있을 수 있습니다. 기본 생성자와 **`unsigned int`** 인수 (기본 C 예외 표현을 제공 하기 위해)를 허용 하는 생성자 및 비트 복사 생성자를 정의할 수도 있습니다. 다음은 C 예외 래퍼 클래스의 가능한 구현입니다.

```cpp
// exceptions_Exception_Handling_Differences2.cpp
// compile with: /c
class SE_Exception {
private:
   SE_Exception() {}
   SE_Exception( SE_Exception& ) {}
   unsigned int nSE;
public:
   SE_Exception( unsigned int n ) : nSE( n ) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() {
      return nSE;
   }
};
```

이 클래스를 사용 하려면 C 예외가 throw 될 때마다 내부 예외 처리 메커니즘에 의해 호출 되는 사용자 지정 C 예외 변환 함수를 설치 합니다. 변환 함수 내에서 `SE_Exception` `SE_Exception` 적절 하 게 일치 하는 c + + 처리기에 의해 catch 될 수 있는 모든 형식의 예외 (또는에서 파생 된 클래스 형식)를 throw 할 수 있습니다 **`catch`** . 대신 translation 함수는 예외를 처리 하지 못했음을 나타내는를 반환할 수 있습니다. 변환 함수 자체가 C 예외를 발생 시키면 [terminate](../c-runtime-library/reference/terminate-crt.md) 가 호출 됩니다.

사용자 지정 변환 함수를 지정 하려면 변환 함수의 이름을 단일 인수로 사용 하 여 [_set_se_translator](../c-runtime-library/reference/set-se-translator.md) 함수를 호출 합니다. 작성 하는 변환 함수는 블록이 있는 스택의 각 함수 호출에 대해 한 번씩 호출 됩니다 **`try`** . 기본 변환 함수가 없습니다. **_set_se_translator**를 호출 하 여 지정 하지 않는 경우에는 줄임표 처리기만 C 예외를 catch 할 수 있습니다 **`catch`** .

## <a name="example---use-a-custom-translation-function"></a>예-사용자 지정 변환 함수 사용

예를 들어 다음 코드에서는 사용자 지정 변환 함수를 설치한 후 `SE_Exception` 클래스로 래핑된 C 예외를 발생시킵니다.

```cpp
// exceptions_Exception_Handling_Differences3.cpp
// compile with: /EHa
#include <stdio.h>
#include <eh.h>
#include <windows.h>

class SE_Exception {
private:
   SE_Exception() {}
   unsigned int nSE;
public:
   SE_Exception( SE_Exception& e) : nSE(e.nSE) {}
   SE_Exception(unsigned int n) : nSE(n) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() { return nSE; }
};

void SEFunc() {
    __try {
        int x, y = 0;
        x = 5 / y;
    }
    __finally {
        printf_s( "In finally\n" );
    }
}

void trans_func( unsigned int u, _EXCEPTION_POINTERS* pExp ) {
    printf_s( "In trans_func.\n" );
    throw SE_Exception( u );
}

int main() {
    _set_se_translator( trans_func );
    try {
        SEFunc();
    }
    catch( SE_Exception e ) {
        printf_s( "Caught a __try exception with SE_Exception.\n" );
        printf_s( "nSE = 0x%x\n", e.getSeNumber() );
    }
}
```

```Output
In trans_func.
In finally
Caught a __try exception with SE_Exception.
nSE = 0xc0000094
```

## <a name="see-also"></a>참고 항목

[C(구조적) 및 C++ 예외 혼합](../cpp/mixing-c-structured-and-cpp-exceptions.md)
