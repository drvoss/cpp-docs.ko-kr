---
title: EDITBIN 옵션
description: Microsoft EDITBIN 유틸리티 명령줄 옵션에 대 한 참조 가이드입니다.
ms.date: 02/09/2020
helpviewer_keywords:
- EDITBIN program, options
ms.assetid: 2da9f88e-cbab-4d64-bb66-ef700535230f
ms.openlocfilehash: 9fd4170e5ee020780963d83936f1a9fd08d2be11
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439967"
---
# <a name="editbin-options"></a>EDITBIN 옵션

EDITBIN을 사용 하 여 개체 파일, 실행 파일 및 Dll (동적 연결 라이브러리)을 수정할 수 있습니다. 옵션에 따라 EDITBIN이 수행하는 변경 사항이 지정됩니다.

옵션은 대시 (`-`) 또는 슬래시 (`/`), 옵션 이름을 차례로 나타내는 옵션 지정자로 구성 됩니다. 옵션 이름은 약식 일 수 없습니다. 일부 옵션은 콜론 (`:`) 뒤에 지정 되는 인수를 사용 합니다. 옵션 사양에는 공백이나 탭을 사용할 수 없습니다. 한 개 이상의 공백 또는 탭을 사용하여 명령줄에서 옵션 사양을 구분합니다. 옵션 이름과 해당 키워드 인수나 파일 이름 인수는 대/소문자를 구분 하지 않습니다. 예를 들어 `-bind`와 `/BIND`는 동일한 것을 의미 합니다.

EDITBIN에는 다음과 같은 옵션이 있습니다.

|옵션|목적|
|------------|-------------|
|[/ALLOWBIND](allowbind.md)|DLL을 바인딩할 수 있는지 여부를 지정합니다.|
|[/ALLOWISOLATION](allowisolation.md)|DLL 또는 실행 파일 매니페스트 조회 동작을 지정합니다.|
|[/APPCONTAINER](appcontainer.md)|앱을 AppContainer 내에서 실행 해야 하는지 여부를 지정 합니다 (예: UWP 앱).|
|[/BIND](bind.md)|로드 시간을 줄이기 위해 지정된 개체에서 진입점에 대한 주소를 설정합니다.|
|[/DYNAMICBASE](dynamicbase.md)|로드 시 ASLR(주소 공간 레이아웃 불규칙화)을 사용해서 DLL 또는 실행 가능 이미지를 무작위로 다시 지정할지 여부를 지정합니다.|
|[/ERRORREPORT](errorreport-editbin-exe.md)| 사용되지 않습니다. 오류 보고는 [WER (Windows 오류 보고)](/windows/win32/wer/windows-error-reporting) 설정에 의해 제어 됩니다. |
|[/HEAP](heap.md)|실행 가능한 이미지 힙의 크기 (바이트)를 설정 합니다.|
|[/HIGHENTROPYVA](highentropyva.md)|DLL 또는 실행 가능한 이미지가 높은 엔트로피(64비트) ASLR(주소 공간 레이아웃 불규칙화)을 지원하는지 여부를 지정합니다.|
|[/INTEGRITYCHECK](integritycheck.md)|로드 시 디지털 서명을 확인할지 여부를 지정합니다.|
|[/LARGEADDRESSAWARE](largeaddressaware.md)|개체에서 2GB보다 큰 주소가 지원되는지 여부를 지정합니다.|
|[/NOLOGO](nologo-editbin.md)|EDITBIN 시작 배너를 표시하지 않습니다.|
|[/NXCOMPAT](nxcompat.md)|실행 가능한 이미지가 Windows 데이터 실행 방지와 호환되는지 여부를 지정합니다.|
|[/REBASE](rebase.md)|지정된 개체에 대한 기준 주소를 설정합니다.|
|[/RELEASE](release.md)|헤더에 체크섬을 설정합니다.|
|[/SECTION](section-editbin.md)|섹션의 특성을 재정의합니다.|
|[/STACK](stack.md)|실행 가능한 이미지의 스택 크기 (바이트)를 설정 합니다.|
|[/SUBSYSTEM](subsystem.md)|실행 환경을 지정합니다.|
|[/SWAPRUN](swaprun.md)|실행 가능 이미지를 스왑 파일에 복사한 다음 해당 이미지에서 실행 하도록 지정 합니다.|
|[/TSAWARE](tsaware.md)|다중 사용자 환경에서 실행할 수 있도록 응용 프로그램이 설계되도록 지정합니다.|
|[/VERSION](version.md)|헤더에서 버전 번호를 설정합니다.|

## <a name="see-also"></a>참고 항목

[추가 MSVC 빌드 도구](c-cpp-build-tools.md)\
[EDITBIN 참조](editbin-reference.md)
