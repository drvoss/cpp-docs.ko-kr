---
title: /ERRORREPORT(내부 링커 오류 보고)
description: Microsoft NMAKE 명령줄 옵션에 대 한 참조 가이드입니다.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 5e919d4f7eb59524b9145c8e3e59613e60aef1d2
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257691"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT(내부 링커 오류 보고)

**/ERRORREPORT** 옵션은 사용 되지 않습니다. Windows Vista부터 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다.

## <a name="syntax"></a>구문

> **/ERRORREPORT:** \[ **none** \| **프롬프트** \| **queue** \| **send** ]

## <a name="remarks"></a>주의

**/ERRORREPORT** 인수는 Windows 오류 보고 서비스 설정에 의해 재정의 됩니다. Windows 오류 보고에서 보고를 사용 하도록 설정한 경우 링커에서는 내부 오류에 대 한 보고서를 Microsoft에 자동으로 보냅니다. Windows 오류 보고에서 사용 하지 않도록 설정한 경우 보고서가 전송 되지 않습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 [Visual Studio에서 컴파일러 및 빌드 속성 설정](../working-with-project-properties.md)을 참조합니다.

1. **구성 속성** > **링커** > **고급** 속성 페이지를 엽니다.

1. **오류 보고** 속성을 수정 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)\
[MSVC 링커 옵션](linker-options.md)
