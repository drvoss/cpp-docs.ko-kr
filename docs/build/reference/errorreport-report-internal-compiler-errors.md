---
title: /errorReport(내부 컴파일러 오류 보고)
description: Microsoft C/C++ 컴파일러/errorReport 명령줄 옵션에 대 한 참조입니다.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 9efe96ed2611795e1fef408ad07b49d65261c3b1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075082"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport(내부 컴파일러 오류 보고)

> [!NOTE]
> **/ErrorReport** 옵션은 사용 되지 않습니다. Windows Vista부터 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다.

## <a name="syntax"></a>구문

> **/errorReport:** \[**none** \| **프롬프트** \| **queue** \| **send** ]

## <a name="remarks"></a>주의

컴파일러에서 소스 코드 파일을 처리할 수 없는 경우 ICE (내부 컴파일러 오류)가 발생 합니다. ICE가 발생 하면 컴파일러는 출력 파일 또는 코드를 수정 하는 데 사용할 수 있는 유용한 진단을 생성 하지 않습니다.

**/ErrorReport** 인수는 Windows 오류 보고 서비스 설정에 의해 재정의 됩니다. Windows 오류 보고에서 보고를 사용 하도록 설정한 경우 컴파일러는 내부 오류에 대 한 보고서를 Microsoft에 자동으로 보냅니다. Windows 오류 보고에서 사용 하지 않도록 설정한 경우 보고서가 전송 되지 않습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **C/C++**  > **고급** 속성 페이지를 엽니다.

1. **오류 보고** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 컴파일러 옵션](compiler-options.md)\
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)
