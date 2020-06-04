---
title: 프로젝트 만들기(ATL 자습서, 1부)
ms.custom: get-started-article
ms.date: 08/19/2019
ms.assetid: f6b727d1-390a-4b27-b82f-daadcd9fc059
ms.openlocfilehash: 31ecee084f620256820a685df1f0e6891046fb8f
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075340"
---
# <a name="creating-the-project-atl-tutorial-part-1"></a>프로젝트 만들기(ATL 자습서, 1부)

이 자습서에서는 다각형을 표시 하는 ActiveX 개체를 만드는 특성을 사용 하지 않는 ATL 프로젝트를 단계별로 안내 합니다. 생성된 개체는 사용자가 다각형을 구성하는 변의 수를 바꾸고 화면을 새로 고치는 코드가 가능한 옵션을 포함합니다.

> [!NOTE]
> 이 자습서에서는 다각형 샘플과 동일한 소스 코드를 만듭니다. 소스 코드를 수동으로 입력 하지 않으려면 [Polygon sample abstract](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/Polygon)에서 다운로드할 수 있습니다. 자습서를 통해 작업 하거나 자신의 프로젝트에 오류가 있는지 확인하는데 다각형 소스 코드를 참조할 수 있습니다.
> 컴파일하려면 *.pch* (Visual Studio 2017 및 이전 버전에서*stdafx.h* )를 열고 다음을 바꿉니다.
>
> ```
> #ifndef WINVER
> #define WINVER 0x0400
> #endif
> ```
>
> 다음과 같이 바꿉니다.
>
> ```
> #ifndef WINVER
> #define WINVER 0x0500
> #define _WIN32_WINNT 0x0500
> #endif
> ```
>
> 컴파일러는 올바르게 종료 되지 `regsvr32` 계속 해 서 발생 하지만 컨트롤의 DLL을 빌드하고 사용할 수 있어야 합니다.

### <a name="to-create-the-initial-atl-project-using-the-atl-project-wizard"></a>ATL 프로젝트 마법사를 사용하여 초기 ATL 프로젝트를 만들려면

1. Visual Studio 2017 이전 버전: **파일** > **새** > **프로젝트**. **시각적 개체 C++**  탭을 열고 **MFC/ATL**을 선택 합니다. **ATL 프로젝트**를 선택 합니다.

   Visual Studio 2019: **파일** > **새** > **프로젝트**를 선택 하 고 검색 상자에 "Atl"을 입력 한 다음 **atl 프로젝트**를 선택 합니다.

1. 프로젝트 이름으로 *Polygon* 을 입력 합니다.

    소스 코드의 위치는 일반적으로 기본적으로 \Users\\\<username > \source\repos이 고 새 폴더는 자동으로 만들어집니다.

1. Visual Studio 2019에서 기본값을 그대로 적용 하 고 **확인**을 클릭 합니다.
   Visual Studio 2017에서 **확인** 을 클릭 하 여 **ATL 프로젝트** 마법사를 엽니다. **응용 프로그램 설정** 을 클릭 하 여 사용할 수 있는 옵션을 확인 합니다. 이 프로젝트는 컨트롤을 만들지만 컨트롤이 in-process 서버 여야 하므로 **응용 프로그램 유형을** DLL로 그대로 둡니다. **확인**을 클릭합니다.

Visual Studio에서 여러 파일을 생성 하 여 프로젝트를 만듭니다. **솔루션 탐색기** 에서 `Polygon` 개체를 확장 하 여 이러한 파일을 볼 수 있습니다. 파일은 다음과 같습니다.

::: moniker range="<=vs-2017"

|파일|설명|
|----------|-----------------|
|Polygon .cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`및 `DllUnregisterServer`의 구현을 포함 합니다. 프로젝트의 ATL 개체의 목록인 개체 맵의 포함 됩니다. 이 옵션은 처음에 비어 있습니다.|
|Polygon .def|이 모듈 정의 파일은 링커에게 DLL에서 필요로 하는 내보내기에 대한 정보를 제공합니다.|
|Polygon .idl|인터페이스 정의 언어 파일입니다. 개체에 특정 인터페이스를 설명합니다.|
|Polygon. rgs|이 레지스트리 스크립트를 사용하면 프로그램의 DLL 등록을 위한 정보가 있습니다.|
|Polygon .rc|버전 정보 및 프로젝트 이름이 문자열로 포함된 리소스 파일입니다.|
|Resource.h|리소스 파일용 헤더 파일.|
|Polygonps|이 모듈 정의 파일은 경계를 넘어 호출하는 프록시와 스텁 코드에서 필요한 내보내기 정보를 링커에 제공합니다.|
|stdafx.cpp|*Stdafx.h*를 `#include` 파일입니다.|
|stdafx.h|ATL 헤더 파일을 `#include` 하 고 미리 컴파일하는 파일입니다.|

::: moniker-end

::: moniker range=">=vs-2019"

|파일|설명|
|----------|-----------------|
|Polygon .cpp|`DllMain`, `DllCanUnloadNow`, `DllGetClassObject`, `DllRegisterServer`및 `DllUnregisterServer`의 구현을 포함 합니다. 프로젝트의 ATL 개체의 목록인 개체 맵의 포함 됩니다. 이 옵션은 처음에 비어 있습니다.|
|Polygon .def|이 모듈 정의 파일은 링커에게 DLL에서 필요로 하는 내보내기에 대한 정보를 제공합니다.|
|Polygon .idl|인터페이스 정의 언어 파일입니다. 개체에 특정 인터페이스를 설명합니다.|
|Polygon. rgs|이 레지스트리 스크립트를 사용하면 프로그램의 DLL 등록을 위한 정보가 있습니다.|
|Polygon .rc|버전 정보 및 프로젝트 이름이 문자열로 포함된 리소스 파일입니다.|
|Resource.h|리소스 파일용 헤더 파일.|
|Polygonps|이 모듈 정의 파일은 경계를 넘어 호출하는 프록시와 스텁 코드에서 필요한 내보내기 정보를 링커에 제공합니다.|
|.pch .cpp|Pch를 `#include` 하는 파일입니다 *.*|
|.pch. h|ATL 헤더 파일을 `#include` 하 고 미리 컴파일하는 파일입니다.|

::: moniker-end

1. **솔루션 탐색기**에서 `Polygon` 프로젝트를 마우스 오른쪽 단추로 클릭합니다.

1. 바로 가기 메뉴에서 **속성**을 클릭 합니다.

1. **링커**를 클릭 합니다. **UserRedirection** 옵션을 **예**로 변경 합니다.

1. **확인**을 클릭합니다.

다음 단계에서는 프로젝트에 컨트롤을 추가합니다.

[2 단계에서](../atl/adding-a-control-atl-tutorial-part-2.md)

## <a name="see-also"></a>참고 항목

[자습서](../atl/active-template-library-atl-tutorial.md)
