---
title: Visual C++에서 MBCS 지원
ms.date: 11/04/2016
helpviewer_keywords:
- tools [C++], MBCS support
- Asian languages [C++]
- Code Editor [C++], MBCS support
- IME [C++]
- Chinese characters [C++]
- Input Method Editor [C++], MBCS
- resource editors [C++], MBCS support
- debugger [C++], MBCS support
- character sets [C++], multibyte
- Japanese characters [C++]
- multibyte characters [C++]
- Kanji character support [C++]
- NMAKE program, MBCS support
- double-byte character sets [C++]
- IME [C++], MBCS
- Input Method Editor [C++]
- MBCS [C++], enabling
ms.assetid: 6179f6b7-bc61-4a48-9267-fb7951223e38
ms.openlocfilehash: 404fcee5e48d8db28e56a005f24f8cac5892240e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375787"
---
# <a name="mbcs-support-in-visual-c"></a>Visual C++에서 MBCS 지원

MBCS 지원 Windows 버전에서 실행되는 경우 메모리 창을 제외한 Visual C++ 개발 시스템(통합 소스 코드 편집기, 디버거 및 명령줄 도구 포함)이 MBCS에서 활성화됩니다.

메모리 창은 데이터 바이트를 ANSI 또는 유니코드 문자로 해석할 수 있더라도 MBCS 문자로 해석하지 않습니다. ANSI 문자는 항상 크기가 1바이트이고 유니코드 문자의 크기는 2바이트입니다. MBCS를 사용하면 문자 크기가 1바이트 또는 2바이트가 될 수 있으며 해석은 사용 중인 코드 페이지에 따라 다릅니다. 따라서 메모리 창에 MBCS 문자를 안정적으로 표시하기가 어렵습니다. 메모리 창은 문자의 시작바이트를 알 수 없습니다. 개발자는 메모리 창에서 바이트 값을 보고 테이블의 값을 조회하여 문자 표현을 결정할 수 있습니다. 이는 개발자가 소스 코드를 기반으로 문자열의 시작 주소를 알고 있기 때문에 가능합니다.

Visual C++는 적절한 경우 이중 바이트 문자를 허용합니다. 여기에는 대화 상자의 경로 이름과 파일 이름과 Visual C++ 리소스 편집기의 텍스트 항목이 포함됩니다(예: 대화 상자 편집기의 정적 텍스트 및 아이콘 편집기의 정적 텍스트 항목). 또한 전처리기는 `#include` 명령문의 파일 이름과 pragmas `code_seg` 및 `data_seg` pragmas에 대한 인수와 같은 일부 이중 바이트 지시문을 인식합니다. 소스 코드 편집기에서는 C/C++ 언어 요소(예: 변수 이름)에는 없지만 주석 및 문자열 리터럴의 이중 바이트 문자가 허용됩니다.

## <a name="support-for-the-input-method-editor-ime"></a><a name="_core_support_for_the_input_method_editor_.28.ime.29"></a>입력 방법 편집기(IME) 지원

MBCS(예: 일본)를 사용하는 동아시아 시장을 위해 작성된 응용 프로그램은 일반적으로 단일 및 이중 바이트 문자를 모두 입력하기 위한 Windows IME를 지원합니다. Visual C++ 개발 환경에는 IME에 대한 전체 지원이 포함되어 있습니다.

일본어 키보드는 한자 문자를 직접 지원하지 않습니다. IME는 다른 일본어 알파벳(로마지, 카타카나 또는 히라가나)에 입력된 발음 문자열을 가능한 한자 표현으로 변환합니다. 모호성이 있는 경우 여러 대안 중에서 선택할 수 있습니다. 의도한 한자 문자를 선택하면 IME는 제어 `WM_CHAR` 응용 프로그램에 두 개의 메시지를 전달합니다.

ALT+\` 키 조합에 의해 활성화된 IME는 단추 집합(표시기) 및 변환 창으로 나타납니다. 응용 프로그램은 텍스트 삽입 지점에 창을 배치합니다. 응용 프로그램은 `WM_MOVE` 대상 `WM_SIZE` 창의 새 위치 또는 크기를 준수하도록 변환 창을 재배치하여 메시지를 처리해야 합니다.

응용 프로그램의 사용자가 한자 문자를 입력할 수 있도록 하려면 응용 프로그램에서 Windows IME 메시지를 처리해야 합니다. IME 프로그래밍에 대한 자세한 내용은 [입력 메서드 관리자를](/windows/win32/intl/input-method-manager)참조하십시오.

## <a name="visual-c-debugger"></a>비주얼 C++ 디버거

Visual C++ 디버거는 IME 메시지에 중단점을 설정하는 기능을 제공합니다. 또한 메모리 창에는 이중 바이트 문자가 표시될 수 있습니다.

## <a name="command-line-tools"></a>명령줄 도구

컴파일러, NMAKE 및 리소스 컴파일러(RC)를 포함한 Visual C++ 명령줄 도구입니다. EXE)는 MBCS가 활성화되어 있습니다. 리소스 컴파일러의 /c 옵션을 사용하여 응용 프로그램의 리소스를 컴파일할 때 기본 코드 페이지를 변경할 수 있습니다.

소스 코드 컴파일 시간에서 기본 로캘을 변경하려면 [setlocale를 #pragma](../preprocessor/setlocale.md)사용합니다.

## <a name="graphical-tools"></a>그래픽 도구

Spy++ 및 리소스 편집 도구와 같은 Visual C++ Windows 기반 도구는 IME 문자열을 완벽하게 지원합니다.

## <a name="see-also"></a>참고 항목

[멀티바이트 캐릭터 세트 지원(MBCS)](../text/support-for-multibyte-character-sets-mbcss.md)<br/>
[MBCS 프로그래밍 팁](../text/mbcs-programming-tips.md)
