---
title: /Zc:trigraphs(삼중자 대체)
description: 삼중 자에 대 한 규칙 지원을 제어 하는 Microsoft c + + 컴파일러 옵션입니다.
ms.date: 07/25/2020
f1_keywords:
- /Zc:trigraphs
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: e24f3d2f0064c3acc04b4c3774f47f6e442d5ddd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211855"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>`/Zc:trigraphs`(삼중 자 대체)

**`/Zc:trigraphs`** 을 지정 하면 컴파일러는 해당 문장 부호 문자를 사용 하 여 삼중 자 문자 시퀀스를 대체 합니다.

## <a name="syntax"></a>구문

> **`/Zc:trigraphs`**[**`-`**]

## <a name="remarks"></a>설명

*삼중* 자는 두 개의 연속 된 물음표 ( **`??`** ) 다음에 고유한 세 번째 문자로 구성 됩니다. C 언어 표준은 일부 문장 부호 문자에 대 한 편리한 그래픽 표현을 포함 하지 않는 문자 집합을 사용 하는 소스 파일에 대해 삼중 자를 지원 합니다. 예를 들어, 삼중 자를 사용 하는 경우 컴파일러는 **`??=`** 문자를 사용 하 여 삼중 자를 대체 합니다 **`#`** . C + + 14를 통해 삼중 자는 C에서와 같이 지원 됩니다. C + + 17 표준은 c + + 언어에서 삼중 자를 제거 합니다. C + + 코드에서 **`/Zc:trigraphs`** 컴파일러 옵션을 사용 하면 해당 문장 부호 문자로 삼중 자 시퀀스를 대체할 수 있습니다. **`/Zc:trigraphs-`** 삼중 자 대체를 사용 하지 않습니다.

옵션은 **`/Zc:trigraphs`** 기본적으로 해제 되어 있으며 옵션이 지정 된 경우 옵션은 영향을 받지 않습니다 [`/permissive-`](permissive-standards-conformance.md) .

C/c + + 삼중 자 목록과 삼중 자를 사용 하는 방법을 보여 주는 예제는 [삼중 자](../../c-language/trigraphs.md)를 참조 하세요.

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 C++ 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성**  >  **C/c + +**  >  **명령줄** 속성 페이지를 선택 합니다.

1. 또는를 포함 하도록 **추가 옵션** 속성을 수정한 **`/Zc:trigraphs`** **`/Zc:trigraphs-`** 다음 **확인**을 선택 합니다.

## <a name="see-also"></a>참고 항목

[`/Zc`규칙](zc-conformance.md)<br/>
[삼중자](../../c-language/trigraphs.md)
