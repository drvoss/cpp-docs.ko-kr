---
title: '빠른 시작: C/C++용 코드 분석'
description: Visual Studio에서 C++ 코드에서 정적 분석을 실행하여 일반적인 코딩 문제 및 결함을 검색합니다.
ms.date: 04/08/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++ code analysis
- code analysis, C/C++
ms.openlocfilehash: 43866564915ac84d227ccbf347280efe59e33351
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370582"
---
# <a name="quickstart-code-analysis-for-cc"></a>빠른 시작: C/C++용 코드 분석

C 또는 C++ 코드에 대한 코드 분석을 정기적으로 실행하여 애플리케이션의 품질을 향상시킬 수 있습니다. 코드 분석을 통해 일반적인 문제와 좋은 프로그래밍 관행 위반을 찾을 수 있습니다. 또한 테스트를 통해 발견하기 어려운 결함을 발견합니다. 경고는 컴파일러 오류 및 경고와 다릅니다. 즉, 코드는 유효하지만 사용자 또는 코드를 사용하는 다른 사용자용으로 문제를 만들 수 있습니다.

## <a name="configure-rule-sets-for-a-project"></a>프로젝트에 대한 규칙 집합 구성

1. **솔루션 탐색기에서**프로젝트 이름에 대한 바로 가기 메뉴를 열고 **속성을**선택합니다.

1. 선택적으로 **구성** 및 **플랫폼** 목록에서 빌드 구성 및 대상 플랫폼을 선택합니다.

1. 선택한 구성을 사용하여 프로젝트를 빌드할 때마다 코드 분석을 실행하려면 **빌드시 코드 분석 활성화** 확인란을 선택합니다. 분석 **메뉴를** 연 다음 *ProjectName에서* 코드 분석 **실행을** 선택하거나 **파일에서 코드 분석 실행을**선택하여 코드 분석을 수동으로 실행할 수도 있습니다.

1. 사용할 [규칙 집합을](using-rule-sets-to-specify-the-cpp-rules-to-run.md) 선택하거나 사용자 [지정 규칙 집합을](using-rule-sets-to-specify-the-cpp-rules-to-run.md#to-create-a-rule-set-in-a-text-editor)만듭니다. LLVM/clang-cl을 사용하는 경우 [Visual Studio에서 Clang-Tidy 사용으로](../code-quality/clang-tidy.md) Clang-Tidy 분석 옵션을 구성합니다.

### <a name="standard-cc-rule-sets"></a>표준 C/C++ 규칙 세트

Visual Studio에는 네이티브 코드에 대한 다음과 같은 표준 규칙 집합이 포함되어 있습니다.

| 규칙 집합 | Description |
|--|--|
| **C++ 코어 체크 산술 규칙** | 이러한 규칙은 [C++ 코어 지침에서 산술 연산과](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es-expressions-and-statements)관련된 검사를 적용합니다. |
| **C++ 코어 체크 바운드 규칙** | 이러한 규칙은 [C++ 코어 지침의 경계 프로파일을 적용합니다.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#probounds-bounds-safety-profile) |
| **C++ 코어 체크 클래스 규칙** | 이러한 규칙은 [C++ 핵심 지침의 클래스와](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-classes-and-class-hierarchies)관련된 검사를 적용합니다. |
| **C++ 코어 확인 동시성 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 동시성](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cpcon-concurrency)관련 검사를 적용합니다. |
| **C ++ 코어 체크 콘스트 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 const 관련 검사를 적용합니다.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con-constants-and-immutability) |
| **C++ 코어 확인 선언 규칙** | 이러한 규칙은 [C++ 핵심 지침의 선언과](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i-interfaces)관련된 검사를 적용합니다. |
| **C++ 코어 체크 열거형 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 열거형 검사를 적용합니다.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-enum) |
| **C++ 코어 체크 실험 규칙** | 이러한 규칙은 몇 가지 실험적 검사를 수집합니다. 결국 이러한 검사는 다른 규칙 집합으로 이동하거나 완전히 제거될 것으로 예상됩니다. |
| **C++ 코어 체크 기능 규칙** | 이러한 규칙은 [C++ 핵심 지침의 함수와](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f-functions)관련된 검사를 적용합니다. |
| **C ++ 코어 체크 GSL 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 지침 지원 라이브러리와](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-gsl)관련된 검사를 적용합니다. |
| **C++ 코어 체크 수명 규칙** | 이러한 규칙은 [C++ 코어 지침의 수명 프로필을 적용합니다.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prolifetime-lifetime-safety-profile) |
| **C ++ 코어 검사 소유자 포인터 규칙** | 이러한 규칙은 [C++ 핵심&lt;지침에서 소유자 T와&gt; ](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)관련된 리소스 관리 검사를 적용합니다. |
| **C ++ 코어 체크 원시 포인터 규칙** | 이러한 규칙은 [C++ 핵심 지침의 원시 포인터와](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)관련된 리소스 관리 검사를 적용합니다. |
| **C++ 코어 검사 규칙** | 이러한 규칙은 [C++ 핵심 지침에서](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c-core-guidelines)검사의 하위 집합을 적용합니다. 이 규칙 집합을 사용하여 열거형 및 실험 규칙 집합을 제외한 모든 C++ 코어 검사 규칙을 포함합니다. |
| **C ++ 코어 확인 공유 포인터 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 공유 포인터 의미 체계가 있는 형식과](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)관련된 리소스 관리 검사를 적용합니다. |
| **C++ 코어 체크 STL 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 STL(표준 템플릿 라이브러리)과](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#S-stdlib)관련된 검사를 적용합니다. |
| **C++ 코어 체크 스타일 규칙** | 이러한 규칙은 [C++ 핵심 지침의 식 및 명령문 사용과](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es-expressions-and-statements)관련된 검사를 적용합니다. |
| **C++ 코어 검사 유형 규칙** | 이러한 규칙은 [C++ 핵심 지침의 형식 프로필을 적용합니다.](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#prosafety-type-safety-profile) |
| **C ++ 코어 확인 고유 포인터 규칙** | 이러한 규칙은 [C++ 핵심 지침에서 고유한 포인터 의미 체계가](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#r-resource-management)있는 형식과 관련된 리소스 관리 검사를 적용합니다. |
| **동시성 확인 규칙** | 이러한 규칙은 C++에서 Win32 동시성 패턴 검사 집합을 적용합니다. |
| **동시성 규칙** | 동시성 검사 규칙에 C++ 핵심 지침에서 **동시성**규칙을 추가합니다. |
| **마이크로 소프트 네이티브 최소 규칙** | 이러한 규칙은 잠재적인 보안 허점 및 응용 프로그램 충돌을 포함하여 네이티브 코드에서 가장 중요한 문제에 중점을 둡니다. 네이티브 프로젝트에 대해 만든 사용자 지정 규칙 집합에 이 규칙 집합을 포함하는 것이 좋습니다. |
| **Microsoft 네이티브 권장 규칙** | 이러한 규칙은 네이티브 코드에서 가장 중요하고 일반적인 문제에 중점을 둡니다. 이러한 문제에는 잠재적인 보안 허점 및 응용 프로그램 충돌이 포함됩니다. 네이티브 프로젝트에 대해 만든 사용자 지정 규칙 집합에 이 규칙 집합을 포함하는 것이 좋습니다. 이 규칙 집합은 Visual Studio 프로페셔널 버전 이상에서 작동하도록 설계되었습니다. 그것은 마이크로 소프트 **네이티브 최소**규칙의 모든 규칙을 포함한다. |

Visual Studio에는 관리 되는 코드에 대 한 이러한 표준 규칙 집합이 포함 됩니다.

| 규칙 집합 | Description |
|--|--|
| **마이크로소프트 기본 정확성 규칙** | 이러한 규칙은 프레임워크 API 를 사용할 때 의한 논리 오류 및 일반적인 실수에 중점을 둡니다. 최소 권장 규칙에 의해 보고된 경고 목록에서 확장하도록 이 규칙을 설정합니다. |
| **마이크로소프트 기본 디자인 지침 규칙** | 이러한 규칙은 코드를 쉽게 이해하고 사용할 수 있도록 모범 사례를 적용하는 데 중점을 둡니다. 프로젝트에 라이브러리 코드가 포함되어 있거나 쉽게 유지 관리할 수 있는 코드에 대한 모범 사례를 적용하려는 경우 이 규칙 집합을 포함합니다. |
| **마이크로소프트 확장 정확성 규칙** | 이러한 규칙은 보고된 논리 및 프레임워크 사용 오류를 최대화하기 위해 기본 정확성 규칙에 대해 확장합니다. COM interop 및 모바일 응용 프로그램과 같은 특정 시나리오에 중점을 둡니다. 이러한 시나리오 중 하나가 프로젝트에 적용되면 이 규칙 집합을 포함하거나 프로젝트에서 추가 문제를 찾는 것이 좋습니다. |
| **마이크로소프트 확장 디자인 지침 규칙** | 이러한 규칙은 보고된 유용성 및 유지 관리 문제를 최대화하기 위해 기본 설계 지침 규칙에 따라 확장됩니다. 명명 지침에 중점을 둡이 있습니다. 프로젝트에 라이브러리 코드가 포함되어 있거나 유지 관리 가능한 코드를 작성하기 위한 가장 높은 표준을 적용하려는 경우 이 규칙 집합을 포함하는 것이 좋습니다. |
| **마이크로소프트 세계화 규칙** | 이러한 규칙은 다른 언어, 로캘 및 문화에서 사용될 때 응용 프로그램의 데이터가 올바르게 표시되지 않도록 하는 문제에 중점을 둡니다. 응용 프로그램이 지역화 및/또는 전역화된 경우 이 규칙 집합을 포함합니다. |
| **마이크로 소프트 관리 최소 규칙** | 이러한 규칙은 코드 분석이 가장 정확한 코드에서 가장 중요한 문제에 중점을 둡니다.  이러한 규칙은 숫자가 작으며 제한된 Visual Studio 버전에서만 실행됩니다.  다른 비주얼 스튜디오 버전과 함께 최소권장규칙.ruleset을 사용합니다. |
| **마이크로소프트 관리 권장 규칙** | 이러한 규칙은 코드에서 가장 중요한 문제에 중점을 둡니다. 이러한 문제에는 잠재적인 보안 허점, 응용 프로그램 충돌 및 기타 중요한 논리 및 디자인 오류가 포함됩니다. 프로젝트에 대해 만든 사용자 지정 규칙 집합에 이 규칙 집합을 포함하는 것이 좋습니다. |
| **마이크로 소프트 혼합 (C ++ / CLR) 최소 규칙** | 이러한 규칙은 공통 언어 런타임을 지원하는 C++ 프로젝트에서 가장 중요한 문제에 중점을 둡니다. 이러한 문제에는 잠재적인 보안 허점, 응용 프로그램 충돌 및 기타 중요한 논리 및 디자인 오류가 포함됩니다. 공통 언어 런타임을 지원하는 C++ 프로젝트에 대해 만든 사용자 지정 규칙 집합에 이 규칙 집합을 포함하는 것이 좋습니다. |
| **마이크로 소프트 혼합 (C ++ / CLR) 권장 규칙** | 이러한 규칙은 공통 언어 런타임을 지원하는 C++ 프로젝트에서 가장 일반적이고 중요한 문제에 중점을 둡니다. 이러한 문제에는 잠재적인 보안 허점, 응용 프로그램 충돌 및 기타 중요한 논리 및 디자인 오류가 포함됩니다. 이 규칙 집합은 Visual Studio 프로페셔널 버전 이상에서 사용하도록 설계되었습니다. |
| **마이크로소프트 보안 규칙** | 이 규칙 집합에는 모든 Microsoft 보안 규칙이 포함되어 있습니다. 보고되는 잠재적보안 문제의 수를 최대화하려면 이 규칙을 포함합니다. |

모든 규칙을 포함하려면 다음을 수행하십시오.

| 규칙 집합 | Description |
|--|--|
| **마이크로 소프트 모든 규칙** | 이 규칙 집합에는 모든 규칙이 포함됩니다. 이 규칙 집합을 실행하면 많은 수의 경고가 보고될 수 있습니다. 이 규칙 집합을 사용하여 코드의 모든 문제를 포괄적으로 파악할 수 있습니다. 프로젝트에 가장 적합한 규칙 집합을 결정하는 데 도움이 될 수 있습니다. |

## <a name="run-code-analysis"></a>코드 분석 실행

프로젝트 속성 대화 상자의 **코드 분석** 페이지에서 프로젝트를 빌드할 때마다 실행되도록 코드 분석을 구성할 수 있습니다. 수동으로 코드 분석을 실행할 수도 있습니다.

솔루션에 대한 코드 분석을 실행하려면

- **빌드** 메뉴에서 **솔루션에서 코드 분석 실행을**선택합니다.

프로젝트에 대한 코드 분석을 실행하려면

1. 솔루션 탐색기에서 프로젝트 이름을 선택합니다.

1. **빌드** 메뉴에서 *프로젝트 이름에*대한 코드 **분석 실행을** 선택합니다.

파일에서 코드 분석을 실행하려면 다음을 수행하십시오.

1. 솔루션 탐색기에서 파일 이름을 선택합니다.

1. **빌드** 메뉴에서 **파일에서 코드 분석 실행을** 선택하거나 **Ctrl+Shift+Alt+F7을**누릅니다.

   프로젝트 또는 솔루션이 컴파일되고 코드 분석이 실행됩니다. 결과가 오류 목록 창에 나타납니다.

## <a name="analyze-and-resolve-code-analysis-warnings"></a>코드 분석 경고를 분석하고 해결합니다.

오류 목록 창에는 발견된 코드 분석 경고가 나열됩니다. 결과가 테이블에 표시됩니다. 특정 경고에 대한 자세한 정보를 사용할 수 있는 경우 첫 번째 열에는 확장 컨트롤이 포함되어 있습니다. 문제에 대한 추가 정보를 보려면 디스플레이를 확장하려면 이 디스플레이를 선택합니다. 가능한 경우 코드 분석에서는 경고를 발생시킨 분석 논리와 줄 번호를 표시합니다.

문제에 대한 가능한 해결 방법을 포함하여 경고에 대한 자세한 정보를 보려면 코드 열에서 경고 ID를 선택하여 해당 온라인 도움말 문서를 표시합니다.

경고를 두 번 클릭하여 커서를 Visual Studio 코드 편집기에서 경고를 발생시킨 코드 줄로 이동합니다. 또는 선택한 경고에 Enter를 누릅니다.

문제를 파악한 후 코드에서 해결할 수 있습니다. 그런 다음 코드 분석을 다시 실행하여 경고가 오류 목록에 더 이상 나타나지 않도록 합니다.

## <a name="create-work-items-for-code-analysis-warnings"></a>코드 분석 경고용 작업 항목 만들기

작업 항목 추적 기능을 사용하여 Visual Studio에서 버그를 기록할 수 있습니다. 이 기능을 사용하려면 Azure DevOps 서버(이전 팀 기초 서버)의 인스턴스에 연결해야 합니다.

### <a name="to-create-a-work-item-for-one-or-more-cc-code-warnings"></a>하나 이상의 C/C++ 코드 경고에 대한 작업 항목을 만들려면

1. 오류 목록에서 경고를 확장하고 선택합니다.

1. 경고의 바로 가기 메뉴에서 **작업 항목 만들기를**선택한 다음 작업 항목 유형을 선택합니다.

1. Visual Studio에서 선택한 경고에 대한 단일 작업 항목을 만들고 IDE의 문서 창에 작업 항목을 표시합니다.

1. 추가 정보를 추가한 다음 **작업 항목 저장을 선택합니다.**

## <a name="search-and-filter-code-analysis-results"></a>코드 분석 결과 검색 및 필터

긴 경고 메시지 목록을 검색하고 다중 프로젝트 솔루션에서 경고를 필터링할 수 있습니다.

- **제목 또는 경고 ID로 경고를 필터링하려면**: 검색 오류 목록 상자에 키워드를 입력합니다.

- **심각도별 경고를 필터링하려면**: 기본적으로 코드 분석 메시지에 **경고의**심각도가 할당됩니다. 사용자 지정 규칙 집합에서 하나 이상의 메시지의 심각도를 **오류로** 지정할 수 있습니다. **오류 목록의** **심각도** 열에서 드롭다운 화살표를 선택한 다음 필터 아이콘을 선택합니다. **경고** 또는 **오류를** 선택하여 각 심각도가 할당된 메시지만 표시합니다. 모든 메시지를 표시하려면 **모두 선택을** 선택합니다.

## <a name="see-also"></a>참고 항목

- [C/C++용 코드 분석](../code-quality/code-analysis-for-c-cpp-overview.md)
