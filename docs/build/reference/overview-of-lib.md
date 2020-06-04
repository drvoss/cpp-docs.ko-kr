---
title: LIB 개요
description: 라이브러리 도구인 lib.exe의 사용 및 옵션에 대 한 개요입니다.
ms.date: 02/09/2020
helpviewer_keywords:
- LIB [C++], modes
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
ms.openlocfilehash: 4ed725f383d956adf7abcf1c68002dee51703013
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439006"
---
# <a name="overview-of-lib"></a>LIB 개요

LIB (lib.exe)는 프로그램을 빌드할 때 [링크](linker-options.md) 와 함께 사용할 수 있는 표준 라이브러리, 가져오기 라이브러리 및 내보내기 파일을 만듭니다. LIB는 명령 프롬프트에서 실행 됩니다.

LIB는 다음 모드에서 사용할 수 있습니다.

- [COFF 라이브러리 빌드 또는 수정](managing-a-library.md)

- [파일에 대 한 멤버 개체 추출](extracting-a-library-member.md)

- [내보내기 파일 및 가져오기 라이브러리 만들기](working-with-import-libraries-and-export-files.md)

이러한 모드는 함께 사용할 수 없습니다. LIB는 한 번에 하나의 모드 에서만 사용할 수 있습니다.

## <a name="lib-options"></a>LIB 옵션

다음 표에서는 lib.exe의 옵션을 나열 하 고 자세한 정보에 대 한 링크를 제공 합니다.

|옵션|Description|
|-|-|
|**/DEF**|가져오기 라이브러리 및 내보내기 파일을 만듭니다.<br/><br/>자세한 내용은 [가져오기 라이브러리 및 내보내기 파일 작성](building-an-import-library-and-export-file.md)을 참조 하세요.|
|**/ERRORREPORT**| 사용되지 않습니다. 자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/EXPORT**|   프로그램에서 함수를 내보냅니다.<br/><br/>자세한 내용은 [가져오기 라이브러리 및 내보내기 파일 작성](building-an-import-library-and-export-file.md)을 참조 하세요.|
|**/EXTRACT**|   기존 라이브러리의 멤버 복사본을 포함 하는 개체 (.obj) 파일을 만듭니다.<br/><br/>자세한 내용은 [라이브러리 멤버 추출](extracting-a-library-member.md)을 참조 하세요.|
|**/INCLUDE**|   기호 테이블에 기호를 추가 합니다.<br/><br/>자세한 내용은 [가져오기 라이브러리 및 내보내기 파일 작성](building-an-import-library-and-export-file.md)을 참조 하세요.|
|**/LIBPATH**|   환경 라이브러리 경로를 재정의합니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/LINKREPRO**|   Lib.exe 충돌 또는 내부 오류를 재현 하는 데 필요한 아티팩트를 만듭니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/LINKREPROTARGET**|   지정 된 파일과 함께 lib.exe를 사용 하는 경우에만 **/LINKREPRO** 아티팩트를 생성 합니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/LIST**|   출력 라이브러리에 대 한 정보를 표준 출력에 표시 합니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/LTCG**|   링크 타임 코드 생성을 사용 하 여 라이브러리를 빌드 합니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/MACHINE**|   프로그램의 대상 플랫폼을 지정 합니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/NAME**|   가져오기 라이브러리를 빌드할 때 가져오기 라이브러리를 빌드할 DLL의 이름을 지정 합니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/NODEFAULTLIB**|   외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거 합니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/NOLOGO**|   LIB 저작권 메시지 및 버전 번호의 표시를 억제 하 고 명령 파일의 에코를 방지 합니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/OUT**|   기본 출력 파일 이름을 재정의 합니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/REMOVE**|   출력 라이브러리에서 개체를 생략 합니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/SUBSYSTEM**|   운영 체제에서 출력 라이브러리에 연결 하 여 만든 프로그램을 실행 하는 방법을 알려 줍니다.<br/><br/>자세한 내용은 [라이브러리 관리](managing-a-library.md)를 참조 하세요.|
|**/VERBOSE**|   추가 되는 .obj 파일의 이름을 포함 하 여 세션 진행률에 대 한 세부 정보를 표시 합니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|
|**/WX**|   경고를 오류로 처리 합니다.<br/><br/>자세한 내용은 [LIB 실행](running-lib.md)을 참조하세요.|

## <a name="see-also"></a>참고 항목

[LIB 참조](lib-reference.md)\
[LIB 입력 파일](lib-input-files.md)\
[LIB 출력 파일](lib-output-files.md)\
[기타 LIB 출력](other-lib-output.md)\
[라이브러리 구조](structure-of-a-library.md)
