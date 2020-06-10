---
title: /Qpar-report(자동 병렬화 도우미 보고 수준)
ms.date: 11/04/2016
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
ms.openlocfilehash: 25732900fa201258331dcb8eee96af9ba97a6def
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319956"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report(자동 병렬화 도우미 보고 수준)

컴파일러의 [자동 병렬화](../../parallel/auto-parallelization-and-auto-vectorization.md) 보고 기능을 활성화하고 컴파일하는 동안 출력에 대한 정보 메시지의 수준을 지정합니다.

## <a name="syntax"></a>구문

```
/Qpar-report:{1}{2}
```

## <a name="remarks"></a>설명

**/Qpar-report:1**<br/>
병렬화되는 루프에 대해 정보 메시지를 출력합니다.

**/Qpar-report:2**<br/>
병렬화되는 루프와 병렬화되지 않는 루프 둘 다에 대한 정보 메시지와 이유 코드를 출력합니다.

메시지는 stdout으로 출력됩니다. 정보 메시지가 보고되지 않는다면 코드에 루프가 없거나 병렬화되지 않은 루프를 보고하도록 보고 수준을 설정하지 않은 것입니다. 원인 코드 및 메시지에 대한 자세한 내용은 [벡터화 도우미 및 병렬화 도우미 메시지](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)를 참조합니다.

### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Visual Studio에서 /Qpar-report 컴파일러 옵션을 설정하려면

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.

1. **속성 페이지** 대화 상자의 **C/C++**에서 **명령줄**을 선택합니다.

1. **추가 옵션** 상자에 `/Qpar-report:1` 또는 `/Qpar-report:2`를 입력합니다.

### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>프로그래밍 방식으로 /Qpar-report 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용합니다.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[네이티브 코드의 병렬 프로그래밍](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
