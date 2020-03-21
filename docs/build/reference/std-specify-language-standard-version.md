---
title: /std(언어 표준 버전 지정)
ms.date: 05/16/2019
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: 52aa99cf5bdf7ddcf83a8423b946a03d2ca95d2d
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079261"
---
# <a name="std-specify-language-standard-version"></a>/std(언어 표준 버전 지정)

지정된 C++ 언어 표준 버전에서 지원되는 C++ 언어 기능을 사용합니다.

## <a name="syntax"></a>구문

> /std:\[c++14\|c++17\|c++latest]

## <a name="remarks"></a>주의

**/std** 옵션은 Visual Studio 2017 이상에서 사용할 수 있습니다. 이 옵션은 코드 컴파일 중에 사용하도록 설정된 버전 특정 ISO C++ 프로그래밍 언어를 제어하는 데 사용합니다. 이 옵션을 통해 특정 언어 표준 버전을 준수하는 기존 코드를 손상시킬 수 있는 특정 새 언어 및 라이브러리에 대한 기능을 사용하지 않도록 설정할 수 있습니다. 기본적으로 이후의 C++ 언어 표준에서 제공하는 언어 및 표준 라이브러리 기능을 사용하지 않게 설정하는 **/std:c++14**를 지정합니다. C++17 표준 특정 기능 및 동작을 사용하려면 **/std:c++17**을 사용합니다. 다음 초안 표준에 대해 현재 구현된 컴파일러와 제안된 표준 라이브러리 기능을 명시적으로 사용하려면 **/std:c++latest**를 사용합니다. 모든 c + + 20 기능에는 **/std: C + + 최신**이 필요 합니다. 구현이 완료 되 면 새 **/std: c + + 20** 옵션이 활성화 됩니다.

기본 **/std:c++14** 옵션은 MSVC 컴파일러에서 구현된 전체 C++14 기능 집합을 사용하도록 설정합니다. 이 옵션은 이후의 언어 표준 버전에서 변경되었거나 새로 도입된 기능에 대한 컴파일러와 표준 라이브러리 지원을 사용하지 않게 설정합니다. 단 이전 MSVC 컴파일러 릴리스에서 이미 구현된 C++17 컴파일러 기능은 예외입니다. Visual Studio 2015 업데이트 2에서 제공되는 기능에 대해 이미 종속성이 있는 사용자에게 중대한 변화가 발생하지 않도록, **/std: c + + 14** 옵션을 지정하면 이 기능을 그대로 사용합니다.

- [중괄호로 묶인 init 목록을 사용한 auto 규칙](https://wg21.link/n3922)

- [template-parameters 템플릿의 typename](https://wg21.link/n4051)

- [삼중자 제거](https://wg21.link/n4086)

- [네임스페이스 및 열거자에 대한 특성](https://wg21.link/n4266)

- [u8 문자 리터럴](https://wg21.link/n4267)

**/Std: c** + + 14가 지정 된 경우 사용할 수 있는 c + + 14 및 c + + 17 기능에 대 한 자세한 내용은 [Microsoft C++ 언어 규칙 표](../../overview/visual-cpp-language-conformance.md)를 참조 하세요.

**/std:c++17** 옵션은 MSVC 컴파일러에서 구현된 전체 C++17 기능 집합을 사용하도록 설정합니다. 이 옵션에서는 C++17 이후의 C++표준 규격 초안(Working Draft) 및 결함 업데이트의 전에서 변경되거나 새로운 기능에 대한 컴파일러 및 표준 라이브러리 지원을 사용하지 않습니다.

**/std:c++latest** 옵션은 현재 컴파일러와 라이브러리에 구현된 C++17 이후 언어 및 라이브러리 기능을 사용하도록 설정합니다. 여기에는 C++17에 포함되지 않은 C++20 초안의 기능과 C++ 표준의 결함 업데이트의 기능과, 초안 표준의 실험적 제안이 포함될 수 있습니다. 지원되는 언어 및 라이브러리 기능 목록은 [Visual C++의 새로운 기능](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md)을 참조하세요. **/std:c++latest** 옵션은 **/experimental** 스위치로 보호되는 기능은 사용하지 않으나 이를 사용하도록 설정해야 할 수 있습니다.

> [!IMPORTANT]
> **/std:c++latest**로 사용하는 컴파일러와 라이브러리 기능은 향후의 C++ 표준과, 승인된 C++20 기능에 있을 수 있는 기능을 나타냅니다. 승인되지 않은 기능은 예고 없이 갑자기 변경되거나 제거될 수 있고, 있는 그대로 제공됩니다.

C++ 컴파일 중에 적용되는 **/std** 옵션은 [\_MSVC\_LANG](../../preprocessor/predefined-macros.md) 전처리기 매크로를 사용하여 검색할 수 있습니다. 자세한 내용은 [전처리기 매크로](../../preprocessor/predefined-macros.md)를 참조하세요.

**/std:c++14** 및 **/std:c++latest** 옵션은 Visual Studio 2015 업데이트 3부터 사용할 수 있습니다. **/std:c++17** 옵션은 Visual Studio 2017 버전 15.3부터 사용할 수 있습니다. 앞서 설명한 것처럼 일부 C++17 표준 동작은 **/std:c++14** 옵션으로 사용하나 그 밖의 모든 C++17 기능은 **/std:c++17**로 사용합니다. C++ 20 기능은 구현이 완료될 때까지 **/std:latest**로 사용합니다.

> [!NOTE]
> MSVC 컴파일러 버전이나 업데이트 수준에 따라, **/std:c++17** 옵션을 지정했을 때 C++17 기능이 일부 구현되지 않거나 호환되지 않을 수 있습니다. 시각적 개체 C++ 릴리스 버전 C++ 의 언어 규칙 개요는 [Microsoft C++ 언어 규칙 표](../../overview/visual-cpp-language-conformance.md)를 참조 하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**, **C/C++** , **언어**를 차례로 선택합니다.

1. **C++ 언어 표준**의 드롭다운 컨트롤에서 지원할 언어 표준을 선택한 다음, **확인** 또는 **적용**을 선택하여 변경 내용을 저장합니다.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
