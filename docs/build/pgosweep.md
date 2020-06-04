---
title: pgosweep
ms.date: 03/14/2018
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
ms.openlocfilehash: 3ba31671fc3794e1cc959d86d914ba1eef2e01e4
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64341192"
---
# <a name="pgosweep"></a>pgosweep

프로필 기반 최적화에서 .pgc 파일에 실행 중인 프로그램의 모든 프로필 데이터를 쓰는 데 사용합니다.

## <a name="syntax"></a>구문

> **pgosweep** [*options*] *image* *pgcfile*

### <a name="parameters"></a>매개 변수

*options*<br/>
(선택 사항) *options*의 유효한 값은 다음과 같습니다.

- **/?** 또는 **/help** 도움말 메시지를 표시합니다.

- **/noreset** 런타임 데이터 구조에서 개수를 유지합니다.

*image*<br/>
[/GENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md), [/FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 또는 [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) 옵션을 사용하여 .exe 또는 .dll 파일의 전체 경로입니다.

*pgcfile*<br/>
이 명령이 데이터 개수를 기록하는 .pgc 파일입니다.

## <a name="remarks"></a>설명

**pgosweep** 명령은 [/GENPROFILE 또는 /FASTGENPROFILE](reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 옵션이나 사용되지 않는 [/LTCG:PGINSTRUMENT](reference/ltcg-link-time-code-generation.md) 옵션을 사용하여 빌드된 프로그램에서 작동합니다. 이 명령은 실행 중인 프로그램을 중단하고 새 .pgc 파일에 프로필 데이터를 기록합니다. 기본적으로 이 명령은 각 쓰기 작업 후에 개수를 다시 설정합니다. **/noreset** 옵션을 지정하면 이 명령은 값을 기록하지만 실행 중인 프로그램에서 값을 다시 설정하지 않습니다. 이 옵션을 사용하는 경우 나중에 프로필 데이터를 검색할 때 중복 데이터가 제공됩니다.

**pgosweep**의 다른 용도는 애플리케이션의 정상 작업에 관한 프로필 정보만 검색하는 것입니다. 예를 들어 애플리케이션을 시작하고 해당 파일을 삭제한 후 바로 **pgosweep**를 실행할 수 있습니다. 이렇게 하면 시작 비용과 관련된 프로필 데이터가 제거됩니다. 그런 다음 애플리케이션을 종료하기 전에 **pgosweep**를 실행할 수 있습니다. 이제 수집된 데이터에는 사용자가 프로그램을 조작할 수 있는 때부터의 프로필 정보만 포함됩니다.

*pgcfile* 매개 변수를 사용하여 .pgc 파일의 이름을 지정할 때 표준 형식인 *appname!n*.pgc를 사용할 수 있습니다. 이 형식을 사용하면 컴파일러는 **/LTCG /USEPROFILE** 또는 **/LTCG:PGO** 단계에서 이 데이터를 자동으로 찾습니다. 표준 형식을 사용하지 않는 경우에는 [pgomgr](pgomgr.md)을 사용하여 .pgc 파일을 병합해야 합니다.

> [!NOTE]
> 이 도구는 Visual Studio 개발자 명령 프롬프트에서만 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.

실행 파일 내에서 프로필 데이터를 캡처하는 방법에 대한 자세한 내용은 [PgoAutoSweep](pgoautosweep.md)를 참조하세요.

## <a name="example"></a>예제

이 예제 명령에서 **pgosweep**는 myapp.exe의 현재 프로필 정보를 myapp!1.pgc에 기록합니다.

`pgosweep myapp.exe myapp!1.pgc`

## <a name="see-also"></a>참조

[프로필 기반 최적화](profile-guided-optimizations.md)<br/>
[PgoAutoSweep](pgoautosweep.md)<br/>
