---
title: LINK 출력
ms.date: 11/04/2016
helpviewer_keywords:
- mapfiles [C++]
- ILK files
- output files [C++], linker
- files [C++], LINK
- .ilk files
- LINK tool [C++], output
- import libraries [C++], creating
- executable files [C++], as linker output
- mapfiles [C++], LINK output
- linker [C++], output files
- DLLs [C++], as linker output
- LINK tool [C++], mapfile
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
ms.openlocfilehash: 253f88ed50b9f064edf976277a4618e4f101ec7e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331786"
---
# <a name="link-output"></a>LINK 출력

링크 출력에는 .exe 파일, DLL, 맵파일 및 메시지가 포함됩니다.

## <a name="output-files"></a><a name="_core_output_files"></a>출력 파일

LINK의 기본 출력 파일은 .exe 파일입니다. [/DLL](dll-build-a-dll.md) 옵션을 지정하면 LINK는 .dll 파일을 빌드합니다. 출력 파일 [이름(/OUT)](out-output-file-name.md) 옵션을 사용 하 고 출력 파일 이름을 제어할 수 있습니다.

증분 모드에서 LINK는 프로그램의 이후 증분 빌드에 대한 상태 정보를 보유하는 .ilk 파일을 만듭니다. .ilk 파일에 대한 자세한 내용은 [.ilk 파일을](dot-ilk-files-as-linker-input.md)참조하십시오. 증분 연결에 대한 자세한 내용은 [증분 링크(/증분)](incremental-link-incrementally.md) 옵션을 참조하십시오.

LINK가 내보내기(일반적으로 DLL)를 포함하는 프로그램을 만들 때 빌드에서 .exp 파일이 사용되지 않는 한 .lib 파일도 빌드합니다. [/IMPLIB](implib-name-import-library.md) 옵션을 사용 하 고 가져오기 라이브러리 파일 이름을 제어할 수 있습니다.

[맵파일 생성(/MAP)](map-generate-mapfile.md) 생성 옵션이 지정되면 LINK는 맵 파일을 만듭니다.

[디버그 정보 생성(/DEBUG)](debug-generate-debug-info.md) 생성 옵션을 지정하면 LINK는 프로그램에 대한 디버깅 정보를 포함하도록 PDB를 만듭니다.

## <a name="other-output"></a><a name="_core_other_output"></a>기타 출력

다른 명령줄 입력 없이 입력하면 `link` LINK는 해당 옵션을 요약하는 사용 문을 표시합니다.

LINK는 시작 [배너(/NOLOGO) 표시 기 압제](nologo-suppress-startup-banner-linker.md) 옵션을 사용하지 않는 한 저작권 및 버전 메시지를 표시하고 명령 파일 입력을 에코합니다.

[진행률 메시지 인쇄(/자세한 내용)](verbose-print-progress-messages.md) 옵션을 사용하여 빌드에 대한 추가 세부 정보를 표시할 수 있습니다.

LINK는 LNK*nnn*형식으로 오류 및 경고 메시지를 발행합니다. 이 오류 접두사 및 숫자 범위는 LIB, DUMPBIN 및 EDITBIN에서도 사용됩니다.

## <a name="see-also"></a>참고 항목

[MSVC 링커 참조](linking.md)<br/>
[MSVC 링커 옵션](linker-options.md)
