---
title: Microsoft C++ 언어 규칙 테이블
description: Microsoft C++ 규칙 테이블은 Visual Studio 버전에 따라 업데이트됩니다.
ms.date: 03/17/2020
ms.technology: cpp-language
ms.assetid: 475da6e9-0d78-4b4e-bd23-f41c406c4efe
author: corob-msft
ms.author: corob
ms.openlocfilehash: 8a5ffb5b3ab4bc80cb200b41752b19d1c958ece6
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079368"
---
# <a name="microsoft-c-language-conformance-table"></a>Microsoft C++ 언어 규칙 테이블

Visual Studio(MSVC)의 Microsoft C++ 컴파일러에 대한 표준 규칙은 진행 중인 작업입니다. 다음은 Microsoft ISO 표준 C++ 언어 및 Visual Studio의 라이브러리 규칙에 대한 요약입니다. 각 컴파일러 및 표준 라이브러리 기능 이름은 기능을 설명하는 ISO 표준 C++ 제안 문서에 연결됩니다(게시 시점에 사용 가능한 경우). **지원됨** 열에는 기능에 대한 지원이 먼저 표시되는 Visual Studio 버전이 나열됩니다.

Visual Studio 2017 또는 Visual Studio 2019 MSVC 규칙 향상에 대한 자세한 내용은 [Visual Studio의 C++ 규칙 향상](cpp-conformance-improvements.md)을 참조하세요. 기타 변경 내용의 목록은 [새로워진 Visual Studio의 Visual C++ 기능](what-s-new-for-visual-cpp-in-visual-studio.md)을 참조하세요. 이전 버전의 규칙 변경 내용에 대해서는 [Visual C++ change history](../porting/visual-cpp-change-history-2003-2015.md)(Visual C++ 주요 변경 내용) 및 [2003~ 2015 Visual C++ 주요 변경 내용](../porting/visual-cpp-what-s-new-2003-through-2015.md)을 참조하세요. C++ 팀의 최신 뉴스를 보려면 [C++ 팀 블로그](https://devblogs.microsoft.com/cppblog/)를 방문하세요.

> [!NOTE]
> Visual Studio 2015, Visual Studio 2017 및 Visual Studio 2019 간에는 주요 이진 변경 내용이 없습니다. 자세한 내용은 [Visual Studio 2015, Visual Studio 2017, Visual Studio 2019 간의 C++ 이진 호환성](../porting/binary-compat-2015-2017.md)을 참조하세요.

## <a name="compiler-features"></a>컴파일러 기능

|  |  |
|--|--|
| __C++03/11 핵심 언어 기능__ | __지원됨__ |
| &nbsp;&nbsp;그 밖의 모든 항목 | VS 2015 <sup>[A](#note_A)</sup> |
| &nbsp;&nbsp;2단계 이름 조회 | VS 2017 15.7 <sup>[B](#note_B)</sup> |
| &nbsp;&nbsp;[N2634 Expression SFINAE](https://wg21.link/N2634) | VS 2017 15.7 |
| &nbsp;&nbsp;[N1653 C99 전처리기](https://wg21.link/N1653) | 부분 <sup>[C](#note_C)</sup> |
| __C++14 핵심 언어 기능__ | __지원됨__ |
| &nbsp;&nbsp;[N3323 컨텍스트 변환에 대해 조정된 표현](https://wg21.link/N3323) | VS 2013 |
| &nbsp;&nbsp;[N3472 이진 리터럴](https://wg21.link/N3472) | VS 2015 |
| &nbsp;&nbsp;[N3638 auto 및 decltype(auto) 반환 형식](https://wg21.link/n3638) | VS 2015 |
| &nbsp;&nbsp;[N3648 init 캡처](https://wg21.link/n3648) | VS 2015 |
| &nbsp;&nbsp;[N3649 제네릭 람다](https://wg21.link/n3649) | VS 2015 |
| &nbsp;&nbsp;[N3760 \[\[deprecated\]\] attribute](https://wg21.link/n3760)(N3760 [[deprecated]] 특성) | VS 2015 |
| &nbsp;&nbsp;[N3778 크기가 지정된 할당 해제](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3781 자릿수 구분 기호](https://wg21.link/n3781) | VS 2015 |
| &nbsp;&nbsp;[N3651 변수 템플릿](https://wg21.link/n3651) | VS 2015.2 |
| &nbsp;&nbsp;[N3652 확장된 constexpr](https://wg21.link/n3652) | VS 2017 15.0 |
| &nbsp;&nbsp;[N3653 Default member initializers for aggregates](https://wg21.link/n3653)(N3653 집계에 대한 기본 멤버 이니셜라이저) | VS 2017 15.0 |
| __C++17 핵심 언어 기능__ | __지원됨__ |
| &nbsp;&nbsp;[N4086 삼중자 제거](https://wg21.link/n4086) | VS 2010 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N3922 중괄호로 묶인 Init 목록을 사용한 auto에 대한 새 규칙](https://wg21.link/n3922) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4051 템플릿 template-parameters의 typename](https://wg21.link/n4051) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4266 네임스페이스 및 열거자에 대한 특성](https://wg21.link/n4266) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4267 u8 문자 리터럴](https://wg21.link/n4267) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4230 중첩된 네임스페이스 정의](https://wg21.link/n4230) | VS 2015.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N3928 간결한 static_assert](https://wg21.link/n3928) | VS 2017 15.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0184R0 일반화된 범위 기반 for 루프](https://wg21.link/p0184r0) | VS 2017 15.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0188R1 \[\[fallthrough\]\] attribute](https://wg21.link/p0188r1)(P0188R1 [[fallthrough]] 특성) | VS 2017 15.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0001R1 레지스터 키워드 제거](https://wg21.link/p0001r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0002R1 bool 형식 operator++ 제거](https://wg21.link/p0002r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0018R3 값으로 *this 캡처](https://wg21.link/p0018r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0028R4 반복 없이 특성 네임스페이스 사용](https://wg21.link/p0028r4) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0061R1 \_\_has_include](https://wg21.link/p0061r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0138R2 정수에서 고정 열거형 Direct-list-init](https://wg21.link/p0138r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0170R1 constexpr 람다](https://wg21.link/p0170r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0189R1 \[\[nodiscard\]\] attribute](https://wg21.link/p0189r1)(P0189R1 [[nodiscard]] 특성) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0212R1 \[\[maybe_unused\]\] attribute](https://wg21.link/p0212r1)(P0212R1 [[maybe_unused]] 특성) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0217R3 구조적 바인딩](https://wg21.link/p0217r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0292R2 constexpr if 문](https://wg21.link/p0292r2) | VS 2017 15.3 <sup>[D](#note_D)</sup> |
| &nbsp;&nbsp;[P0305R1 이니셜라이저를 사용하는 선택 문](https://wg21.link/p0305r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0245R1 Hexfloat 리터럴](https://wg21.link/p0245r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4268 더 많은 비형식 템플릿 인수 허용](https://wg21.link/n4268) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4295 식 폴딩](https://wg21.link/n4295) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 동적 예외 사양 제거](https://wg21.link/p0003r5) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0012R1 형식 시스템에 noexcept 추가](https://wg21.link/p0012r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0035R4 과다 정렬된 동적 메모리 할당](https://wg21.link/p0035r4) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0386R2 인라인 변수](https://wg21.link/p0386r2) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0522R0 template-parameters 템플릿을 호환되는 인수와 일치](https://wg21.link/p0522r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0036R0 일부 비어 있는 단항 폴드 제거](https://wg21.link/p0036r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[N4261 한정 변환 수정](https://wg21.link/n4261) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0017R1 확장된 집계 초기화](https://wg21.link/p0017r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0091R3 클래스 템플릿에 대한 템플릿 인수 추론](https://wg21.link/p0091r3)<br/>&nbsp;&nbsp;[P0512R0 클래스 템플릿 인수 추론 문제(영문)](https://wg21.link/p0512r0) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0127R2 자동으로 비형식 템플릿 매개 변수 선언](https://wg21.link/p0127r2) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0135R1 보장된 복사 생략](https://wg21.link/p0135r1) | VS 2017 15.6 |
| &nbsp;&nbsp;[P0136R1 상속 생성자 다시 표시](https://wg21.link/p0136r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0137R1 std::launder](https://wg21.link/p0137r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0145R3 식 계산 순서 구체화](https://wg21.link/p0145r3)<br/>&nbsp;&nbsp;[P0400R0 함수 인수 평가 순서(영문)](https://wg21.link/p0400r0) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0195R2 using 선언의 팩 확장](https://wg21.link/p0195r2) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0283R2 인식할 수 없는 특성 무시](https://wg21.link/p0283r2) | VS 2015 <sup>[14](#note_14)</sup> |
| __C++17 핵심 언어 기능(결함 보고서)__ | __지원됨__ |
| &nbsp;&nbsp;[P0702R1 이니셜라이저 목록 작업자(initializer-list actors)에 대한 클래스 템플릿 인수 추론 문제 해결(영문)](https://wg21.link/p0702r1) | VS 2017 15.7 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0961R1 Relaxing the structured bindings customization point finding rules](https://wg21.link/p0961r1)(P0961R1 구조적 바인딩 사용자 지정 지점 찾기 규칙 완화) | VS 2019 16.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0969R0 액세스할 수 있는 멤버에게 구조화된 바인딩 허용](https://wg21.link/p0969r0) | VS 2019 16.0 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0588R1 암시적 람다 캡처 단순화](https://wg21.link/p0588r1) | VS 2019 16.4 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P1771R1 생성자용 \[\[nodiscard\]\]](https://wg21.link/p1771r1) | VS 2019 16.4 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P1825R0 P0527R1 및 P1155R3에 대한 병합된 문구, 암시적 동작](https://wg21.link/p1825r0) | VS 2019 16.4 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0929R2 Checking for abstract class types](https://wg21.link/P0929R2)(P0929R2 추상 클래스 형식 확인) | 아니요 |
| &nbsp;&nbsp;[P0962R2 range-for 루프 사용자 지정 지점 찾기 규칙 완화](https://wg21.link/p0962r1) | 아니요 |
| &nbsp;&nbsp;[P0859R0 CWG 1581: constexpr 멤버 함수가 정의되는 시기](https://wg21.link/p0859r0) | 아니요 |
| &nbsp;&nbsp;[P1009R2 Array size deduction in new-expressions](https://wg21.link/P1009R2)(P1009R2 새 식의 배열 크기 감소) | 아니요 |
| &nbsp;&nbsp;[P1286R2 Contra CWG DR1778](https://wg21.link/P1286R2) | 아니요 |
| __C++20 핵심 언어 기능__ | __지원됨__ |
| &nbsp;&nbsp;[P0704R1 멤버에 대한 const lvalue ref-qualified 포인터 수정(영문)](https://wg21.link/p0704r1) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1041R4 Make char16_t/char32_t string literals be UTF-16/32](https://wg21.link/P1041R4)(P1041R4 char16_t/char32_t 문자열 리터럴을 UTF-16/32로 설정) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1330R0 Changing the active member of a union inside constexpr](https://wg21.link/P1330R0)(P1330R0 constexpr 내부 공용 구조체의 활성 멤버 변경) | VS 2017 15.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0972R0 noexcept For \<chrono> zero(), min(), max()](https://wg21.link/P0972R0)(P0972R0 <chrono> zero(), min(), max()에 대한 noexcept) | VS 2017 15.7 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0515R3 3방향(우주선) 비교 연산자 <=>](https://wg21.link/P0515R3) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0941R2 Feature-test macros](https://wg21.link/P0941R2)(P0941R2 기능 테스트 매크로) | VS 2019 16.0 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1008R1 Prohibiting aggregates with user-declared constructors](https://wg21.link/P1008R1)(P1008R1 사용자 선언 생성자를 사용하여 집계 금지) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0329R4 지정된 초기화(영문)](https://wg21.link/p0329r4) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0846R0 ADL and function templates that are not visible](https://wg21.link/P0846R0)(P0846R0 표시되지 않는 ADL 및 함수 템플릿) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0409R2 Allowing lambda-capture \[=, this\]](https://wg21.link/p0409r2)(P0409R2 람다 캡처 [=, this] 허용) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0428R2 일반 람다에 대한 친숙한 템플릿 구문(영문)](https://wg21.link/p0428r2) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0624R2 Default constructible and assignable stateless lambdas](https://wg21.link/P0624R2)(P0624R2 기본 constructible 및 assignable stateless 람다) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0780R2 Allowing pack expansion in lambda init-capture](https://wg21.link/P0780R2)(P0780R2 람다 init 캡처에서 팩 확장 허용) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0806R2 Deprecate implicit capture of this via \[=\]](https://wg21.link/P0806R2)(P0806R2 [[=]]를 통해 this의 암시적 캡처 사용 중단) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1120R0 Consistency improvements for <=> and other comparison operators](https://wg21.link/P1120R0)(P1120R0 <=> 및 기타 비교 연산자의 일관성 향상) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1185R2 \<=\> != ==](https://wg21.link/P1185R2) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0734R0 개념(영문)](https://wg21.link/P0734R0) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0857R0 Fixing functionality gaps in constraints](https://wg21.link/P0857R0)(P0857R0 제약 조건의 기능 차이 수정) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1084R2 Today's return-type-requirements are insufficient](https://wg21.link/P1084R2)(P1084R2 현재 반환 형식 요구 사항이 부족함) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0892R2 Conditional explicit](https://wg21.link/P0892R2)(P0892R2 조건부 명시적) | VS 2019 16.4 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1091R3 Extending structured bindings to be more like variable declarations](https://wg21.link/P1091R3)(P1091R3 구조적 바인딩을 변수 선언과 더 비슷하게 확장) | VS 2019 16.4 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1099R5 열거형 사용](https://wg21.link/P1099R5) | VS 2019 16.4 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1186R3 \<=>를 실제로 사용하는 경우](https://wg21.link/P1186R3) | VS 2019 16.4 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1630R1 우주선에 조정 필요](https://wg21.link/P1630R1) | VS 2019 16.4 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0306R4 쉼표 생략 및 쉼표 삭제에 \_\_VA_OPT\_\_ 추가(영문)](https://wg21.link/P0306R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0614R1 Range-based for-loops with initializers](https://wg21.link/P0614R1)(P0614R1 이니셜라이저를 사용한 범위 기반 for 루프) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0683R1 비트 필드에 대한 기본 멤버 이니셜라이저(영문)](https://wg21.link/P0683R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1002R1 try-catch blocks in constexpr functions](https://wg21.link/P1002R1)(P1002R1 constexpr 함수의 try-catch 블록) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1161R3 첨자 식에서의 쉼표 연산자 사용 중단](https://wg21.link/P1161R3) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1301R4 \[\[nodiscard("메시지")\]\]](https://wg21.link/P1301R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1703R1 가져온 헤더 단위를 인식하려면 전체 전처리 필요](https://wg21.link/P1703R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1946R0 값에 의한 기본값 비교 허용](https://wg21.link/P1946R0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0641R2 const mismatch with defaulted copy constructor](https://wg21.link/P0641R2)(P0641R2 기본 복사 생성자와 const 불일치) | Partial |
| &nbsp;&nbsp;[P0912R5 Coroutines](https://wg21.link/P0912R5)(P0912R5 코루틴) | Partial |
| &nbsp;&nbsp;[P1103R3 Modules](https://wg21.link/P1103R3)(P1103R3 모듈) | Partial |
| &nbsp;&nbsp;[P0315R4 Allowing lambdas in unevaluated contexts](https://wg21.link/P0315R4)(P0315R4 평가되지 않은 컨텍스트에서 람다 허용) | 아니요 |
| &nbsp;&nbsp;[P0388R4 범위를 알 수 없는 배열로의 변환 허용](https://wg21.link/P0388R4) | 아니요 |
| &nbsp;&nbsp;[P0479R5 \[\[likely\]\] and \[\[unlikely\]\] attributes](https://wg21.link/P0479R5)(P0479R5 [[likely]] 및 [[unlikely]] 특성) | 아니요 |
| &nbsp;&nbsp;[P0634R3 Down with typename!](https://wg21.link/P0634R3)(P0634R3 typename을 사용한 다운!) | 아니요 |
| &nbsp;&nbsp;[P0692R1 Relaxing access checking on specializations](https://wg21.link/P0692R1)(P0692R1 특수화를 확인하는 액세스 완화) | 아니요 |
| &nbsp;&nbsp;[P0722R3 Efficient sized delete for variable sized classes](https://wg21.link/P0722R3)(P0722R3 변수 크기 클래스의 효율적 크기 삭제) | 아니요 |
| &nbsp;&nbsp;[P0732R2 Class types in non-type template parameters](https://wg21.link/P0732R2)(P0732R2 비형식 템플릿 매개 변수의 클래스 형식) | 아니요 |
| &nbsp;&nbsp;[P0735R1 memory_order_consume과 릴리스 시퀀스의 상호 작용](https://wg21.link/P0735R1) | 아니요 |
| &nbsp;&nbsp;[P0784R7 추가 constexpr 컨테이너](https://wg21.link/P0784R7) | 아니요 |
| &nbsp;&nbsp;[P0840R2 \[\[no_unique_address\]\] attribute](https://wg21.link/P0840R2)(P0840R2 [[no_unique_address]] 특성) | 아니요 |
| &nbsp;&nbsp;[P0848R3 조건부 trivial 형식의 특수 멤버 함수](https://wg21.link/P0848R3) | 아니요 |
| &nbsp;&nbsp;[P0960R3 Allow initializing aggregates from a parenthesized list of values](https://wg21.link/P0960R3)(P0960R3 괄호로 묶인 값 목록에서 집계 초기화 허용) | 아니요 |
| &nbsp;&nbsp;[P1064R0 Allowing virtual function calls in constant expressions](https://wg21.link/P1064R0)(P1064R0 상수 식에서 가상 함수 호출 허용) | 아니요 |
| &nbsp;&nbsp;[P1073R3 Immediate functions](https://wg21.link/P1073R3)(P1073R3 직접 함수) | 아니요 |
| &nbsp;&nbsp;[P1094R2 Nested inline namespaces](https://wg21.link/P1094R2)(P1094R2 중첩 인라인 네임스페이스) | 아니요 |
| &nbsp;&nbsp;[P1139R2 Address wording issues related to ISO 10646](https://wg21.link/P1139R2)(P1139R2 ISO 10646에 관련된 단어 문제 해결) | 아니요 |
| &nbsp;&nbsp;[P1141R2 Yet another approach for constrained declarations](https://wg21.link/P1141R2)(P1141R2 제한된 선언의 또 다른 접근 방식) | 아니요 |
| &nbsp;&nbsp;[P1143R2 constinit](https://wg21.link/P1143R2) | 아니요 |
| &nbsp;&nbsp;[P1152R4 volatile 사용 중단](https://wg21.link/P1152R4) | 아니요 |
| &nbsp;&nbsp;[P1236R1 Signed integers are two's complement](https://wg21.link/P1236R1)(P1236R1 부호 있는 정수가 2의 보수임) | 아니요 |
| &nbsp;&nbsp;[P1327R1 Allowing dynamic_cast, polymorphic typeid in constant expressions](https://wg21.link/P1327R1)(P1327R1 상수 식에서 dynamic_cast, 다형 typeid 허용) | 아니요 |
| &nbsp;&nbsp;[P1331R2 constexpr 컨텍스트에서 trivial 형식의 기본 초기화 허용](https://wg21.link/P1331R2) | 아니요 |
| &nbsp;&nbsp;[P1353R0 Missing feature-test macros](https://wg21.link/P1353R0)(P1353R0 기능 테스트 매크로 누락) | 아니요 |
| &nbsp;&nbsp;[P1381R1 Reference capture of structured bindings](https://wg21.link/P1381R1)(P1381R1 구조적 바인딩의 참조 캡처) | 아니요 |
| &nbsp;&nbsp;[P1452R2 return-type-requirements의 균일하지 않은 의미 체계](https://wg21.link/P1452R2) | 아니요 |
| &nbsp;&nbsp;[P1616R1 제약 조건이 있는 TTP를 제약 조건이 있는 템플릿과 함께 사용](https://wg21.link/P1616R1) | 아니요 |
| &nbsp;&nbsp;[P1668R1 constexpr 함수에서 확인되지 않은 인라인 어셈블리 허용](https://wg21.link/P1668R1) | 아니요 |
| &nbsp;&nbsp;[P1766R1 사소한 모듈 문제의 영향 줄이기](https://wg21.link/P1766R1) | 아니요 |
| &nbsp;&nbsp;[P1811R0 다시 내보내기 강건성을 위한 재정의 제한 사항 완화](https://wg21.link/P1811R0) | 아니요 |
| &nbsp;&nbsp;[P1814R0 별칭 템플릿의 CTAD](https://wg21.link/P1814R0) | 아니요 |
| &nbsp;&nbsp;[P1816R0 집계의 CTAD](https://wg21.link/P1816R0) | 아니요 |
| &nbsp;&nbsp;[P1874R1 모듈의 비 지역 변수 동적 초기화 순서](https://wg21.link/P1874R1) | 아니요 |
| &nbsp;&nbsp;[P1907R1 비형식 템플릿 매개 변수의 불일치](https://wg21.link/P1907R1) | 아니요 |
| &nbsp;&nbsp;[P1971R0 2019년 11월(벨파스트) 미팅에서 합의된 NB 주석의 주요 변경 내요](https://wg21.link/P1971R0) | 아니요 |
| &nbsp;&nbsp;[P1972R0 US105 함수에 대한 포인터 설정 시 비형식에 대한 제약 조건 만족도 검사](https://wg21.link/P1972R0) | 아니요 |
| &nbsp;&nbsp;[P1975R0 괄호로 묶인 집계 초기화의 표현 수정](https://wg21.link/P1975R0) | 아니요 |
| &nbsp;&nbsp;[P1979R0 US086 준수](https://wg21.link/P1979R0) | 아니요 |
| &nbsp;&nbsp;[P1980R0 CA096: 종속되지 않은 requires 절의 선언 일치](https://wg21.link/P1980R0) | 아니요 |

## <a name="standard-library-features"></a>표준 라이브러리 기능

|  |  |
|--|--|
| __C++20 표준 라이브러리 기능__ | __지원됨__ |
| &nbsp;&nbsp;[P0809R0 정렬되지 않은 컨테이너 비교](https://wg21.link/p0809r0) | VS 2010 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0858R0 Constexpr 반복기의 요구 사항](https://wg21.link/p0858r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0777R1 Avoiding Unnecessary Decay](https://wg21.link/p0777r1)(P0777R1 불필요한 감소 방지) | VS 2017 15.7 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P1164R1 create_directory()를 직관적으로 만들기](https://wg21.link/P1164R1) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0550R2 remove_cvref](https://wg21.link/p0550r2) | VS 2019 16.0 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0318R1 unwrap_reference, unwrap_ref_decay](https://wg21.link/p0318r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0457R2 starts_with()/ends_with() For basic_string/basic_string_view](https://wg21.link/p0457r2)(P0457R2 basic_string/basic_string_view에 대한 starts_with()/ends_with()) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0458R2 contains() For Ordered And Unordered Associative Containers](https://wg21.link/p0458r2)(P0458R2 순서 있는 및 순서 없는 연관 컨테이너에 대한 contains()) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0646R1 list/forward_list remove()/remove_if()/unique() Return size_type](https://wg21.link/p0646r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0769R2 shift_left(), shift_right()](https://wg21.link/p0769r2) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0887R1 type_identity](https://wg21.link/p0887r1) | VS 2019 16.1 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0020R6 atomic\<float>, atomic\<double>, atomic\<long double>](https://wg21.link/p0020r6) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0463R1 endian(영문)](https://wg21.link/p0463r1) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0482R6 char8_t: A type for UTF-8 characters and strings](https://wg21.link/P0482R6)(P0482R6 char8_t: UTF-8 문자 및 문자열 형식) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0600R1 \[\[nodiscard\]\] For The STL, Part 1](https://wg21.link/p0600r1)(P0600R1 STL, Part 1에 대한 [[nodiscard]]) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0754R2 \<version>](https://wg21.link/p0754r2) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0771R1 noexcept For std::function's Move Constructor](https://wg21.link/P0771R1)(std::function의 이동 생성자에 대한 noexcept) | VS 2019 16.2 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0487R1 연산자>>(basic_istream&, CharT* 수정](https://wg21.link/P0487R1) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0616R0 Using move() In \<numeric>](https://wg21.link/p0616r0)(P0616R0 <numeric>에서 move() 사용) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0758R1 is_nothrow_convertible](https://wg21.link/P0758R1) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0898R3 Standard Library Concepts](https://wg21.link/P0898R3)(P0898R3 표준 라이브러리 개념) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0919R3 Heterogeneous Lookup For Unordered Containers](https://wg21.link/P0919R3)(P0919R3 순서 없는 컨테이너에 대한 이종 조회) | VS 2019 16.3 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1754R1 개념 이름을 standard_case로 변경](https://wg21.link/P1754R1) | VS 2019 16.4 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0325R4 업데이트가 적용된 LFTS의 to_array](https://wg21.link/P0325R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0340R3 SFINAE-Friendly underlying_type](https://wg21.link/P0340R3) | VS 2019 16.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0356R5 bind_front()](https://wg21.link/P0356R5) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0439R0 enum class memory_order](https://wg21.link/p0439r0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0553R4 \<bit> 회전 및 개수 세기 함수](https://wg21.link/P0553R4) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0556R3 \<bit> ispow2(), ceil2(), floor2(), log2p1()](https://wg21.link/P0556R3) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0595R2 is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0631R8 \<numbers> Math 상수](https://wg21.link/P0631R8) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0738R2 istream_iterator Cleanup](https://wg21.link/P0738R2)(P0738R2 istream_iterator 정리) | VS 2019 16.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0767R1 Deprecating is_pod](https://wg21.link/P0767R1)(P0767R1 is_pod 사용 중단) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0966R1 string::reserve() Should Not Shrink](https://wg21.link/P0966R1)(P0966R1 string::reserve() 축소하지 않아야 함) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1209R0 erase_if(), erase()](https://wg21.link/P1209R0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1227R2 Signed std::ssize(), Unsigned span::size()](https://wg21.link/P1227R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1355R2 ceil2()의 좁은 제약](https://wg21.link/P1355R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1357R1 is_bounded_array, is_unbounded_array](https://wg21.link/P1357R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1612R1 endian을 \<bit>으로 이동](https://wg21.link/P1612R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1651R0 bind_front()가 reference_wrapper를 래핑 해제하면 안 됨](https://wg21.link/P1651R0) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1690R1 순서 없는 컨테이너의 이종 조회 개선](https://wg21.link/P1690R1) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P1902R1 누락된 기능 테스트 매크로 2017~2019](https://wg21.link/P1902R1) | VS 2019 16.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0019R8 atomic_ref](https://wg21.link/P0019R8) | 아니요 |
| &nbsp;&nbsp;[P0053R7 \<syncstream>](https://wg21.link/p0053r7)<br/>&nbsp;&nbsp;[P0753R2 osyncstream Manipulators](https://wg21.link/p0753r2)(P0753R2 osyncstream 조작자) | 아니요 |
| &nbsp;&nbsp;[P0122R7 \<span>](https://wg21.link/p0122r7) | 아니요 |
| &nbsp;&nbsp;[P0202R3 constexpr For \<algorithm> And exchange()](https://wg21.link/p0202r3)(P0202R3 <algorithm> 및 exchange()에 대한 constexpr) | 아니요 |
| &nbsp;&nbsp;[P0339R6 polymorphic_allocator<>](https://wg21.link/P0339R6) | 아니요 |
| &nbsp;&nbsp;[P0355R7 \<chrono> Calendars And Time Zones](https://wg21.link/p0355r7)(P0355R7 <chrono> 일정 및 표준 시간대) | 아니요 |
| &nbsp;&nbsp;[P0357R3 Supporting Incomplete Types In reference_wrapper](https://wg21.link/P0357R3)(P0357R3 reference_wrapper에서 불완전한 형식 지원) | 아니요 |
| &nbsp;&nbsp;[P0415R1 constexpr For \<complex> (Again)](https://wg21.link/p0415r1)(P0415R1 <complex>(다시 실행)에 대한 constexpr) | 아니요 |
| &nbsp;&nbsp;[P0475R1 Guaranteed Copy Elision For Piecewise Construction](https://wg21.link/P0475R1)(P0475R1 Piecewise 구문에 대한 보장된 복사 생략) | 아니요 |
| &nbsp;&nbsp;[P0476R2 \<bit> bit_cast](https://wg21.link/P0476R2) | 아니요 |
| &nbsp;&nbsp;[P0528R3 Atomic Compare-And-Exchange With Padding Bits](https://wg21.link/P0528R3)(P0528R3 패딩 비트를 사용한 원자성 비교 및 교환) | 아니요 |
| &nbsp;&nbsp;[P0591R4 Utility Functions For Uses-Allocator Construction](https://wg21.link/P0591R4)(P0591R4 할당자 사용 구문에 대한 유틸리티 함수) | 아니요 |
| &nbsp;&nbsp;[P0608R3 Improving variant's Converting Constructor/Assignment](https://wg21.link/P0608R3)(P0608R3 variant의 변환 생성자/할당 개선) | 아니요 |
| &nbsp;&nbsp;[P0619R4 Removing C++17-Deprecated Features In C++20](https://wg21.link/P0619R4)(P0619R4 C++20에서 C++17의 사용 중단 기능 제거) | 아니요 |
| &nbsp;&nbsp;[P0653R2 to_address()](https://wg21.link/p0653r2) | 아니요 |
| &nbsp;&nbsp;[P0655R1 visit\<R>()](https://wg21.link/P0655R1) | 아니요 |
| &nbsp;&nbsp;[P0674R1 배열에 대한 make_shared()(영문)](https://wg21.link/p0674r1) | 아니요 |
| &nbsp;&nbsp;[P0718R2 atomic\<shared_ptr\<T>>, atomic\<weak_ptr\<T>>](https://wg21.link/p0718r2) | 아니요 |
| &nbsp;&nbsp;[P0768R1 Library Support For The Spaceship Comparison Operator \<=>](https://wg21.link/p0768r1)(우주선 비교 연산자에 대한 라이브러리 지원) | 아니요 |
| &nbsp;&nbsp;[P0811R3 midpoint(), lerp()](https://wg21.link/P0811R3) | 아니요 |
| &nbsp;&nbsp;[P0879R0 constexpr For Swapping Functions](https://wg21.link/P0879R0)(P0879R0 함수 교환을 위한 constexpr) | 아니요 |
| &nbsp;&nbsp;[P0896R4 \<ranges\>](https://wg21.link/P0896R4) | 아니요 |
| &nbsp;&nbsp;[P0912R5 Library Support For Coroutines](https://wg21.link/P0912R5)(P0912R5 코루틴에 대한 라이브러리 지원) | 아니요 |
| &nbsp;&nbsp;[P0920R2 Precalculated Hash Value Lookup](https://wg21.link/P0920R2)(P0920R2 미리 계산된 해시 값 조회) | 아니요 |
| &nbsp;&nbsp;[P0935R0 Eradicating Unnecessarily Explicit Default Constructors](https://wg21.link/P0935R0)(P0935R0 불필요하게 명시적인 기본 생성자 제거) | 아니요 |
| &nbsp;&nbsp;[P1001R2 execution::unseq](https://wg21.link/P1001R2) | 아니요 |
| &nbsp;&nbsp;[P1006R1 pointer_traits<T*>::pointer_to()에 대한 constexpr](https://wg21.link/P1006R1) | 아니요 |
| &nbsp;&nbsp;[P1007R3 assume_aligned()](https://wg21.link/P1007R3) | 아니요 |
| &nbsp;&nbsp;[P1020R1 Smart Pointer Creation With Default Initialization](https://wg21.link/P1020R1)(P1020R1 기본 초기화를 사용한 스마트 포인터 만들기) | 아니요 |
| &nbsp;&nbsp;[P1023R0 constexpr For std::array Comparisons](https://wg21.link/P1023R0)(P1023R0 std::array 비교에 대한 constexpr) | 아니요 |
| &nbsp;&nbsp;[P1032R1 Miscellaneous constexpr](https://wg21.link/P1032R1)(P1032R1 기타 constexpr) | 아니요 |
| &nbsp;&nbsp;[P1165R1 Consistently Propagating Stateful Allocators In basic_string's operator+()](https://wg21.link/P1165R1)(P1165R1 basic_string의 operator+()에서 상태 저장 할당자를 일관적으로 전파) | 아니요 |
| &nbsp;&nbsp;[P1285R0 Improving Completeness Requirements For Type Traits](https://wg21.link/P1285R0)(P1285R0 형식 특성에 대한 완전성 요구 사항 개선) | 아니요 |
| __C++17 표준 라이브러리 기능__ | __지원됨__ |
| &nbsp;&nbsp;[LWG 2221 Formatted output operator for nullptr](https://cplusplus.github.io/LWG/issue2221)(LWG 2221 nullptr에 대한 서식 있는 출력 연산자) | VS 2019 16.1 |
| &nbsp;&nbsp;[N3911 void_t](https://wg21.link/n3911) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4089 unique_ptr\<T[]>에서 안전하게 변환](https://wg21.link/n4089) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4169 invoke()](https://wg21.link/n4169) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4190 auto_ptr, random_shuffle() 및 이전 \<functional> 항목 제거](https://wg21.link/n4190) | VS 2015 <sup>[rem](#note_rem)</sup> |
| &nbsp;&nbsp;[N4258 noexcept 정리](https://wg21.link/n4258) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4259 uncaught_exceptions](https://wg21.link/n4259) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4277 일반적으로 복사 가능한 reference_wrapper](https://wg21.link/n4277) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4279 map/unordered_map에 대한 insert_or_assign()/try_emplace()](https://wg21.link/n4279) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4280 size(), empty(), data()](https://wg21.link/n4280) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4366 정확하게 unique_ptr 할당 제약](https://wg21.link/n4366) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4387 쌍 및 튜플 향상](https://wg21.link/n4387) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4389 bool_constant](https://wg21.link/n4389) | VS 2015 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4508 shared_mutex(시간 제한 없음)](https://wg21.link/n4508) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4510 vector/list/forward_list에서 불완전한 형식 지원](https://wg21.link/n4510) | VS 2013 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<algorithm> sample()](https://wg21.link/n4562#alg.random.sample) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<any>](https://wg21.link/n4562#any) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<memory_resource>](https://wg21.link/n4562#memory.resource.synop)<br/>&nbsp;&nbsp;[P0337R0 polymorphic_allocator 할당 삭제](https://wg21.link/p0337r0) | VS 2017 15.6 |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<optional>](https://wg21.link/n4562#optional) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<string_view>](https://wg21.link/n4562#string.view) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: \<tuple> apply()](https://wg21.link/n4562#tuple) | VS 2017 15.0 |
| &nbsp;&nbsp;[N4562 라이브러리 기본 사항: Boyer-Moore search()](https://wg21.link/n4562#func.searchers.boyer_moore)<br/>&nbsp;&nbsp;[P0253R1 검색자 반환 형식 수정](https://wg21.link/p0253r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0003R5 동적 예외 사양 제거](https://wg21.link/p0003r5) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0004R1 사용되지 않는 Iostreams 별칭 제거](https://wg21.link/p0004r1) | VS 2015.2 <sup>[rem](#note_rem)</sup> |
| &nbsp;&nbsp;[P0005R4 not_fn()](https://wg21.link/p0005r4)<br/>&nbsp;&nbsp;[P0358R1 not_fn()에 대한 수정 사항](https://wg21.link/p0358r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0006R0 형식 특성에 대한 변수 템플릿(is_same_v 등)](https://wg21.link/p0006r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0007R1 as_const()](https://wg21.link/p0007r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0013R1 논리 연산자 형식 특성(conjunction 등)](https://wg21.link/p0013r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0024R2 병렬 알고리즘](https://wg21.link/p0024r2)<br/>&nbsp;&nbsp;[P0336R1 병렬 실행 정책 이름 바꾸기](https://wg21.link/p0336r1)<br/>&nbsp;&nbsp;[P0394R4 예외가 발생할 경우 병렬 알고리즘을 종료()해야 함](https://wg21.link/p0394r4)<br/>&nbsp;&nbsp;[P0452R1 \<numeric> 병렬 알고리즘 통합(영문)](https://wg21.link/p0452r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0025R1 clamp()](https://wg21.link/p0025r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0030R1 hypot(x, y, z)](https://wg21.link/p0030r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0031R0 \<array>(다시 실행) 및 \<iterator>에 대한 constexpr](https://wg21.link/p0031r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0032R3 variant/any/optional에 대한 동종 인터페이스](https://wg21.link/p0032r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0033R1 enable_shared_from_this 다시 표시](https://wg21.link/p0033r1) | VS 2017 15.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0040R3 메모리 관리 도구 확장](https://wg21.link/p0040r3) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0063R3 C11 표준 라이브러리](https://wg21.link/p0063r3) | VS 2015 <sup>[C11](#note_C11), [14](#note_14)</sup> |
| &nbsp;&nbsp;[P0067R5 기본 문자열 변환](https://wg21.link/p0067r5) | VS 2019 16.4 <sup>[charconv](#note_charconv)</sup> |
| &nbsp;&nbsp;[P0074R0 owner_less\<>](https://wg21.link/p0074r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0077R2 is_callable, is_nothrow_callable](https://wg21.link/p0077r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0083R3 맵 및 집합 스플라이스](https://wg21.link/p0083r3)<br/>&nbsp;&nbsp;[P0508R0 명확히 insert_return_type 설명](https://wg21.link/p0508r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0084R2 Emplace 반환 형식](https://wg21.link/p0084r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0088R3 \<variant>](https://wg21.link/p0088r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0092R1 \<chrono> floor(), ceil(), round(), abs()](https://wg21.link/p0092r1) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0152R1 atomic::is_always_lock_free](https://wg21.link/p0152r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0154R1 hardware_destructive_interference_size 등](https://wg21.link/p0154r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0156R0 Variadic lock_guard](https://wg21.link/p0156r0) | VS 2015.2 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0156R2 Variadic lock\_guard를 scoped\_lock으로 이름 바꾸기(영문)](https://wg21.link/p0156r2) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0163R0 shared_ptr::weak_type](https://wg21.link/p0163r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0174R2 남아 있는 라이브러리 파트 사용 중단](https://wg21.link/p0174r2) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0185R1 is_swappable, is_nothrow_swappable](https://wg21.link/p0185r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0209R2 make_from_tuple()](https://wg21.link/p0209r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0218R1 \<filesystem>](https://wg21.link/p0218r1)<br/>&nbsp;&nbsp;[P0219R1 파일 시스템에 대한 상대 경로](https://wg21.link/p0219r1)<br/>&nbsp;&nbsp;[P0317R1 파일 시스템에 대한 디렉터리 항목 캐싱(영문)](https://wg21.link/p0317r1)<br/>&nbsp;&nbsp;[P0392R0 파일 시스템 경로에서 string_view 지원](https://wg21.link/p0392r0)<br/>&nbsp;&nbsp;[P0430R2 비POSIX 파일 시스템 지원(영문)](https://wg21.link/p0430r2)<br/>&nbsp;&nbsp;[P0492R2 파일 시스템에 대한 NB 주석 해석(영문)](https://wg21.link/p0492r2) | VS 2017 15.7 <sup>[E](#note_E)</sup> |
| &nbsp;&nbsp;[P0220R1 라이브러리 기본 사항 V1](https://wg21.link/p0220r1) | VS 2017 15.6 |
| &nbsp;&nbsp;[P0226R1 수학 특수 함수](https://wg21.link/p0226r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0254R2 string_view 및 std::string 통합](https://wg21.link/p0254r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0258R2 has_unique_object_representations](https://wg21.link/p0258r2) | VS 2017 15.3 <sup>[G](#note_G)</sup> |
| &nbsp;&nbsp;[P0272R1 상수가 아닌 basic_string::data()](https://wg21.link/p0272r1) | VS 2015.3 |
| &nbsp;&nbsp;[P0295R0 gcd(), lcm()](https://wg21.link/p0295r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0298R3 std::byte(영문)](https://wg21.link/p0298r3) | VS 2017 15.3 <sup>[17](#note_17),&nbsp;[byte](#note_byte)</sup> |
| &nbsp;&nbsp;[P0302R1 std::function에서 할당자 지원 제거](https://wg21.link/p0302r1) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0307R2 선택적으로 크거나 같게 만들기](https://wg21.link/p0307r2) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0393R3 Variant를 크거나 같게 만들기](https://wg21.link/p0393r3) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0403R1 \<string_view>용 UDL("meow"sv 등)](https://wg21.link/p0403r1) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0414R2 shared_ptr\<T[]>, shared_ptr\<T[N]>](https://wg21.link/p0414r2)<br/>&nbsp;&nbsp;[P0497R0 배열에 대한 shared_ptr 해결](https://wg21.link/p0497r0) | VS 2017 15.5 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0418R2 atomic compare_exchange memory_order 요구 사항](https://wg21.link/p0418r2) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0426R1 char_traits에 대한 constexpr](https://wg21.link/p0426r1) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0433R2 클래스 템플릿에 대한 템플릿 추론을 표준 라이브러리에 통합(영문)](https://wg21.link/p0433r2)<br/>&nbsp;&nbsp;[P0739R0 표준 라이브러리에 클래스 템플릿 인수 추론 통합 향상(영문)](https://wg21.link/p0739r0) | VS 2017 15.7 |
| &nbsp;&nbsp;[P0435R1 common_type 점검](https://wg21.link/p0435r1)<br/>&nbsp;&nbsp;[P0548R1 Tweaking common\_type 및 기간 조정(영문)](https://wg21.link/p0548r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0504R0 in_place_t/in_place_type_t\<T>/in_place_index_t\<I> 다시 방문](https://wg21.link/p0504r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0505R0 \<chrono>(다시 실행)에 대한 constexpr](https://wg21.link/p0505r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0510R0 없음, 배열, 참조, 불완전한 형식의 variant 거부](https://wg21.link/p0510r0) | VS 2017 15.0 |
| &nbsp;&nbsp;[P0513R0 악성 공격 해시](https://wg21.link/p0513r0)<br/>&nbsp;&nbsp;[P0599R1 noexcept 해시(영문)](https://wg21.link/p0599r1) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0516R0 shared_future 복사를 noexcept로 표시](https://wg21.link/p0516r0) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0517R0 future_errc에서 future_error 생성](https://wg21.link/p0517r0) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0521R0 shared_ptr::unique() 사용 중단](https://wg21.link/p0521r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0558R1 Resolving atomic\<T> Named Base Class Inconsistencies](https://wg21.link/p0558r1)(P0558R1 atomic<T> 명명된 기본 클래스 불일치 해결) | VS 2017 15.3 <sup>[14](#note_14)</sup> |
| &nbsp;&nbsp;[P0595R2 std::is_constant_evaluated()](https://wg21.link/P0595R2) | VS 2019 16.5 <sup>[20](#note_20)</sup> |
| &nbsp;&nbsp;[P0602R4 Propagating Copy/Move Triviality In variant/optional](https://wg21.link/P0602R4)(P0602R4 variant/optional에서 복사/이동 사소성(triviality) 전파) | VS 2017 15.3<sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0604R0 is\_callable/result\_of를 invoke\_result, is\_invocable, is\_nothrow\_invocable로 변경(영문)](https://wg21.link/p0604r0) | VS 2017 15.3 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0607R0 표준 라이브러리에 대한 인라인 변수(영문)](https://wg21.link/p0607r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0618R0 \<codecvt> 사용 중단(영문)](https://wg21.link/p0618r0) | VS 2017 15.5 <sup>[17](#note_17)</sup> |
| &nbsp;&nbsp;[P0682R1 Repairing Elementary String Conversions](https://wg21.link/P0682R1)(P0682R1 기본 문자열 변환 복구) | VS 2015 15.7 <sup>[17](#note_17)</sup> |
| __C++14 표준 라이브러리 기능__ | __지원됨__ |
| &nbsp;&nbsp;[N3462 SFINAE-Friendly result_of](https://wg21.link/n3462) | VS 2015.2 |
| &nbsp;&nbsp;[N3302 \<complex>에 대한 constexpr](https://wg21.link/n3302) | VS 2015 |
| &nbsp;&nbsp;[N3469 \<chrono>에 대한 constexpr](https://wg21.link/n3469) | VS 2015 |
| &nbsp;&nbsp;[N3470 \<array>에 대한 constexpr](https://wg21.link/n3470) | VS 2015 |
| &nbsp;&nbsp;[N3471 \<initializer_list>, \<tuple>, \<utility>에 대한 constexpr](https://wg21.link/n3471) | VS 2015 |
| &nbsp;&nbsp;[N3545 integral_constant::operator()()](https://wg21.link/n3545) | VS 2015 |
| &nbsp;&nbsp;[N3642 \<chrono>, \<string>에 대한 UDL(1729ms, "meow" 등)](https://wg21.link/n3642) | VS 2015 |
| &nbsp;&nbsp;[N3644 Null 정방향 반복기](https://wg21.link/n3644) | VS 2015 |
| &nbsp;&nbsp;[N3654 quoted()](https://wg21.link/n3654) | VS 2015 |
| &nbsp;&nbsp;[N3657 유형이 다른 연관 조회](https://wg21.link/n3657) | VS 2015 |
| &nbsp;&nbsp;[N3658 integer_sequence](https://wg21.link/n3658) | VS 2015 |
| &nbsp;&nbsp;[N3659 shared_mutex(시간 제한)](https://wg21.link/n3659) | VS 2015 |
| &nbsp;&nbsp;[N3668 exchange()](https://wg21.link/n3668) | VS 2015 |
| &nbsp;&nbsp;[N3669 const 없는 constexpr 멤버 함수 수정](https://wg21.link/n3669) | VS 2015 |
| &nbsp;&nbsp;[N3670 get\<T>()](https://wg21.link/n3670) | VS 2015 |
| &nbsp;&nbsp;[N3671 이중 범위 equal(), is_permutation(), mismatch()](https://wg21.link/n3671) | VS 2015 |
| &nbsp;&nbsp;[N3778 크기가 지정된 할당 해제](https://wg21.link/n3778) | VS 2015 |
| &nbsp;&nbsp;[N3779 \<complex>에 대한 UDL(3.14i 등)](https://wg21.link/n3779) | VS 2015 |
| &nbsp;&nbsp;[N3789 \<functional>에 대한 constexpr](https://wg21.link/n3789) | VS 2015 |
| &nbsp;&nbsp;[N3887 tuple_element_t](https://wg21.link/n3887) | VS 2015 |
| &nbsp;&nbsp;[N3891 shared_mutex(시간 제한)의 이름을 shared_timed_mutex로 바꾸기](https://wg21.link/n3891) | VS 2015 |
| &nbsp;&nbsp;[N3346 최소 컨테이너 요소 요구 사항](https://wg21.link/n3346) | VS 2013 |
| &nbsp;&nbsp;[N3421 투명 연산자 함수(less\<> 등)](https://wg21.link/n3421) | VS 2013 |
| &nbsp;&nbsp;[N3655 \<type_traits>에 대한 별칭 템플릿(decay_t 등)](https://wg21.link/n3655) | VS 2013 |
| &nbsp;&nbsp;[N3656 make_unique()](https://wg21.link/n3656) | VS 2013 |

함께 나열된 문서 그룹은 하나 이상의 승인된 향상 또는 확장과 함께 표준 기능을 나타냅니다. 이러한 기능은 함께 구현됩니다.

### <a name="supported-values"></a>지원되는 값

__아니요__는 아직 구현되지 않았음을 의미합니다.\
__부분__은 부분적으로 구현되었음을 의미합니다. 자세한 내용은 참고 섹션을 참조하세요.\
__VS 2010__은 Visual Studio 2010에서 지원되는 기능을 나타냅니다.\
__VS 2013__은 Visual Studio 2013에서 지원되는 기능을 나타냅니다.\
__VS 2015__는 Visual Studio 2015(RTW)에서 지원되는 기능을 나타냅니다.\
__VS 2015.2__ 및 __VS 2015.3__은 각각 Visual Studio 2015 업데이트 2와 Visual Studio 2015 업데이트 3에서 지원되는 기능을 나타냅니다.\
__VS 2017 15.0__은 Visual Studio 2017 버전 15.0(RTW)에서 지원되는 기능을 나타냅니다.\
__VS 2017 15.3__은 Visual Studio 2017 버전 15.3에서 지원되는 기능을 나타냅니다.\
__VS 2017 15.5__는 Visual Studio 2017 버전 15.5에서 지원되는 기능을 나타냅니다.\
__VS 2017 15.7__은 Visual Studio 2017 버전 15.7에서 지원되는 기능을 나타냅니다.\
__VS 2019 16.0__은 Visual Studio 2019 버전 16.0(RTW)에서 지원되는 기능을 나타냅니다.\
__VS 2019 16.1__은 Visual Studio 2019 버전 16.1에서 지원되는 기능을 나타냅니다.\
__VS 2019 16.2__는 Visual Studio 2019 버전 16.2에서 지원되는 기능을 나타냅니다.\
__VS 2019 16.3__은 Visual Studio 2019 버전 16.3에서 지원되는 기능을 나타냅니다.\
__VS 2019 16.4__는 Visual Studio 2019 버전 16.4에서 지원되는 기능을 나타냅니다.\
__VS 2019 16.5__는 Visual Studio 2019 버전 16.5에서 지원되는 기능을 나타냅니다.

### <a name="notes"></a>참고

<a name="note_A"></a>__A__[/std:c++14](../build/reference/std-specify-language-standard-version.md) 모드에서는 동적 예외 사양이 구현되지 않은 상태로 남아 있으며 `throw()`는 여전히 `__declspec(nothrow)`의 동의어로 처리됩니다. C++17에서 동적 예외 사양은 P0003R5에 의해 대부분 제거되었으므로 1개의 vestige: `throw()`가 더 이상 사용되지 않으며 `noexcept`의 동의어로 작동해야 합니다. [/std:c++17](../build/reference/std-specify-language-standard-version.md) 모드에서 MSVC는 이제 `noexcept`, 즉 종료를 통한 적용과 동일한 동작을 `throw()`에 제공하여 표준을 준수합니다.

컴파일러 옵션 [/Zc:noexceptTypes](../build/reference/zc-noexcepttypes.md)는 `__declspec(nothrow)`의 이전 동작을 요청합니다. `throw()`는 C++20에서 제거될 가능성이 있습니다. 표준 및 구현에서 이러한 변경 사항에 대한 응답으로 코드를 마이그레이션하는 것을 돕기 위해 예외 사양 문제에 대한 새로운 컴파일러 경고가 [/std:c++17](../build/reference/std-specify-language-standard-version.md) 및 [/permissive-](../build/reference/permissive-standards-conformance.md) 아래에 추가되었습니다.

<a name="note_B"></a>__B__ Visual Studio 2017 버전 15.7의 [/permissive-](../build/reference/permissive-standards-conformance.md) 모드에서 지원됩니다. 자세한 내용은 [2단계 이름 조회 지원이 MSVC에 제공](https://devblogs.microsoft.com/cppblog/two-phase-name-lookup-support-comes-to-msvc/)을 참조하세요.

<a name="note_C"></a>__C__ Visual Studio 2017에서 C99 전처리기 규칙에 대한 컴파일러의 지원이 완전하지 않습니다. Microsoft에서는 전처리기를 점검하고 있으며 [/experimental:preprocessor](../build/reference/experimental-preprocessor.md) 컴파일러 스위치를 포함하여 Visual Studio 2017 버전 15.8에 해당 변경 내용 전달을 시작했습니다.

<a name="note_D"></a>__D__[/std:c++14](../build/reference/std-specify-language-standard-version.md) 아래에서 억제 가능한 경고 [C4984](../error-messages/compiler-warnings/compiler-warning-c4984.md)로 표시됩니다.

<a name="note_E"></a>__E__ 이것은 완전히 새로운 구현이기 때문에 이전의 `std::experimental` 버전과 호환되지 않으며, symlink 지원, 버그 수정 및 표준 필수 동작의 변경이 필요합니다. 지금은 \<filesystem>을 포함하면 새로운 `std::filesystem`과 이전 `std::experimental::filesystem`을 제공하고 \<experimental/filesystem>을 포함하면 오래된 실험 구현만을 제공합니다. 실험적 구현은 다음 ABI-breaking 라이브러리 릴리스에서 제거될 것입니다.

<a name="note_G"></a>__G__ 컴파일러 내장 함수에서 지원됩니다.

<a name="note_14"></a>__14__ 이러한 C++17/20 기능은 [/std:c++14](../build/reference/std-specify-language-standard-version.md)(기본값)를 지정한 경우에도 항상 활성화됩니다. 이는 **/std** 옵션을 도입하기 전에 기능이 구현되었거나 조건부 구현이 바람직하지 않게 복잡했기 때문입니다.

<a name="note_17"></a>__17__ 이러한 기능은 [/std:c++17](../build/reference/std-specify-language-standard-version.md)(또는 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) 컴파일러 옵션으로 활성화됩니다.

<a name="note_20"></a>__20__ 이 기능은 [/std:c++latest](../build/reference/std-specify-language-standard-version.md) 컴파일러 옵션을 통해 사용할 수 있습니다. C++20 구현이 완료되면 새 **/std:c++20** 컴파일러 옵션이 추가되어 이러한 기능도 사용할 수 있게 됩니다.

<a name="note_byte"></a>__byte__`std::byte`는 [/std:c++17](../build/reference/std-specify-language-standard-version.md)(또는 [/std:c++latest](../build/reference/std-specify-language-standard-version.md))로 활성화되지만, 경우에 따라 Windows SDK 헤더와 충돌할 수 있으므로 세분화된 옵트아웃 매크로가 있습니다. `_HAS_STD_BYTE`를 `0`으로 정의하여 비활성화할 수 있습니다.

<a name="note_C11"></a>__C11__ 유니버셜 CRT에서는 C99 `strftime()` E/O 대체 변환 지정자, C11 `fopen()` 단독 모드 및 C11 `aligned_alloc()`을 제외하고는 C++17에 필요한 C11 표준 라이브러리의 일부를 구현했습니다. 후자는 C11에서 `free()`의 Microsoft 구현과 호환되지 않는 방식, 즉 `free()`에서 고도로 정렬된 할당을 처리할 수 있어야 하는 `aligned_alloc()`을 지정했기 때문에 구현되지 않을 것입니다.

<a name="note_rem"></a>__rem__[/std:c++17](../build/reference/std-specify-language-standard-version.md)(또는 [/std:c++latest](../build/reference/std-specify-language-standard-version.md)) 컴파일러 옵션이 지정되면 기능이 제거됩니다. 이 기능을 다시 사용하도록 설정하면 `_HAS_AUTO_PTR_ETC`, `_HAS_FUNCTION_ALLOCATOR_SUPPORT`, `_HAS_OLD_IOSTREAMS_MEMBERS` 및 `_HAS_UNEXPECTED` 매크로를 사용하여 최신 언어 모드로 쉽게 전환할 수 있습니다.

<a name="note_charconv"></a>__charconv__`from_chars()` 및 `to_chars()`은(는) 정수에 사용할 수 있습니다. 부동 소수점 `from_chars()` 및 부동 소수점 `to_chars()`의 타임라인은 다음과 같습니다.
- VS 2017 15.7: 정수 `from_chars()` 및 `to_chars()`.
- VS 2017 15.8: 부동 소수점 `from_chars()`.
- VS 2017 15.9: 가장 짧은 10진수에 대한 부동 소수점 `to_chars()` 오버로드.
- VS 2019 16.0: 가장 짧은 16진수 및 16진수 전체 자릿수에 대한 부동 소수점 `to_chars()` 오버로드.
- VS 2019 16.2: 고정 전체 자릿수 및 지수 전체 자릿수에 대한 부동 소수점 `to_chars()` 오버로드.
- VS 2019 16.4: 일반 전체 자릿수에 대한 부동 소수점 `to_chars()` 오버로드.

<a name ="note_parallel"></a> __parallel__ C++17의 병렬 알고리즘 라이브러리가 완료되었습니다. 이는 모든 경우에서 모든 알고리즘이 병렬 처리된다는 것을 의미하지는 않습니다. 가장 중요한 알고리즘이 병렬 처리되었으며 알고리즘이 병렬 처리되지 않은 경우에도 실행 정책 시그니처가 제공됩니다. 구현의 중앙 내부 헤더인 yvals_core.h에는 다음과 같은 “병렬 알고리즘 참고 사항”이 포함되어 있습니다. C++를 사용하면 구현 시 직렬 알고니즘 호출로 병렬 알고리즘을 구현할 수 있습니다. 이 구현은 몇 가지 일반적인 알고리즘 호출을 병렬 처리하지만 전부는 아닙니다.

다음 알고리즘은 병렬 처리됩니다.

- `adjacent_difference`, `adjacent_find`, `all_of`, `any_of`, `count`, `count_if`, `equal`, `exclusive_scan`, `find`, `find_end`, `find_first_of`, `find_if`, `find_if_not`, `for_each`, `for_each_n`, `inclusive_scan`, `is_heap`, `is_heap_until`, `is_partitioned`, `is_sorted`, `is_sorted_until`, `mismatch`, `none_of`, `partition`, `reduce`, `remove`, `remove_if`, `replace`, `replace_if`, `search`, `search_n`, `set_difference`, `set_intersection`, `sort`, `stable_sort`, `transform`, `transform_exclusive_scan`, `transform_inclusive_scan`, `transform_reduce`

다음은 현재 병렬 처리되지 않습니다.

- 대상 하드웨어에 대한 병렬 처리 성능이 눈에 띄게 향상되지는 않습니다. 분기가 없는 요소를 단순히 복사하거나 치환하는 모든 알고리즘은 일반적으로 메모리 대역폭을 제한합니다.
  - `copy`, `copy_n`, `fill`, `fill_n`, `move`, `reverse`, `reverse_copy`, `rotate`, `rotate_copy`, `shift_left`, `shift_right`, `swap_ranges`
- 위의 범주에서 사용자 병렬 처리 요구 사항에 대한 혼란이 있을 수 있습니다.
  - `generate`, `generate_n`
- 실행할 수 없는 것으로 생각되는 유효한 병렬 처리:
  - `partial_sort`, `partial_sort_copy`
- 아직 평가되지 않았지만, 병렬 처리는 향후 릴리스에서 구현될 수 있으며 유익한 것으로 생각됩니다.
  - `copy_if`, `includes`, `inplace_merge`, `lexicographical_compare`, `max_element`, `merge`, `min_element`, `minmax_element`, `nth_element`, `partition_copy`, `remove_copy`, `remove_copy_if`, `replace_copy`, `replace_copy_if`, `set_symmetric_difference`, `set_union`, `stable_partition`, `unique`, `unique_copy`

## <a name="see-also"></a>참조

[C++ 언어 참조](../cpp/cpp-language-reference.md)\
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)\
[Visual Studio의 C++ 규칙 향상](cpp-conformance-improvements.md)\
[새로워진 Visual Studio의 Visual C++ 기능](what-s-new-for-visual-cpp-in-visual-studio.md)\
[Visual C++ 2003~2015 변경 내용](../porting/visual-cpp-change-history-2003-2015.md)\
[Visual C++ 2003~2015의 새로운 기능](../porting/visual-cpp-what-s-new-2003-through-2015.md)\
[C++ team blog](https://devblogs.microsoft.com/cppblog/)(C++ 팀 블로그)
