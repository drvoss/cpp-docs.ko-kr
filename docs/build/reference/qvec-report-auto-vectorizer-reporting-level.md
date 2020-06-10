---
title: /Qvec-report(자동 벡터화 도우미 보고 수준)
ms.date: 11/04/2016
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
ms.openlocfilehash: 655be3581eee4b23a8d0f2bcfaea7d07c8b1b07c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319254"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report(자동 벡터화 도우미 보고 수준)

컴파일러의 [자동 벡터화 도우미](../../parallel/auto-parallelization-and-auto-vectorization.md) 보고 기능을 사용하도록 설정하고 컴파일하는 동안 출력할 정보 메시지의 수준을 지정합니다.

## <a name="syntax"></a>구문

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>설명

**/Qvec-report:1**<br/>
벡터화된 for 루프의 정보 메시지를 출력합니다.

**/Qvec-report:2**<br/>
벡터화된 그리고 벡터화되지 않은 for 루프에 대한 이유 코드와 함께 정보 메시지를 출력합니다.

이유 코드 및 메시지에 대한 내용은 [벡터화 도우미 및 병렬화 도우미 메시지](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)를 참조합니다.

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Visual Studio에서 /Qvec-report 컴파일러 옵션을 설정 하려면

1. **솔루션 탐색기**에서 프로젝트의 바로가기 메뉴를 열고 **속성**을 선택합니다.

1. **속성 페이지** 대화 상자의 **C/C++**에서 **명령줄**을 선택합니다.

1. **추가 옵션** 상자에 `/Qvec-report:1` 또는 `/Qvec-report:2`를 입력합니다.

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>/Qvec-report 컴파일러 옵션을 프로그래밍 방식으로 설정 하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>에 있는 코드 예제를 사용합니다.

## <a name="see-also"></a>참고자료

[/Q 옵션(하위 수준 작업)](q-options-low-level-operations.md)<br/>
[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)<br/>
[네이티브 코드의 병렬 프로그래밍](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)
