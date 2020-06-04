---
title: 기존 ActiveX 컨트롤 업그레이드
ms.date: 09/12/2018
helpviewer_keywords:
- ActiveX controls [MFC], Internet
- LPK files for Internet controls
- safe for scripting and initialization (controls)
- OLE controls [MFC], upgrading to ActiveX
- CAB files, for ActiveX controls
- Internet applications [MFC], ActiveX controls
- Internet applications [MFC], packaging code for download
- upgrading ActiveX controls
- licensing ActiveX controls
ms.assetid: 4d12ddfa-b491-4f9f-a0b7-b51458e05651
ms.openlocfilehash: dfee42369b698956f4f91ab61a1f37e0ef06d9f1
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754511"
---
# <a name="upgrading-an-existing-activex-control"></a>기존 ActiveX 컨트롤 업그레이드

기존 ActiveX 컨트롤(이전 OLED 컨트롤)은 수정 없이 인터넷에서 사용할 수 있습니다. 그러나 컨트롤의 성능을 향상시키기 위해 컨트롤을 수정할 수 있습니다.

> [!IMPORTANT]
> ActiveX는 새로운 개발에 사용해서는 안 되는 레거시 기술입니다. ActiveX를 대체하는 최신 기술에 대한 자세한 내용은 [ActiveX 컨트롤](activex-controls.md)을 참조하십시오.

웹 페이지에서 컨트롤을 사용하는 경우 추가 고려 사항이 있습니다. .ocx 파일과 모든 지원 파일은 대상 컴퓨터에 있거나 인터넷을 통해 다운로드해야 합니다. 이렇게 하면 코드 크기와 다운로드 시간이 중요한 고려 사항입니다. 다운로드는 서명된 .cab 파일로 패키징할 수 있습니다. 스크립팅에 안전하고 초기화에 안전하다고 컨트롤을 표시할 수 있습니다.

이 문서는 다음 항목을 설명합니다.

- [다운로드를 위한 패키징 코드](#_core_packaging_code_for_downloading)

- [스크립팅 및 초기화를 위한 컨트롤 안전 표시](#_core_marking_a_control_safe_for_scripting_and_initializing)

- [라이선스 문제](#_core_licensing_issues)

- [서명 코드](#_core_signing_code)

- [팔레트 관리](#_core_managing_the_palette)

- [인터넷 익스플로러 브라우저 안전 수준 및 제어 동작](#_core_internet_explorer_browser_safety_levels_and_control_behavior)

[ActiveX 컨트롤: 최적화에](../mfc/mfc-activex-controls-optimization.md)설명된 대로 최적화를 추가할 수도 있습니다. Monikers는 [인터넷의 ActiveX 컨트롤에](../mfc/activex-controls-on-the-internet.md)설명된 대로 속성 및 큰 BLOB를 비동기적으로 다운로드하는 데 사용할 수 있습니다.

## <a name="packaging-code-for-downloading"></a><a name="_core_packaging_code_for_downloading"></a>다운로드를 위한 패키징 코드

이 주제에 대한 자세한 내용은 [ActiveX 컨트롤 패키징을](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa751974%28v%3dvs.85%29)참조하십시오.

### <a name="the-codebase-tag"></a>코드베이스 태그

ActiveX 컨트롤은 `<OBJECT>` 태그를 사용하여 웹 페이지에 포함됩니다. 태그의 매개 변수는 `CODEBASE` 컨트롤을 다운로드할 위치를 지정합니다. `<OBJECT>` `CODEBASE`여러 가지 다른 파일 형식을 성공적으로 가리킬 수 있습니다.

### <a name="using-the-codebase-tag-with-an-ocx-file"></a>OCX 파일이 있는 코드베이스 태그 사용

```
CODEBASE="http://example.microsoft.com/mycontrol.ocx#version=4,
    70,
    0,
    1086"
```

이 솔루션은 컨트롤의 .ocx 파일만 다운로드하며 지원되는 DLL을 클라이언트 컴퓨터에 이미 설치해야 합니다. 이는 Internet Explorer가 Visual C++ 컨트롤에 대한 지원 DLL과 함께 제공되므로 Visual C++로 빌드된 인터넷 익스플로러 및 MFC ActiveX 컨트롤에서 작동합니다. ActiveX 제어 가능 인 다른 인터넷 브라우저가이 컨트롤을 보려면 사용 하는 경우이 솔루션이 작동 하지 않습니다.

### <a name="using-the-codebase-tag-with-an-inf-file"></a>INF 파일이 있는 코드베이스 태그 사용

```
CODEBASE="http://example.microsoft.com/trustme.inf"
```

.inf 파일은 .ocx 및 지원 파일의 설치를 제어합니다. .inf 파일에 서명할 수 없으므로 이 방법은 권장되지 않습니다(코드 서명시 포인터에 대한 [코드 서명](#_core_signing_code) 참조).

### <a name="using-the-codebase-tag-with-a-cab-file"></a>CAB 파일이 있는 코드베이스 태그 사용

```
CODEBASE="http://example.microsoft.com/acontrol.cab#version=1,
    2,
    0,
    0"
```

캐비닛 파일은 MFC를 사용하는 ActiveX 컨트롤을 패키징하는 데 권장되는 방법입니다. 캐비닛 파일에서 MFC ActiveX 컨트롤을 패키징하면 .inf 파일을 포함하여 ActiveX 컨트롤 및 종속 DLL(예: MFC DLL)의 설치를 제어할 수 있습니다. CAB 파일을 사용하면 코드를 자동으로 압축하여 더 빠르게 다운로드할 수 있습니다. 구성 요소 다운로드에 .cab 파일을 사용하는 경우 각 개별 구성 요소보다 전체 .cab 파일에 서명하는 것이 더 빠릅니다.

### <a name="creating-cab-files"></a>CAB 파일 만들기

캐비닛 파일을 만드는 도구는 이제 윈도우의 일부입니다 [10 SDK](https://dev.windows.com/downloads/windows-10-sdk).

가리키는 캐비닛 파일에는 `CODEBASE` ActiveX 컨트롤의 .ocx 파일과 설치를 제어하는 .inf 파일이 포함되어야 합니다. 컨트롤 파일의 이름과 .inf 파일을 지정하여 캐비닛 파일을 만듭니다. 이 캐비닛 파일에 시스템에 이미 있을 수 있는 종속 DLL을 포함하지 마십시오. 예를 들어 MFC DLL은 별도의 캐비닛 파일에 패키징되며 제어 .inf 파일에 의해 참조됩니다.

CAB 파일을 만드는 방법에 대한 자세한 내용은 [CAB 파일 만들기](/windows/win32/devnotes/cabinet-api-functions)를 참조하십시오.

### <a name="the-inf-file"></a>INF 파일

다음 예제인 spindial.inf에서는 지원 파일과 MFC 스핀다이얼 제어에 필요한 버전 정보를 나열합니다. MFC DLL의 위치는 Microsoft 웹 사이트입니다. mfc42.cab은 Microsoft에서 제공하고 서명합니다.

```
Contents of spindial.inf:
[mfc42installer]
file-win32-x86=http://activex.microsoft.com/controls/vc/mfc42.cab
[Olepro32.dll] - FileVersion=5,
    0,
    4261,
    0
[Mfc42.dll] - FileVersion=6,
    0,
    8168,
    0
[Msvcrt.dll] - FileVersion=6,
    0,
    8168,
    0
```

### <a name="the-object-tag"></a>\<개체> 태그

다음 예제에서는 `<OBJECT>` 태그를 사용하여 MFC Spindial 샘플 컨트롤을 패키징하는 방법을 보여 줍니다.

```
<OBJECT ID="Spindial1" WIDTH=100 HEIGHT=51
    CLASSID="CLSID:06889605-B8D0-101A-91F1-00608CEAD5B3"
    CODEBASE="http://example.microsoft.com/spindial.cab#Version=1,0,0,001">
<PARAM NAME="_Version" VALUE="65536">
<PARAM NAME="_ExtentX" VALUE="2646">
<PARAM NAME="_ExtentY" VALUE="1323">
<PARAM NAME="_StockProps" VALUE="0">
<PARAM NAME="NeedlePosition" VALUE="2">
</OBJECT>
```

이 경우 spindial.cab에는 spindial.ocx 와 spindial.inf의 두 개의 파일이 포함됩니다. 다음 명령은 캐비닛 파일을 빌드합니다.

```
C:\CabDevKit\cabarc.exe -s 6144 N spindial.cab spindial.ocx spindial.inf
```

매개 `-s 6144` 변수는 코드 서명을 위해 캐비닛에 공간을 예약합니다.

### <a name="the-version-tag"></a>버전 태그

CAB 파일로 `#Version` 지정된 정보는 `<OBJECT>` 태그의 *CLASSID* 매개 변수에 의해 지정된 컨트롤에 적용됩니다.

지정된 버전에 따라 컨트롤을 강제로 다운로드할 수 있습니다. `OBJECT` *CODEBASE* 매개 변수를 포함한 태그의 전체 사양은 W3C 참조를 참조하십시오.

## <a name="marking-a-control-safe-for-scripting-and-initializing"></a><a name="_core_marking_a_control_safe_for_scripting_and_initializing"></a>스크립팅 및 초기화를 위한 컨트롤 안전 표시

웹 페이지에 사용되는 ActiveX 컨트롤은 스크립팅에 안전하며 실제로 안전한 경우 초기화에 안전합니다. 안전 제어는 디스크 IO를 수행하거나 컴퓨터의 메모리 또는 레지스터에 직접 액세스하지 않습니다.

컨트롤은 스크립팅에 안전하고 레지스트리를 통해 초기화하는 데 안전하다고 표시할 수 있습니다. 레지스트리의 스크립팅 및 지속성에 대한 안전한 컨트롤로 표시하려면 다음과 유사한 항목을 추가하도록 수정합니다. `DllRegisterServer` 다른 방법은 을 `IObjectSafety`구현하는 것입니다.

스크립팅 및 지속성에 대해 안전하다고 표시하기 위해 컨트롤에 대한 GUID(전역 고유 식별자)를 정의합니다. 안전하게 스크립팅할 수 있는 컨트롤에는 다음과 유사한 레지스트리 항목이 포함됩니다.

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
```

영구 데이터에서 안전하게 초기화할 수 있는 컨트롤은 다음과 유사한 레지스트리 항목을 사용하여 지속성에 대해 안전한 것으로 표시됩니다.

```
HKEY_CLASSES_ROOT\Component Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

키를 다음 클래스 ID와 연결하려면 다음(컨트롤의 클래스 ID `{06889605-B8D0-101A-91F1-00608CEAD5B3}`대신 대체)과 유사한 항목을 추가합니다.

```
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95801-9882-11CF-9FA9-00AA006C42C4}
HKEY_CLASSES_ROOT\CLSID\{06889605-B8D0-101A-91F1-00608CEAD5B3}\Implemented Categories\{7DD95802-9882-11CF-9FA9-00AA006C42C4}
```

## <a name="licensing-issues"></a><a name="_core_licensing_issues"></a>라이선싱 문제

웹 페이지에서 사용이 허가된 컨트롤을 사용하려면 사용권 계약이 인터넷에서 사용할 수 있는지 확인하고 라이센스 패키지 파일(LPK)을 만들어야 합니다.

Internet Explorer를 실행하는 컴퓨터가 컨트롤을 사용하도록 라이선스가 부여되지 않은 경우 라이선스가 부여된 ActiveX 컨트롤이 HTML 페이지에서 제대로 로드되지 않습니다. 예를 들어 Visual C++를 사용하여 라이선스가 부여된 컨트롤을 빌드한 경우 컨트롤을 사용하는 HTML 페이지가 컨트롤이 빌드된 컴퓨터에서 제대로 로드되지만 라이선스 정보가 포함되지 않는 한 다른 컴퓨터에서는 로드되지 않습니다.

Internet Explorer에서 라이선스가 부여된 ActiveX 컨트롤을 사용하려면 공급업체의 사용권 계약을 확인하여 제어에 대한 라이센스가 허용되는지 확인해야 합니다.

- 재배포

- 인터넷에서 컨트롤 사용

- 코드베이스 매개 변수 사용

라이센스가 없는 컴퓨터의 HTML 페이지에서 라이선스가 부여된 컨트롤을 사용하려면 라이센스 패키지 파일(LPK)을 생성해야 합니다. LPK 파일에는 HTML 페이지에서 사용이 허가된 컨트롤에 대한 런타임 라이선스가 포함되어 있습니다. 이 파일은 LPK_TOOL 통해 생성됩니다. 액티브X SDK와 함께 제공되는 EXE.

#### <a name="to-create-an-lpk-file"></a>LPK 파일을 만들려면

1. LPK_TOOL 실행합니다. 컨트롤을 사용하도록 라이선스가 부여된 컴퓨터의 EXE입니다.

1. 사용 **가능한** 컨트롤 목록 상자에서 사용 **가능한 컨트롤** 목록 상자에서 사용 가능한 사용 가능한 ActiveX 컨트롤을 선택하고 HTML 페이지에서 사용할 각 ActiveX 컨트롤을 선택하고 **추가**를 클릭합니다.

1. **종료 & 저장을** 클릭하고 LPK 파일의 이름을 입력합니다. 이렇게 하면 LPK 파일이 생성되고 응용 프로그램이 닫힙됩니다.

#### <a name="to-embed-a-licensed-control-on-an-html-page"></a>HTML 페이지에 라이선스가 부여된 컨트롤을 포함하려면

1. HTML 페이지를 편집합니다. HTML 페이지에서 다른 \< \<OBJECT> 태그 앞에 라이센스 관리자 개체에 대한 OBJECT> 태그를 삽입합니다. 라이센스 관리자는 인터넷 익스플로러와 함께 설치된 ActiveX 컨트롤입니다. 클래스 ID는 다음과 같습니다. 라이센스 관리자 개체의 LPKPath 속성을 LPK 파일의 경로 및 이름으로 설정합니다. HTML 페이지당 LPK 파일은 하나만 가질 수 있습니다.

```
<OBJECT CLASSID = "clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="relative URL to .LPK file">
</OBJECT>
```

1. 라이센스 \<관리자 태그 다음라이센스 컨트롤에 대한 OBJECT> 태그를 삽입합니다.

   예를 들어 Microsoft 마스머티드 편집 컨트롤을 표시하는 HTML 페이지가 아래에 표시됩니다. 첫 번째 클래스 ID는 라이센스 관리자 컨트롤용이며 두 번째 클래스 ID는 마스크된 편집 컨트롤용입니다. 태그를 변경하여 이전에 만든 .lpk 파일의 상대 경로를 가리키고 컨트롤의 클래스 ID를 포함한 개체 태그를 추가합니다.

1. NCompass ActiveX 플러그인을 \<사용하는 경우 LPK 파일에 대한 EMBED> 특성을 삽입합니다.

   예를 들어 NCompass ActiveX 플러그인을 사용하는 Netscape와 같은 다른 Active 지원 브라우저에서 컨트롤을 \<볼 수 있는 경우 아래와 같이 EMBED> 구문을 추가해야 합니다.

```
<OBJECT CLASSID="clsid:5220cb21-c88d-11cf-b347-00aa00a28331">
<PARAM NAME="LPKPath" VALUE="maskedit.lpk">

<EMBED SRC = "maskedit.LPK">

</OBJECT>
<OBJECT CLASSID="clsid:C932BA85-4374-101B-A56C-00AA003668DC" WIDTH=100 HEIGHT=25>
</OBJECT>
```

제어 라이선스에 대한 자세한 내용은 [ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../mfc/mfc-activex-controls-licensing-an-activex-control.md)를 참조하십시오.

## <a name="signing-code"></a><a name="_core_signing_code"></a>서명 코드

코드 서명은 코드의 소스를 식별하고 코드가 서명된 이후 변경되지 않도록 하기 위해 설계되었습니다. 브라우저 안전 설정에 따라 코드를 다운로드하기 전에 사용자에게 경고가 표시될 수 있습니다. 사용자는 특정 인증서 소유자 또는 회사를 신뢰하도록 선택할 수 있으며, 이 경우 신뢰할 수 있는 사용자가 서명한 코드는 경고 없이 다운로드됩니다. 코드는 변조를 방지하기 위해 디지털 서명됩니다.

신뢰 경고 메시지를 표시하지 않고 컨트롤을 자동으로 다운로드할 수 있도록 최종 코드가 서명되어 있는지 확인합니다. 코드 에 서명하는 방법에 대한 자세한 내용은 ActiveX SDK의 Authenticode설명서를 참조하고 [CAB 파일 서명을](/windows/win32/devnotes/cabinet-api-functions)참조하십시오.

신뢰 및 브라우저 안전 수준 설정에 따라 서명자 또는 회사를 식별하기 위한 인증서가 표시될 수 있습니다. 안전 수준이 없음이거나 서명된 컨트롤의 인증서 소유자가 신뢰할 수 있는 경우 인증서가 표시되지 않습니다. 브라우저 안전 설정에서 컨트롤을 다운로드하고 인증서를 표시하는지 여부를 결정하는 방법에 대한 자세한 내용은 [Internet Explorer 브라우저 안전 수준 및 제어 동작을](#_core_internet_explorer_browser_safety_levels_and_control_behavior) 참조하십시오.

디지털 서명은 코드가 서명된 이후로 변경되지 않음을 보장합니다. 코드의 해시가 수행되어 인증서에 포함됩니다. 이 해시는 나중에 코드를 다운로드한 후 실행되기 전에 수행된 코드의 해시와 비교됩니다. Verisign과 같은 회사는 코드에 서명하는 데 필요한 개인 및 공개 키를 제공할 수 있습니다. ActiveX SDK는 테스트 인증서를 만들기 위한 유틸리티인 MakeCert와 함께 제공됩니다.

## <a name="managing-the-palette"></a><a name="_core_managing_the_palette"></a>팔레트 관리

컨테이너는 팔레트를 결정하고 DISPID_AMBIENT_PALETTE **환경**속성으로 사용할 수 있도록 합니다. 컨테이너(예: Internet Explorer)는 페이지의 모든 ActiveX 컨트롤에서 자체 팔레트를 결정하는 데 사용되는 팔레트를 선택합니다. 이렇게 하면 디스플레이가 깜박이는 것을 방지하고 일관된 모양을 제공합니다.

컨트롤을 재정의하여 `OnAmbientPropertyChange` 팔레트에 대한 변경 내용 알림을 처리할 수 있습니다.

컨트롤은 팔레트를 `OnGetColorSet` 그리는 색상 세트를 반환하도록 재정의할 수 있습니다. 컨테이너는 반환 값을 사용하여 컨트롤이 팔레트를 인식하는지 확인합니다.

OCX 96 지침에 따라 컨트롤은 항상 백그라운드에서 해당 팔레트를 실현해야 합니다.

앰비언트 팔레트 속성을 사용하지 않는 이전 컨테이너는 WM_QUERYNEWPALETTE 메시지를 보내고 WM_PALETTECHANGED 메시지를 보냅니다. 컨트롤은 이러한 `OnQueryNewPalette` 메시지를 `OnPaletteChanged` 재정의하고 처리할 수 있습니다.

## <a name="internet-explorer-browser-safety-levels-and-control-behavior"></a><a name="_core_internet_explorer_browser_safety_levels_and_control_behavior"></a>인터넷 익스플로러 브라우저 안전 수준 및 제어 동작

브라우저에는 사용자가 구성할 수 있는 안전 수준에 대한 옵션이 있습니다. 웹 페이지에는 사용자의 컴퓨터에 해를 끼칠 수 있는 활성 콘텐츠가 포함될 수 있으므로 브라우저를 통해 사용자가 안전 수준에 대한 옵션을 선택할 수 있습니다. 브라우저가 안전 수준을 구현하는 방식에 따라 컨트롤이 전혀 다운로드되지 않거나 사용자가 런타임에 컨트롤을 다운로드할지 여부를 선택할 수 있도록 인증서 또는 경고 메시지가 표시됩니다. Internet Explorer에서 높음, 중간 및 낮은 안전 수준에서 ActiveX 제어동작은 다음과 같습니다.

### <a name="high-safety-mode"></a>높은 안전 모드

- 서명되지 않은 컨트롤은 다운로드되지 않습니다.

- 서명된 컨트롤은 신뢰할 수 없는 경우 인증서를 표시합니다(사용자는 지금부터 이 인증서 소유자로부터 코드를 항상 신뢰하는 옵션을 선택할 수 있습니다).

- 안전으로 표시된 컨트롤만 영구 데이터 및/또는 스크립팅가능합니다.

### <a name="medium-safety-mode"></a>중간 안전 모드

- 서명되지 않은 컨트롤은 다운로드하기 전에 경고가 표시됩니다.

- 서명된 컨트롤은 신뢰할 수 없는 경우 인증서를 표시합니다.

- 안전으로 표시되지 않은 컨트롤에는 경고가 표시됩니다.

### <a name="low-safety-mode"></a>낮은 안전 모드

- 컨트롤은 경고 없이 다운로드됩니다.

- 스크립팅 및 지속성은 경고 없이 발생합니다.

## <a name="see-also"></a>참조

[MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)<br/>
[MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)<br/>
[MFC ActiveX 컨트롤: ActiveX 컨트롤 라이선스](../mfc/mfc-activex-controls-licensing-an-activex-control.md)
