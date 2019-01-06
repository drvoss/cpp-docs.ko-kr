---
title: C++ 언어 참조
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- language reference
- C++, language reference
- language reference, Visual C++
- Visual C++, language reference
ms.assetid: 4be9cacb-c862-4391-894a-3a118c9c93ce
ms.openlocfilehash: 69b244a1559a4570cc00a72d86426a7929ffc474
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469383"
---
# <a name="c-language-reference"></a>C++ 언어 참조

이 문서에서는 Microsoft Visual C++에서 사용하는 C++ 프로그래밍 언어를 설명하며 [*The Annotated C++ Reference Manual*](http://www.stroustrup.com/arm.html)(머거렛 앨리스(Margaret Ellis), 비야네 스트롭스트룹(Bjarne Stroustrup) 공저)의 구성을 참고하고 ANSI/ISO C++ 국제 표준(ISO/IEC FDIS 14882)을 기반으로 합니다. 또한 C++ 언어 기능의 Microsoft 전용 구현 사항이 포함되어 있습니다.

모던 C++ 프로그래밍 방법은 [C++의 진화( C++)](welcome-back-to-cpp-modern-cpp.md)를 참조합니다.

키워드나 연산자를 빠르게 찾으려면 다음 표를 참조하십시오.

- [C++ 키워드](../cpp/keywords-cpp.md)

- [C++ 연산자](../cpp/cpp-built-in-operators-precedence-and-associativity.md)

## <a name="in-this-section"></a>섹션 내용

[어휘 규칙](../cpp/lexical-conventions.md)<br/>
C++ 프로그램의 기본적인 어휘 요소에는 토큰, 주석, 연산자, 키워드, 문장 부호, 리터럴이 있습니다. 또한 파일 변환, 연산자 우선 순위/결합성이 있습니다.

[기본 개념](../cpp/basic-concepts-cpp.md)<br/>
범위, 링크, 프로그램 시작 및 종료, 기억 영역 클래스 및 형식입니다.

[표준 변환](../cpp/standard-conversions.md)<br/>
기본 제공(Built-in)되거나 '기본형'인 형식 사이의 형변환입니다. 또한 산술 변환 및 포인터, 참조 및 멤버 포인터 형식 간의 변환입니다.

[연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
C++의 연산자입니다.

[식](../cpp/expressions-cpp.md)<br/>
표현식의 유형 및 의미, 연산자에 대한 참조 항목, 캐스팅 및 캐스팅 연산자, 런타임 형식 정보입니다.

[람다 식](../cpp/lambda-expressions-in-cpp.md)<br/>
함수 개체 클래스를 암시적으로 정의하고 해당 클래스 형식의 함수 개체를 생성하는 프로그래밍 기술입니다.

[문](../cpp/statements-cpp.md)<br/>
표현식, null, 복합, 선택, 반복, 점프 및 선언문입니다.

[선언 및 정의](declarations-and-definitions-cpp.md)<br/>
기억 영역 클래스 지정자(auto, register, static 등), 함수 정의, 초기화, 열거형 **클래스**, **구조체**, **인라인** 함수, **const** 키워드, 네임 스페이스, **union** 및 **typedef**의 선언 및 정의와 관련된 내용입니다. 

[클래스, 구조체 및 공용 구조체](../cpp/classes-and-structs-cpp.md)<br/>
클래스, 구조체 및 공용 구조체에 대한 소개입니다. 멤버 함수, 특수 멤버 함수, 데이터 멤버, 비트 필드 **this** 포인터, 중첩된 클래스와 관련된 내용입니다.

[파생된 클래스](../cpp/inheritance-cpp.md)<br/>
단일 및 다중 상속, **가상** 함수, 다중 기본 클래스, **추상** 클래스, 범위 관련 규칙입니다. 또한 **__super**와 **__interface** 키워드도 포함됩니다.

[멤버 Access Control](../cpp/member-access-control-cpp.md)<br/>
클래스 멤버에 대한 액세스 제어: **public**, **private**, 및 **protected** 키워드 관련 내용입니다. Friend 함수 및 클래스도 포함됩니다.

[오버 로드](operator-overloading.md)<br/>
오버로드 된 연산자, 연산자 오버로드에 대한 규칙입니다.

[예외 처리](../cpp/exception-handling-in-visual-cpp.md)<br/>
C++ 예외 처리, SEH(구조적 예외 처리), 예외처리 문을 작성하는 데 사용되는 키워드입니다.

[어설션 및 사용자 제공 메시지](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
`#error` 지시문, **static_assert** 키워드, `assert` 매크로에 대한 내용입니다.

[템플릿](../cpp/templates-cpp.md)<br/>
템플릿 지정, 함수 템플릿, 템플릿 클래스 **typename** 키워드, 템플릿과 매크로의 비교, 템플릿 및 스마트 포인터에 대한 내용입니다.

[이벤트 처리](../cpp/event-handling.md)<br/>
이벤트 및 이벤트 처리기에 대한 내용입니다.

[Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)<br/>
Microsoft C++ 전용 한정자를 설명합니다. 메모리 주소 지정, 호출 규칙, **naked** 함수, 확장된 기억 영역 클래스 특성(**__declspec**), **__w64**와 관련된 내용입니다.

[인라인 어셈블러](../assembler/inline/inline-assembler.md)<br/>
**__asm** 블록을 사용하여 C++에서 어셈블리 언어를 사용하는 방법에 대한 내용입니다.

[컴파일러 COM 지원](../cpp/compiler-com-support.md)<br/>
COM 형식을 지원하는 데 사용되는 Microsoft 전용 클래스 및 전역 함수에 대한 참조입니다.

[Microsoft 확장](../cpp/microsoft-extensions.md)<br/>
C++에 대한 Microsoft 확장입니다.

[비표준 동작](../cpp/nonstandard-behavior.md)<br/>
Visual C++ 컴파일러의 비표준 동작에 대한 정보입니다.

[C++의 진화(최신 C++)](welcome-back-to-cpp-modern-cpp.md)<br/>
최신 C++ 프로그래밍을 도입해 안전하고, 올바른 효율적인 프로그램을 작성하는 것에 대한 사례를 간략하게 설명합니다.

## <a name="related-sections"></a>관련 단원

[런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)<br/>
공용 언어 런타임을 대상으로 하는 Visual C++ 사용에 대한 참조 자료입니다.

[C/C++ 빌드 참조](../build/reference/c-cpp-building-reference.md)<br/>
컴파일러 옵션, 링커 옵션 및 기타 빌드 도구입니다.

[ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
pragma, 전처리기 지시문, 미리 정의된 매크로 및 전처리기에 대한 참조 자료입니다.

[Visual C++ 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
다양한 Visual C++ 라이브러리에 대한 참조 시작 페이지의 링크 목록입니다.

## <a name="see-also"></a>참고자료

[C# 언어 참조](../c-language/c-language-reference.md)
