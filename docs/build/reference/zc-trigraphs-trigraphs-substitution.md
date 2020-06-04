---
title: /Zc:trigraphs(삼중자 대체)
ms.date: 03/06/2018
f1_keywords:
- /Zc:trigraphs
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 0e4c98e09551d39e3ff7978767b21f1d2c5bb318
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79438656"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs(삼중자 대체)

**/Zc: 삼중** 이 지정 된 경우 컴파일러는 해당 문장 부호 문자를 사용 하 여 삼중 자 문자 시퀀스를 대체 합니다.

## <a name="syntax"></a>구문

> **/Zc: 삼중 자**[ **-** ]

## <a name="remarks"></a>설명

*삼중* 자는 두 개의 연속 된 물음표 ("??")와 고유한 세 번째 문자로 구성 됩니다. C 언어 표준은 일부 문장 부호 문자에 대 한 편리한 그래픽 표현을 포함 하지 않는 문자 집합을 사용 하는 소스 파일에 대해 삼중 자를 지원 합니다. 예를 들어 삼중 자를 사용 하는 경우 컴파일러는 "?? = "삼중 자 ' # ' 문자를 사용 합니다. C + + 14를 통해 삼중 자는 C에서와 같이 지원 됩니다. C + + 17 표준은 C++ 언어에서 삼중 자를 제거 합니다. 코드 C++ 에서 **/zc: 삼중** 컴파일러 옵션은 해당 문장 부호 문자를 사용 하 여 삼중 자 시퀀스를 대체 합니다. **/Zc: 삼중 자-삼중 자** 대체를 사용 하지 않습니다.

**/Zc: 삼중 자** 옵션은 기본적으로 해제 되어 있으며 [/permissive-](permissive-standards-conformance.md) 옵션이 지정 된 경우이 옵션은 영향을 받지 않습니다.

C/C++ 삼중 자 목록과 삼중 자를 사용 하는 방법을 보여 주는 예제는 [삼중 자](../../c-language/trigraphs.md)를 참조 하세요.

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **명령줄** 속성 페이지를 선택합니다.

1. **/Zc: 삼중 자** 또는 **/zc: 삼중 자를** 포함 하도록 **추가 옵션** 속성을 수정한 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참고 항목

[/Zc(규칙)](zc-conformance.md)<br/>
[삼중자](../../c-language/trigraphs.md)<br/>
