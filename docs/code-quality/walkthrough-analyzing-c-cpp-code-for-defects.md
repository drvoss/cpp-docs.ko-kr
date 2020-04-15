---
title: '연습: 결함에 대한 C/C++ 코드 분석'
description: Visual Studio에서 Microsoft C++에서 코드 분석을 사용하는 방법을 보여 줍니다.
ms.date: 04/14/2020
ms.topic: conceptual
helpviewer_keywords:
- C/C++, code analysis
- code analysis, walkthroughs
- code, analyzing C/C++
- code analysis tool, walkthroughs
ms.openlocfilehash: fe9b3775199b2a18cf940b99e87852350f1fbea9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370211"
---
# <a name="walkthrough-analyzing-cc-code-for-defects"></a>연습: 결함에 대한 C/C++ 코드 분석

이 연습에서는 잠재적인 코드 결함에 대한 C/C++ 코드를 분석하는 방법을 보여 줍니다. C/C++ 코드에 대한 코드 분석 도구를 사용합니다.

이 연습에서는 다음을 수행합니다.

- 네이티브 코드에서 코드 분석을 실행합니다.
- 코드 결함 경고를 분석합니다.
- 경고를 오류로 처리합니다.
- 소스 코드에 추가하여 코드 결함 분석을 개선합니다.

## <a name="prerequisites"></a>사전 요구 사항

- [CppDemo 샘플의](../code-quality/demo-sample.md)복사본입니다.
- C/C++에 대한 기본적인 이해.

## <a name="run-code-analysis-on-native-code"></a>네이티브 코드에서 코드 분석 실행

### <a name="to-run-code-defect-analysis-on-native-code"></a>네이티브 코드에서 코드 결함 분석을 실행하려면

::: moniker range=">=vs-2019"

1. 비주얼 스튜디오에서 CppDemo 솔루션을 엽니다.

     이제 CppDemo 솔루션에 **솔루션 탐색기가**채워집니다.

1. **빌드** 메뉴에서 **솔루션 재생성**을 선택합니다.

     솔루션은 오류 나 경고없이 빌드됩니다.

1. **솔루션 탐색기에서**CodeDefects 프로젝트를 선택합니다.

1. **프로젝트** 메뉴에서 **속성**을 선택합니다.

     **CodeDefects 속성 페이지** 대화 상자가 표시됩니다.

1. 코드 **분석** 속성 페이지를 선택합니다.

1. 빌드 **속성에서 코드 분석 사용** **(예)을 변경합니다.** **확인**을 선택하여 변경 내용을 저장합니다.

1. CodeDefects 프로젝트를 다시 빌드합니다.

     코드 분석 경고가 **오류 목록** 창에 표시됩니다.

::: moniker-end

::: moniker range="<=vs-2017"

1. 비주얼 스튜디오에서 CppDemo 솔루션을 엽니다.

     이제 CppDemo 솔루션에 **솔루션 탐색기가**채워집니다.

1. **빌드** 메뉴에서 **솔루션 재생성**을 선택합니다.

     솔루션은 오류 나 경고없이 빌드됩니다.

     > [!NOTE]
     > Visual Studio 2017에서는 IntelliSense `E1097 unknown attribute "no_init_all"` 엔진에 가짜 경고가 표시될 수 있습니다. 이 경고는 무시해도 됩니다.

1. **솔루션 탐색기에서**CodeDefects 프로젝트를 선택합니다.

1. **프로젝트** 메뉴에서 **속성**을 선택합니다.

     **CodeDefects 속성 페이지** 대화 상자가 표시됩니다.

1. 코드 **분석** 속성 페이지를 선택합니다.

1. **빌드에서 코드 분석 활성화 확인란을** 선택합니다. **확인**을 선택하여 변경 내용을 저장합니다.

1. CodeDefects 프로젝트를 다시 빌드합니다.

     코드 분석 경고가 **오류 목록** 창에 표시됩니다.

::: moniker-end

### <a name="to-analyze-code-defect-warnings"></a>코드 결함 경고를 분석하려면

1. **보기** 메뉴에서 **오류 목록을**선택합니다.

     이 메뉴 항목이 표시되지 않을 수 있습니다. Visual Studio에서 선택한 개발자 프로필에 따라 다릅니다. **보기** 메뉴에서 **다른 Windows를** 가리키고 오류 목록을 선택해야 할 수 **있습니다.**

1. 오류 **목록** 창에서 다음 경고를 두 번 클릭합니다.

     C6230: 부울 컨텍스트에서 HRESULT를 사용하여 시술적으로 다른 형식 간에 암시적 캐스팅.

     코드 편집기는 함수 `bool ProcessDomain()`내부에 경고를 일으킨 줄을 표시합니다. 이 경고는 `HRESULT` 부울 결과가 예상되는 'if' 문에서 a가 사용되고 있음을 나타냅니다. `S_OK` HRESULT가 함수에서 반환될 때 성공을 나타내지만 부울 값으로 변환될 때 `false`에 평가하기 때문에 일반적으로 실수입니다.

1. 반환 값이 성공을 `SUCCEEDED` 나타내는 경우 변환되는 `true` 매크로를 사용하여 이 경고를 수정합니다. `HRESULT` 코드는 다음 코드와 유사해야 합니다.

   ```cpp
   if (SUCCEEDED(ReadUserAccount()))
   ```

1. 오류 **목록에서**다음 경고를 두 번 클릭합니다.

     C6282: 잘못된 연산자: 부울 컨텍스트에서 상수 할당. 대신 '=='를 사용하는 것이 좋습니다.

1. 같음 테스트를 통해 이 경고를 수정합니다. 코드는 다음 코드와 유사해야 합니다.

   ```cpp
   if ((len == ACCOUNT_DOMAIN_LEN) || (g_userAccount[len] != L'\\'))
   ```

1. **오류 목록의** 나머지 C6001 경고를 `i` 초기화하여 `j` 0으로 수정합니다.

1. CodeDefects 프로젝트를 다시 빌드합니다.

     프로젝트는 경고나 오류 없이 빌드됩니다.

## <a name="correct-source-code-annotation-warnings"></a>올바른 소스 코드 부침 경고

### <a name="to-enable-the-source-code-annotation-warnings-in-annotationc"></a>annotation에서 소스 코드 부침 경고를 사용하려면

::: moniker range=">=vs-2019"

1. 솔루션 탐색기에서 주석 프로젝트를 선택합니다.

1. **프로젝트** 메뉴에서 **속성**을 선택합니다.

     **속성 페이지** 주석 대화 상자가 표시됩니다.

1. 코드 **분석** 속성 페이지를 선택합니다.

1. 빌드 **속성에서 코드 분석 사용** **(예)을 변경합니다.** **확인**을 선택하여 변경 내용을 저장합니다.

::: moniker-end

::: moniker range="<=vs-2017"

1. 솔루션 탐색기에서 주석 프로젝트를 선택합니다.

1. **프로젝트** 메뉴에서 **속성**을 선택합니다.

     **속성 페이지** 주석 대화 상자가 표시됩니다.

1. 코드 **분석** 속성 페이지를 선택합니다.

1. **빌드에서 코드 분석 활성화 확인란을** 선택합니다. **확인**을 선택하여 변경 내용을 저장합니다.

::: moniker-end

### <a name="to-correct-the-source-code-annotation-warnings-in-annotationc"></a>annotation에서 소스 코드 부침 경고를 수정하려면

1. 주석 프로젝트를 다시 작성합니다.

1. **빌드** 메뉴에서 **주석에 대한 코드 분석 실행을 선택합니다.**

1. 오류 **목록에서**다음 경고를 두 번 클릭합니다.

     C6011: NULL 포인터 'newNode'를 구분합니다.

     이 경고는 호출자의 반환 값 확인 실패를 나타냅니다. 이 경우 NULL 값을 `AllocateNode` 반환하는 호출이 있을 수 있습니다. `AllocateNode`에 대한 함수 선언에 대한 annotations.h 헤더 파일을 참조하십시오.

1. 커서는 경고가 발생한 annotations.cpp 파일의 위치에 있습니다.

1. 이 경고를 수정하려면 'if' 문을 사용하여 반환 값을 테스트합니다. 코드는 다음 코드와 유사해야 합니다.

   ```cpp
   LinkedList* newNode = AllocateNode();
   if (nullptr != newNode)
   {
       newNode->data = value;
       newNode->next = 0;
       node->next = newNode;
   }
   ```

1. 주석 프로젝트를 다시 작성합니다.

     프로젝트는 경고나 오류 없이 빌드됩니다.

## <a name="use-source-code-annotation-to-discover-more-issues"></a>소스 코드 추가를 사용하여 더 많은 문제를 발견합니다.

### <a name="to-use-source-code-annotation"></a>소스 코드 추가를 사용하려면

1. 공식 매개 변수에 추가하고 함수의 `AddTail` 반환 값을 사용하여 포인터 값이 null일 수 있음을 나타냅니다.

   ```cpp
   _Ret_maybenull_ LinkedList* AddTail(_Maybenull_ LinkedList* node, int value)
   ```

1. **빌드** 메뉴에서 **솔루션에서 코드 분석 실행**을 선택합니다.

1. 오류 **목록에서**다음 경고를 두 번 클릭합니다.

     C6011: NULL 포인터 '노드'를 구분해제합니다.

     이 경고는 함수에 전달된 노드가 null일 수 있음을 나타냅니다.

1. 이 경고를 수정하려면 함수 시작 시 'if' 문을 사용하여 전달된 값을 테스트합니다. 코드는 다음 코드와 유사해야 합니다.

   ```cpp
   if (nullptr == node)
   {
        return nullptr;
   }
   ```

1. **빌드** 메뉴에서 **솔루션에서 코드 분석 실행**을 선택합니다.

     이제 경고나 오류 없이 프로젝트가 빌드됩니다.

## <a name="see-also"></a>참고 항목

[연습: 코드 결함에 대한 관리 코드 분석](/visualstudio/code-quality/walkthrough-analyzing-managed-code-for-code-defects)\
[C/C++용 코드 분석](../code-quality/code-analysis-for-c-cpp-overview.md)
