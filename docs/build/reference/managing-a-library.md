---
title: 라이브러리 관리
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
ms.openlocfilehash: de55059834a0887d487b7be38377af9984512b75
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336402"
---
# <a name="managing-a-library"></a>라이브러리 관리

LIB의 기본 모드는 COFF 개체 라이브러리를 빌드하거나 수정하는 것입니다. LIB는 /EXTRACT(개체를 파일에 복사) 또는 /DEF(가져오기 라이브러리 작성)를 지정하지 않을 때 이 모드에서 실행됩니다.

개체 및/또는 라이브러리에서 라이브러리를 빌드하려면 다음 구문을 사용합니다.

```
LIB [options...] files...
```

이 명령은 하나 이상의 입력 *파일에서*라이브러리를 만듭니다. *파일은* COFF 개체 파일, 32비트 OMF 개체 파일 또는 기존 COFF 라이브러리일 수 있습니다. LIB는 지정된 파일에 있는 모든 개체를 포함하는 하나의 라이브러리를 만듭니다. 입력 파일이 32비트 OMF 개체 파일인 경우 LIB는 라이브러리를 빌드하기 전에 이를 COFF로 변환합니다. LIB는 LIB의 16비트 버전에서 만든 라이브러리에 있는 32비트 OMF 개체를 허용할 수 없습니다. 먼저 16비트 LIB를 사용하여 개체를 추출해야 합니다. 그런 다음 추출된 개체 파일을 32비트 LIB에 대한 입력으로 사용할 수 있습니다.

기본적으로 LIB는 첫 번째 개체 또는 라이브러리 파일의 기본 이름과 확장명 .lib를 사용하여 출력 파일의 이름을 지정합니다. 출력 파일은 현재 디렉터리에 배치됩니다. 파일이름이 이미 같은 경우 출력 파일이 기존 파일을 대체합니다. 기존 라이브러리를 유지하려면 /OUT 옵션을 사용하여 출력 파일의 이름을 지정합니다.

라이브러리를 빌드하고 수정하는 데 다음 옵션이 적용됩니다.

**/LIBPATH:** *디르*<br/>
환경 라이브러리 경로를 재정의합니다. 자세한 내용은 LINK [/LIBPATH](libpath-additional-libpath.md) 옵션에 대한 설명을 참조하십시오.

**/list**<br/>
출력 라이브러리에 대한 정보를 표준 출력으로 표시합니다. 출력을 파일로 리디렉션할 수 있습니다. /LIST를 사용하여 수정하지 않고 기존 라이브러리의 내용을 확인할 수 있습니다.

**/NAME:** *파일 이름*<br/>
가져오기 라이브러리를 작성할 때 가져오기 라이브러리가 빌드되는 DLL의 이름을 지정합니다.

**/NODEFAULTLIB**<br/>
외부 참조를 확인할 때 검색하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거합니다. 자세한 내용은 [/NODEFAULTLIB를](nodefaultlib-ignore-libraries.md) 참조하십시오.

**/OUT:** *파일 이름*<br/>
기본 출력 파일 이름을 재정의합니다. 기본적으로 출력 라이브러리는 명령줄에 첫 번째 라이브러리 또는 개체 파일의 기본 이름과 확장 .lib와 함께 현재 디렉터리에서 만들어집니다.

**/REMOVE:** *오브젝트*<br/>
출력 라이브러리에서 지정된 *개체를* 생략합니다. LIB는 모든 개체(개체 파일 또는 라이브러리)를 결합한 다음 /REMOVE로 지정된 개체를 삭제하여 출력 라이브러리를 만듭니다.

**/subsystem:****{콘솔** **&#124;** **&#124;** EFI_APPLICATION EFI_BOOT_SERVICE_DRIVER &#124; EFI_BOOT_SERVICE_DRIVER EFI_BOOT_SERVICE_DRIVER EFI_BOOT_SERVICE_DRIVER **EFI_ROM EFI_BOOT_SERVICE_DRIVER** &#124; **EFI_RUNTIME_DRIVER &#124;** **네이티브** &#124; **POSIX** &#124; &#124; **WINDOWSCE** }[,#.##]] &#124; 네이티브 &#124; **WINDOWSCE**<br/>
운영 체제에 출력 라이브러리에 연결하여 만든 프로그램을 실행하는 방법을 알려줍니다. 자세한 내용은 [LINK/SUBSYSTEM](subsystem-specify-subsystem.md) 옵션에 대한 설명을 참조하십시오.

명령줄에 지정된 LIB 옵션은 대/소문자를 구분하지 않습니다.

LIB를 사용하여 다음 라이브러리 관리 작업을 수행할 수 있습니다.

- 라이브러리에 객체를 추가하려면 기존 라이브러리의 파일 이름과 새 객체의 파일 이름을 지정합니다.

- 라이브러리를 결합하려면 라이브러리 파일 이름을 지정합니다. 개체를 추가하고 라이브러리를 단일 LIB 명령으로 결합할 수 있습니다.

- 라이브러리 멤버를 새 개체로 바꾸려면 바꿀 멤버 개체가 포함된 라이브러리와 새 개체(또는 라이브러리를 포함하는 라이브러리)의 파일 이름을 지정합니다. 이름이 같은 개체가 두 개 이상의 입력 파일에 있는 경우 LIB는 LIB 명령에 지정된 마지막 개체를 출력 라이브러리에 넣습니다. 라이브러리 멤버를 바꿀 때는 이전 개체가 포함된 라이브러리 옆에 새 개체 또는 라이브러리를 지정해야 합니다.

- 라이브러리에서 멤버를 삭제하려면 /REMOVE 옵션을 사용합니다. LIB는 명령줄 순서에 관계없이 모든 입력 개체를 결합한 후 /REMOVE의 모든 사양을 처리합니다.

> [!NOTE]
> 멤버를 삭제하고 동일한 단계에서 파일로 추출할 수 없습니다. 먼저 /EXTRACT를 사용하여 멤버 개체를 추출한 다음 /REMOVE를 사용하여 LIB를 다시 실행해야 합니다. 이 동작은 다른 Microsoft 제품에서 제공하는 16비트 LIB(OMF 라이브러리의 경우)와 다릅니다.

## <a name="see-also"></a>참고 항목

[LIB 참조](lib-reference.md)
