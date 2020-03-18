---
title: Windows XP용 프로그램 구성
description: Visual Studio에서 C++ Windows XP 도구 집합을 설치 하 고 사용 하는 방법입니다.
ms.date: 03/16/2020
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
ms.openlocfilehash: 92364d7fd25ac617baacc125b279fb0ee9c92f62
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440472"
---
# <a name="configuring-programs-for-windows-xp"></a>Windows XP용 프로그램 구성

Visual Studio는 여러 플랫폼 도구 집합을 지원 합니다. 즉, 기본 도구 집합에서 지원 하지 않는 운영 체제 및 런타임 라이브러리를 대상으로 지정할 수 있습니다. 예를 들어 플랫폼 도구 집합을 전환 하면 Visual Studio 2017 C++ 컴파일러를 사용 하 여 windows XP 및 windows Server 2003를 대상으로 하는 앱을 만들 수 있습니다. 또한 이전 플랫폼 도구 집합을 사용하여 이진 호환 레거시 코드를 유지하면서도 Visual Studio IDE의 최신 기능을 활용할 수 있습니다.

::: moniker range="vs-2019"

Visual Studio 2019에 제공 된 v142 도구 집합에는 Windows XP 용 코드를 만들기 위한 지원이 포함 되어 있지 않습니다. Visual Studio 2017 v141_xp 도구 집합을 사용 하 여 Windows XP 개발에 대 한 지원은 Visual Studio 설치 관리자 개별 구성 요소 옵션으로 제공 됩니다.

::: moniker-end

## <a name="install-the-windows-xp-platform-toolset"></a>Windows XP 플랫폼 도구 집합 설치

::: moniker range="<=vs-2017"

Windows XP 및 Windows Server 2003를 대상으로 하는 Visual Studio 2017 플랫폼 도구 집합 및 구성 요소를 가져오려면 Visual Studio 설치 관리자를 실행 합니다. 처음에 Visual Studio를 설치 하거나 기존 설치를 수정할 때 작업을 **사용 하 여 C++ 데스크톱 개발** 이 선택 되어 있는지 확인 합니다. 이 워크로드에 대한 선택적 구성 요소 목록에서 **C++용 Windows XP 지원**을 선택한 다음, **설치** 또는 **수정**을 선택합니다.

::: moniker-end

::: moniker range="vs-2019"

Windows XP 및 Windows Server 2003를 대상으로 하는 v141_xp 플랫폼 도구 집합 및 구성 요소를 가져오려면 Visual Studio 설치 관리자를 실행 합니다. 처음에 Visual Studio를 설치 하거나 기존 설치를 수정할 때 작업을 **사용 하 여 C++ 데스크톱 개발** 이 선택 되어 있는지 확인 합니다. **개별 구성 요소** 탭의 **컴파일러, 빌드 도구 및 런타임**에서  **C++ Windows XP Support for VS 2017 (v141) tools \[사용 되지 않음]** 을 선택한 다음 **설치** 또는 **수정**을 선택 합니다.

::: moniker-end

## <a name="windows-xp-targeting-experience"></a>Windows XP 대상 환경

Visual Studio에 포함 된 Windows XP 플랫폼 도구 집합은 Windows 7 SDK 버전 이지만 Visual Studio 2017 C++ 컴파일러를 사용 합니다. 또한 프로젝트 속성을 적합한 기본값(예: 하위 수준 대상 지정을 위한 호환 링커의 사양)으로 구성합니다. Windows xp 플랫폼 도구 집합을 사용 하 여 만든 Windows 데스크톱 앱만 Windows XP 및 Windows Server 2003에서 실행할 수 있습니다. 이러한 앱은 더 최신 Windows 운영 체제에서 실행할 수도 있습니다.

### <a name="to-target-windows-xp"></a>Windows XP를 대상으로 지정하려면

1. **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.

1. 프로젝트에 대 한 **속성 페이지** 대화 상자에서 **구성 속성** > **일반**을 선택 합니다. **플랫폼 도구 집합** 속성을 원하는 Windows XP 도구 집합으로 설정 합니다. 예를 들어 Visual Studio 2017에서 Microsoft C++ 컴파일러를 사용하여 Windows XP 및 Windows Server 2003에 대한 코드를 작성하려면 **Visual Studio 2017 - Windows XP(v141_xp)** 를 선택합니다.

### <a name="c-runtime-support"></a>C++ 런타임 지원

Windows XP 플랫폼 도구 집합과 함께 여러 라이브러리에는 Windows XP 및 Windows Server 2003에 대 한 런타임 지원이 포함 되어 있습니다. 이러한 라이브러리에는 CRT (C 런타임 라이브러리), C++ 표준 라이브러리, ATL (액티브 템플릿 라이브러리), concrt (동시성 런타임 Library), PPL (병렬 패턴 라이브러리), MFC 라이브러리 (MFC) 및 C++ AMP (C++ 가속화 된 대형 프로그래밍) 라이브러리가 있습니다. 이러한 운영 체제의 경우 지원 되는 최소 버전은 x 86 용 Windows XP 서비스 팩 3 (SP3), x 64 용 Windows XP 서비스 팩 2 (SP2) 및 x86 및 x 64의 경우 Windows Server 2003 SP2 (서비스 팩 2)입니다.

이러한 라이브러리는 대상에 따라 Visual Studio에서 설치하는 플랫폼 도구 집합을 통해 지원됩니다.

|라이브러리|Windows 데스크톱 앱을 대상으로 하는 기본 플랫폼 도구 집합|스토어 앱을 대상으로 하는 기본 플랫폼 도구 집합|Windows XP, Windows Server 2003을 대상으로 하는 Windows XP 플랫폼 도구 집합|
|---|---|---|---|
|CRT|X|X|X|
|C++ 표준 라이브러리|X|X|X|
|ATL|X|X|X|
|ConCRT/PPL|X|X|X|
|MFC|X||X|
|C++ AMP|X|X||

> [!NOTE]
> 작성 응용 프로그램은 C++ /cli CLI 및.NET Framework 4를 대상 Windows XP 및 Windows Server 2003에서 실행 합니다.

### <a name="differences-between-the-toolsets"></a>도구 집합 간의 차이점

플랫폼 및 라이브러리 지원의 차이로 인해 Windows XP 플랫폼 도구 집합을 사용 하는 앱에 대 한 개발 환경은 기본 Visual Studio 플랫폼 도구 집합을 사용 하는 앱의 경우 처럼 완전 하지 않습니다.

- **C++ 언어 기능**

   v110\_XP 플랫폼 도구 집합을 사용하는 앱은 Visual Studio 2012에서 구현된 C++ 언어 기능만 지원합니다. v120\_XP 플랫폼 도구 집합을 사용하는 앱은 Visual Studio 2013에서 구현된 C++ 언어 기능만 지원합니다. v140\_XP 플랫폼 도구 집합을 사용하는 앱은 Visual Studio 2015에서 구현된 C++ 언어 기능만 지원합니다. V141 C++\_xp 플랫폼 도구 집합을 사용 하는 앱에서는 Visual Studio 2017에서 구현 된 언어 기능만 지원 됩니다. Visual Studio는 이전 플랫폼 도구 집합을 사용하여 빌드할 때 해당 컴파일러를 사용합니다. 해당 버전의 컴파일러에서 구현 되는 추가 C++ 언어 기능을 활용 하려면 최신 Windows XP 플랫폼 도구 집합을 사용 합니다.

- **원격 디버깅**

   Visual Studio용 원격 도구는 Windows XP 또는 Windows Server 2003의 원격 디버깅을 지원하지 않습니다. Windows XP 또는 Windows Server 2003에서 로컬로 또는 원격으로 앱을 디버깅 하려면 이전 버전의 Visual Studio에서 디버거를 사용 합니다. 플랫폼 도구 집합의 런타임 대상인 Windows Vista에서 응용 프로그램을 디버깅 하는 것과 유사 하지만 원격 디버깅 대상이 아닙니다.

- **정적 분석**

   Windows 7 SDK의 SAL 주석과 런타임 라이브러리가 호환되지 않으므로 Windows XP 플랫폼 도구 집합은 정적 분석을 지원하지 않습니다. Windows XP 또는 Windows Server 2003를 지 원하는 앱에 대 한 정적 분석을 수행할 수 있습니다. 분석에 대 한 기본 플랫폼 도구 집합을 대상으로 하도록 솔루션을 일시적으로 전환한 다음 Windows XP 플랫폼 도구 집합으로 다시 전환 하 여 앱을 빌드합니다.

- **DirectX 그래픽 디버깅**

   그래픽 디버거는 Direct3D 9 API를 지원 하지 않기 때문에 Windows XP 또는 Windows Server 2003에서 Direct3D를 사용 하는 앱을 디버그 하는 데 사용할 수 없습니다. 그러나 앱이 Direct3D 10 또는 Direct3D 11 Api를 기반으로 하는 대체 렌더러를 구현 하는 경우 그래픽 디버거를 사용 하 여 문제를 진단할 수 있습니다.

- **HLSL 빌드**

   Windows XP 도구 집합은 기본적으로 HLSL 소스 코드 파일을 컴파일하지 않습니다. HLSL 파일을 컴파일하려면 2010년 6월 DirectX SDK를 다운로드하여 설치한 다음 해당 SDK를 포함하도록 프로젝트의 VC 디렉터리를 설정합니다. 자세한 내용은 [2010년 6월 DirectX SDK 다운로드 페이지](https://www.microsoft.com/download/details.aspx?displaylang=en&id=6812)의 "DirectX SDK가 Visual Studio 2010에 포함/라이브러리 경로를 등록하지 않음" 섹션을 참조하세요.
