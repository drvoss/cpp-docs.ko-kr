---
title: volatile (C++)
ms.date: 05/07/2019
f1_keywords:
- volatile_cpp
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
ms.openlocfilehash: 841b2e1e4ffbec87a170c45be8ad0cd0f831a0ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371907"
---
# <a name="volatile-c"></a>volatile (C++)

하드웨어에 의해 프로그램에서 수정할 수 있는 개체를 선언하는 데 사용할 수 있는 형식 한정자입니다.

## <a name="syntax"></a>구문

```
volatile declarator ;
```

## <a name="remarks"></a>설명

[/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) 컴파일러 스위치를 사용하여 컴파일러가 이 키워드를 해석하는 방법을 수정할 수 있습니다.

Visual Studio는 대상 아키텍처에 따라 **휘발성** 키워드를 다르게 해석합니다. ARM의 경우 **/volatile** 컴파일러 옵션이 지정되지 않으면 컴파일러가 **/volatile:iso가** 지정된 것처럼 수행됩니다. ARM 이외의 아키텍처의 경우 **/volatile** 컴파일러 옵션이 지정되지 않은 경우 컴파일러는 **/volatile:ms가** 지정된 것처럼 수행됩니다. 따라서 ARM 이외의 아키텍처의 경우 **/volatile:iso를**지정하고 스레드 간에 공유되는 메모리를 처리할 때 명시적 동기화 프리미티브 및 컴파일러 내장 함수를 사용하는 것이 좋습니다.

**휘발성** 한정자를 사용하여 인터럽트 처리기와 같은 비동기 프로세스에서 사용되는 메모리 위치에 대한 액세스를 제공할 수 있습니다.

[__restrict](../cpp/extension-restrict.md) 키워드가 있는 변수에 **휘발성이** 사용되는 경우 **휘발성이** 우선합니다.

**구조체** 부재가 **휘발성으로**표시되면 **휘발성이** 전체 구조로 전파됩니다. 구조에 하나의 명령을 사용하여 현재 아키텍처에서 복사할 수 있는 길이가 없는 경우 해당 구조에서 **휘발성이** 완전히 손실될 수 있습니다.

다음 조건 중 하나가 true인 경우 **휘발성** 키워드는 필드에 영향을 주지 않을 수 있습니다.

- volatile 필드의 길이가 현재 아키텍처에서 하나의 명령을 사용하여 복사할 수 있는 최대 크기를 초과합니다.

- **구조체가**포함된 가장 바깥쪽길이 또는 중첩된 **구조체의**멤버인 경우 한 명령을 사용하여 현재 아키텍처에서 복사할 수 있는 최대 크기를 초과합니다.

프로세서가 캐시 불가능한 메모리 액세스의 순서를 다시 지정하지는 않지만 캐시할 수 없는 변수는 컴파일러가 메모리 액세스의 순서를 다시 정렬하지 않도록 **휘발성으로** 표시해야 합니다.

**휘발성으로** 선언된 객체는 해당 값이 언제든지 변경될 수 있기 때문에 특정 최적화에 사용되지 않습니다.  이전 명령에서 동일한 개체의 값을 요청한 경우에도 시스템은 요청될 때 항상 휘발성 개체의 현재 값을 읽습니다.  또한 개체의 값은 할당 시 즉시 기록됩니다.

## <a name="iso-compliant"></a>ISO 규격

C# 휘발성 키워드에 익숙하거나 이전 버전의 Microsoft C++ 컴파일러(MSVC)에서 **휘발성** 동작에 익숙한 경우 C++11 ISO 표준 **휘발성** 키워드가 다르며 [/volatile:iso컴파일러](../build/reference/volatile-volatile-keyword-interpretation.md) 옵션이 지정되면 MSVC에서 지원됩니다. ARM의 경우 기본적으로 지정됩니다. C++11 ISO 표준 코드의 **휘발성** 키워드는 하드웨어 액세스에만 사용해야 합니다. 스레드 간 통신에 사용하지 마십시오. 스레드 간 통신의 경우 [C++ 표준 라이브러리에서](../standard-library/cpp-standard-library-reference.md) [std:::atomic\<T>](../standard-library/atomic.md) 와 같은 메커니즘을 사용합니다.

## <a name="end-of-iso-compliant"></a>ISO 규격의 끝

**마이크로소프트 특정**

기본적으로 ARM 이외의 아키텍처가 대상으로 지정될 때 **/volatile:ms** 컴파일러 옵션을 사용하는 경우 컴파일러는 다른 전역 개체에 대한 참조 순서를 유지하는 것 외에도 휘발성 개체에 대한 참조 간의 순서를 유지하기 위해 추가 코드를 생성합니다. 특히 다음 사항에 주의하십시오.

- volatile 개체 쓰기(volatile 쓰기)는 Release 의미 체계를 사용합니다. 즉 명령 시퀀스에서 volatile 개체에 쓰기 전에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 volatile 쓰기 전에 발생합니다.

- volatile 개체 읽기(volatile 읽기)는 Acquire 의미 체계를 사용합니다. 즉 명령 시퀀스에서 volatile 메모리 읽기 다음에 발생하는 전역 또는 정적 개체에 대한 참조는 컴파일된 이진 파일에서 volatile 읽기 다음에 발생합니다.

이렇게 하면 여러 스레드 응용 프로그램의 메모리 잠금 및 릴리스에 휘발성 개체를 사용할 수 있습니다.

> [!NOTE]
> **/volatile:ms** 컴파일러 옵션을 사용할 때 제공되는 향상된 보증에 의존하는 경우 코드는 이식가능하지 않습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고 항목

[키워드](../cpp/keywords-cpp.md)<br/>
[const](../cpp/const-cpp.md)<br/>
[const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)
