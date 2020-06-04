---
title: 컴파일러 및 링커에서의 유니코드 지원
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: 420b01263320cf86df3f99da4523cc2b8bb4d4b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168839"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>컴파일러 및 링커에서의 유니코드 지원

대부분의 C++ 시각적 빌드 도구는 유니코드 입력 및 출력을 지원 합니다.

## <a name="filenames"></a>파일 이름

명령줄 또는 컴파일러 지시문 (예: `#include`)에 지정 된 파일 이름은 유니코드 문자를 포함할 수 있습니다.

## <a name="source-code-files"></a>소스 코드 파일

유니코드 문자는 식별자, 매크로, 문자열 및 문자 리터럴과 주석에서 지원 됩니다.  유니버설 문자 이름도 지원 됩니다.

다음 인코딩의 소스 코드 파일에 유니코드를 입력할 수 있습니다.

- U t f-16 little endian 바이트 순서 표시 (BOM)를 포함 하거나 포함 하지 않습니다.

- U t f-16 big endian BOM 유무

- UTF-8 with BOM

## <a name="output"></a>출력

컴파일하는 동안 컴파일러는 u t f-16으로 진단 정보를 콘솔에 출력 합니다.  콘솔에 표시 될 수 있는 문자는 콘솔 창 속성에 따라 달라 집니다.  파일로 리디렉션되는 컴파일러 출력은 현재 ANSI 콘솔 코드 페이지에 있습니다.

## <a name="linker-response-files-and-def-files"></a>링커 지시 파일 및 DEF 파일

지시 파일 및 DEF 파일은 BOM이 있는 u t f-16 또는 ANSI 중 하나일 수 있습니다.

## <a name="asm-and-cod-dumps"></a>.asm 및 cod 덤프

.asm 및. cod 덤프는 기본적으로 MASM과의 호환성을 위해 ANSI에 있습니다. [/FAu](fa-fa-listing-file.md) 를 사용 하 여 u t f-8을 출력 합니다. **/FAs**를 지정 하면 소스 코드가 u t f-8이 고 **/FAsu**를 지정 하지 않은 경우와 같이 혼합 소스가 직접 인쇄 되 고 왜곡 될 수 있습니다.

## <a name="see-also"></a>참고 항목

[명령줄에서 MSVC 도구 집합 사용](../building-on-the-command-line.md)
