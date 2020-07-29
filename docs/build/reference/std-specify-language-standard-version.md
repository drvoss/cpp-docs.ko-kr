---
title: /std(언어 표준 버전 지정)
ms.date: 06/04/2020
f1_keywords:
- /std
- -std
- VC.Project.VCCLCompilerTool.CppLanguageStandard
ms.assetid: 0acb74ba-1aa8-4c05-b96c-682988dc19bd
ms.openlocfilehash: eef44858064b89d4a836c80a48552599bceec242
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223826"
---
# <a name="std-specify-language-standard-version"></a>`/std`(언어 표준 버전 지정)

지정된 C++ 언어 표준 버전에서 지원되는 C++ 언어 기능을 사용합니다.

## <a name="syntax"></a>구문

> **`/std:c++14`**\
> **`/std:c++17`**\
> **`/std:c++latest`**]

## <a name="remarks"></a>설명

**`/std`** 이 옵션은 Visual Studio 2017 이상에서 사용할 수 있습니다. 코드를 컴파일하는 동안 사용 하도록 설정 된 버전 관련 ISO c + + 프로그래밍 언어 표준 기능을 제어 하는 데 사용 됩니다. 이 옵션을 사용 하면 특정 버전의 언어 표준에 맞는 기존 코드를 중단할 수 있는 특정 언어 및 라이브러리 기능에 대 한 지원을 사용 하지 않도록 설정할 수 있습니다. 기본적으로 **`/std:c++14`** 는를 지정 합니다 .이를 통해 c + + 언어 표준의 이후 버전에서 제공 되는 언어 및 표준 라이브러리 기능을 사용할 수 없습니다. **`/std:c++17`** 를 사용 하 여 c + + 17 표준 특정 기능 및 동작을 사용 하도록 설정 합니다. 다음 초안 표준에 대해 제안 된 현재 구현 된 컴파일러 및 표준 라이브러리 기능을 명시적으로 사용 하도록 설정 하려면를 사용 **`/std:c++latest`** 합니다. 모든 c + + 20 기능에 **`/std:c++latest`** 는가 필요 합니다. 구현이 완료 되 면 새 **`/std:c++20`** 옵션을 사용할 수 있게 됩니다.

기본 **`/std:c++14`** 옵션을 사용 하면 MSVC 컴파일러에서 구현 하는 c + + 14 기능 집합을 사용할 수 있습니다. 이 옵션은 최신 버전의 언어 표준에서 변경 되거나 새로 추가 된 기능에 대 한 컴파일러 및 표준 라이브러리 지원을 사용 하지 않도록 설정 합니다. 이전 버전의 MSVC 컴파일러에서 이미 구현 된 일부 c + + 17 기능을 사용 하지 않도록 설정 하지 않습니다. Visual Studio 2015 업데이트 2에서 사용 가능한 기능에 대 한 종속성을 이미 가져온 사용자에 대 한 주요 변경 내용을 방지 하기 위해 옵션을 지정 하면 이러한 기능이 활성화 된 상태로 유지 됩니다 **`/std:c++14`** .

- [중괄호로 묶인에 대 한 규칙 `auto` -초기화 목록](https://wg21.link/n3922)

- [`typename`템플릿 템플릿-매개 변수](https://wg21.link/n4051)

- [삼중자 제거](https://wg21.link/n4086)

- [네임스페이스 및 열거자에 대한 특성](https://wg21.link/n4266)

- [u8 문자 리터럴](https://wg21.link/n4267)

을 지정할 때 사용할 수 있는 c + + 14 및 c + + 17 기능 목록입니다 **`/std:c++14`** . 자세한 내용은 [Microsoft c + + 언어 규칙 규칙 표](../../overview/visual-cpp-language-conformance.md)를 참조 하세요.

**`/std:c++17`** 옵션을 사용 하면 MSVC 컴파일러에서 구현 된 c + + 17 기능의 전체 집합을 사용할 수 있습니다. 이 옵션을 사용 하면 c + + 17 이후에 새로 제공 되거나 변경 된 기능에 대 한 컴파일러 및 표준 라이브러리 지원을 사용할 수 없습니다. 여기에는 c + + 표준의 작업 초안 및 오류 업데이트 버전에서 C + + 17 이후 변경 내용이 포함 됩니다.

**`/std:c++latest`** 옵션은 컴파일러 및 라이브러리에서 현재 구현 된 C + + + 17 언어 및 라이브러리 기능을 사용 하도록 설정 합니다. 이러한 기능에는 c + + 20 작업 초안의 변경 내용, c + + 17에 포함 되지 않은 결함 업데이트 및 초안 표준에 대 한 실험적 제안이 포함 될 수 있습니다. 지원되는 언어 및 라이브러리 기능 목록은 [Visual C++의 새로운 기능](../../overview/what-s-new-for-visual-cpp-in-visual-studio.md)을 참조하세요. **`/std:c++latest`** 옵션은 스위치에서 보호 하는 기능을 사용 하도록 설정 하지 **`/experimental`** 않지만 사용 하도록 설정 하는 데 필요할 수 있습니다.

> [!IMPORTANT]
> 에서 사용 하도록 설정 된 컴파일러 및 라이브러리 기능은 **`/std:c++latest`** 이후 c + + 표준에 나타날 수 있는 기능과 승인 되는 c + + 20 기능을 나타냅니다. 승인되지 않은 기능은 예고 없이 갑자기 변경되거나 제거될 수 있고, 있는 그대로 제공됩니다.

**`/std`** [ \_ MSVC \_ LANG](../../preprocessor/predefined-macros.md) 전처리기 매크로를 사용 하 여 c + + 컴파일 중에 적용 되는 옵션을 검색할 수 있습니다. 자세한 내용은 [전처리기 매크로](../../preprocessor/predefined-macros.md)를 참조하세요.

**`/std:c++14`** 및 **`/std:c++latest`** 옵션은 Visual Studio 2015 업데이트 3부터 사용할 수 있습니다. **`/std:c++17`** 이 옵션은 Visual Studio 2017 버전 15.3부터 사용할 수 있습니다. 위에서 설명한 것 처럼 일부 c + + 17 표준 동작은 옵션으로 사용 하도록 설정 **`/std:c++14`** 되지만 다른 모든 c + + 17 기능은에서 사용 하도록 설정 됩니다 **`/std:c++17`** . C + + 20 기능은 **`/std:c++latest`** 구현이 완료 될 때까지에서 사용 하도록 설정 됩니다.

> [!NOTE]
> MSVC 컴파일러 버전 또는 업데이트 수준에 따라, 옵션을 지정할 때 c + + 17 기능이 완전히 구현 되거나 완전히 일치 하지 않을 수 있습니다 **`/std:c++17`** . 릴리스 버전에서 Visual C++의 c + + 언어 규칙에 대 한 개요는 [Microsoft c + + 언어 규칙 표](../../overview/visual-cpp-language-conformance.md)를 참조 하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**, **C/C++**, **언어**를 차례로 선택합니다.

1. **C++ 언어 표준**의 드롭다운 컨트롤에서 지원할 언어 표준을 선택한 다음, **확인** 또는 **적용**을 선택하여 변경 내용을 저장합니다.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
