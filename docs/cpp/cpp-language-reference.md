---
title: C++ 언어 참조
ms.custom: index-page
ms.date: 12/10/2019
helpviewer_keywords:
- C++, language reference
ms.assetid: 4be9cacb-c862-4391-894a-3a118c9c93ce
ms.openlocfilehash: f00d4eb5dc69ee0ab95ea864e63091b041a1853f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079931"
---
# <a name="c-language-reference"></a>C++ 언어 참조

이 참조는 C++ 프로그래밍 언어를 Microsoft에서 구현한 C++ 컴파일러에서 구현된대로 설명합니다. 이 조직은 Margaret Ellis 및 Bjarne Stroustrup와 ANSI/ISO C++ 국제 표준 (ISO/IEC FDIS 14882)에서 *주석이 추가 C++ 된 참조 설명서* 를 기반으로 합니다. C++ 언어 기능의 Microsoft 특정 구현이 포함됩니다.

최신 C++ 프로그래밍 방법에 대 한 개요는 [다시 C++시작 ](welcome-back-to-cpp-modern-cpp.md)을 참조 하세요.

키워드나 연산자를 빠르게 찾으려면 다음 표를 참조하십시오.

- [C++어](../cpp/keywords-cpp.md)

- [C++ 연산자](../cpp/cpp-built-in-operators-precedence-and-associativity.md)

## <a name="in-this-section"></a>섹션 내용

[어휘 규칙](../cpp/lexical-conventions.md)<br/>
C++ 프로그램의 기본적인 어휘 요소에는 토큰, 주석, 연산자, 키워드, 문장 부호, 리터럴이 있습니다. 또한 파일 변환, 연산자 우선 순위/결합성이 있습니다.

[기본 개념](../cpp/basic-concepts-cpp.md)<br/>
범위, 링크, 프로그램 시작 및 종료, 기억 영역 클래스 및 형식입니다.

[기본 제공 형식](fundamental-types-cpp.md) C++ 컴파일러 및 해당 값 범위에 기본 제공 되는 기본 형식입니다.

[표준 변환](../cpp/standard-conversions.md)<br/>
기본 제공 형식 간의 형식 변환입니다. 또한 산술 변환 및 포인터, 참조 및 멤버 포인터 형식 간의 변환입니다.

[선언 및 정의](declarations-and-definitions-cpp.md) 변수, 형식 및 함수 선언 및 정의.

[연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
C++의 연산자입니다.

[식](../cpp/expressions-cpp.md)<br/>
표현식의 유형 및 의미, 연산자에 대한 참조 항목, 캐스팅 및 캐스팅 연산자, 런타임 형식 정보입니다.

[람다 식](../cpp/lambda-expressions-in-cpp.md)<br/>
함수 개체 클래스를 암시적으로 정의하고 해당 클래스 형식의 함수 개체를 생성하는 프로그래밍 기술입니다.

[문](../cpp/statements-cpp.md)<br/>
표현식, null, 복합, 선택, 반복, 점프 및 선언문입니다.

[클래스 및 구조체](../cpp/classes-and-structs-cpp.md)<br/>
클래스, 구조체 및 공용 구조체에 대한 소개입니다. 또한 멤버 함수, 특수 멤버 함수, 데이터 멤버, 비트 필드, **this** 포인터, 중첩 클래스입니다.

[공용 구조체](unions.md)<br/>
모든 멤버가 동일한 메모리 위치를 공유 하는 사용자 정의 형식입니다.

[파생 클래스](../cpp/inheritance-cpp.md)<br/>
단일 및 다중 상속, **가상** 함수, 여러 기본 클래스, **추상** 클래스, 범위 규칙. 또한 **__super** 및 **__interface** 키워드입니다.

[멤버-Access Control](../cpp/member-access-control-cpp.md)<br/>
클래스 멤버에 대 한 액세스 제어: **public**, **private**및 **protected** 키워드. Friend 함수 및 클래스도 포함됩니다.

[로딩이](operator-overloading.md)<br/>
오버로드 된 연산자, 연산자 오버로드에 대한 규칙입니다.

[예외 처리](../cpp/exception-handling-in-visual-cpp.md)<br/>
C++ 예외 처리, SEH(구조적 예외 처리), 예외처리 문을 작성하는 데 사용되는 키워드입니다.

[어설션 및 사용자 제공 메시지](../cpp/assertion-and-user-supplied-messages-cpp.md)<br/>
`#error` 지시문, **static_assert** 키워드인 `assert` 매크로입니다.

[템플릿](../cpp/templates-cpp.md)<br/>
템플릿 사양, 함수 템플릿, 클래스 템플릿, **typename** 키워드, 템플릿 및 매크로, 템플릿 및 스마트 포인터

[이벤트 처리](../cpp/event-handling.md)<br/>
이벤트 및 이벤트 처리기에 대한 내용입니다.

[Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md)<br/>
Microsoft C++ 전용 한정자를 설명합니다. 메모리 주소 지정, 호출 규칙, **naked** 함수, 확장 된 저장소 클래스 특성 ( **__declspec**) **__w64**.

[인라인 어셈블러](../assembler/inline/inline-assembler.md)<br/>
어셈블리 언어 및 C++ **__asm** 블록 사용

[컴파일러 COM 지원](../cpp/compiler-com-support.md)<br/>
COM 형식을 지원하는 데 사용되는 Microsoft 전용 클래스 및 전역 함수에 대한 참조입니다.

[Microsoft 확장](../cpp/microsoft-extensions.md)<br/>
C++에 대한 Microsoft 확장입니다.

[비표준 동작](../cpp/nonstandard-behavior.md)<br/>
Microsoft C++ 컴파일러의 비표준 동작에 대한 정보.

[C++의 진화](welcome-back-to-cpp-modern-cpp.md)<br/>
최신 C++ 프로그래밍을 도입해 안전하고, 올바른 효율적인 프로그램을 작성하는 것에 대한 사례를 간략하게 설명합니다.

## <a name="related-sections"></a>관련 섹션

[런타임 플랫폼용 구성 요소 확장](../extensions/component-extensions-for-runtime-platforms.md)<br/>
.NET을 대상으로 하는 Microsoft C++ 컴파일러 사용에 대한 참조 자료.

[C/C++ 빌드 참조](../build/reference/c-cpp-building-reference.md)<br/>
컴파일러 옵션, 링커 옵션 및 기타 빌드 도구.

[ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
pragma, 전처리기 지시문, 미리 정의된 매크로 및 전처리기에 대한 참조 자료.

[Visual C++ 라이브러리](../standard-library/cpp-standard-library-reference.md)<br/>
다양한 Microsoft의 C++ 라이브러리에 대한 시작 페이지로의 참조 링크 목록.

## <a name="see-also"></a>참고 항목

[C 언어 참조](../c-language/c-language-reference.md)
