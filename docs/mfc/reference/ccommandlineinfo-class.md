---
title: CCommandLineInfo 클래스
ms.date: 11/04/2016
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
ms.openlocfilehash: 0b4d5e5d253f2eb10388a69286d21e2190826eba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369456"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo 클래스

애플리케이션을 시작할 때 명령줄을 구문 분석하는 데 유용합니다.

## <a name="syntax"></a>구문

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|기본 `CCommandLineInfo` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|이 콜백을 재정의하여 개별 매개 변수를 구문 분석합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CCommandLineInfo::m_bRunAutomated](#m_brunautomated)|명령줄 `/Automation` 옵션이 발견했음을 나타냅니다.|
|[CCommandLineInfo::m_bRunEmbedded](#m_brunembedded)|명령줄 `/Embedding` 옵션이 발견했음을 나타냅니다.|
|[CCommandLineInfo::m_bShowSplash](#m_bshowsplash)|시작 화면이 표시되어야 하는지 를 나타냅니다.|
|[CCommandLineInfo::m_nShellCommand](#m_nshellcommand)|처리할 셸 명령을 나타냅니다.|
|[CCommandLineInfo::m_strDriverName](#m_strdrivername)|셸 명령이 인쇄 할 때 드라이버 이름을 나타냅니다. 그렇지 않으면 비어 있습니다.|
|[CCommandLineInfo::m_strFileName](#m_strfilename)|열어 보거나 인쇄할 파일 이름을 나타냅니다. 셸 명령이 New 또는 DDE인 경우 비어 있습니다.|
|[CCommandLineInfo::m_strPortName](#m_strportname)|셸 명령이 인쇄 할 수 있는 경우 포트 이름을 나타냅니다. 그렇지 않으면 비어 있습니다.|
|[CCommandLineInfo::m_strPrinterName](#m_strprintername)|셸 명령이 인쇄 할 수 있는 경우 프린터 이름을 나타냅니다. 그렇지 않으면 비어 있습니다.|
|[CCommandLineInfo::m_strRestartIdentifier](#m_strrestartidentifier)|다시 시작 관리자가 응용 프로그램을 다시 시작한 경우 다시 시작 관리자에 대한 고유 다시 시작 식별자를 나타냅니다.|

## <a name="remarks"></a>설명

MFC 응용 프로그램은 일반적으로 해당 응용 프로그램 개체의 [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 함수에서 이 클래스의 로컬 인스턴스를 만듭니다. 그런 다음 이 개체는 [CWinApp::ParseCommandLine으로](../../mfc/reference/cwinapp-class.md#parsecommandline)전달되며, 이 개체는 [반복적으로 ParseParam을](#parseparam) 호출하여 개체를 `CCommandLineInfo` 채웁니다. 그런 `CCommandLineInfo` 다음 개체가 [CWinApp::ProcessShellCommand에](../../mfc/reference/cwinapp-class.md#processshellcommand) 전달되어 명령줄 인수 및 플래그를 처리합니다.

이 개체를 사용하여 다음 명령줄 옵션 및 매개 변수를 캡슐화할 수 있습니다.

|명령줄 인수|실행된 명령|
|----------------------------|----------------------|
|*app*|새 파일입니다.|
|*앱* 파일 이름|파일을 엽니다.|
|*앱* `/p` 파일 이름|파일을 기본 프린터로 인쇄합니다.|
|*앱* `/pt` 파일 이름 프린터 드라이버 포트|지정된 프린터로 파일을 인쇄합니다.|
|*app* `/dde`|DDE 명령을 시작하고 기다립니다.|
|*app* `/Automation`|OLE 자동화 서버로 시작합니다.|
|*app* `/Embedding`|임베디드 OLE 항목을 편집하려면 시작합니다.|
|*app* `/Register`<br /><br /> *app* `/Regserver`|응용 프로그램에 등록 작업을 수행하도록 알립니다.|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|등록 취소 작업을 수행하도록 응용 프로그램에 알립니다.|

다른 플래그 및 `CCommandLineInfo` 매개 변수 값을 처리 하려면 에서 새 클래스를 파생 합니다. 새 플래그를 처리하려면 [ParseParam을](#parseparam) 재정의합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a>CCommandLineInfo::CCommandLineInfo

이 생성자는 `CCommandLineInfo` 기본값을 가진 개체를 만듭니다.

```
CCommandLineInfo();
```

### <a name="remarks"></a>설명

기본값은 시작 화면()을 `m_bShowSplash=TRUE`표시하고 파일 메뉴에서 새 `m_nShellCommand`명령을 실행하는 **것입니다(=NewFile).**

응용 프로그램 프레임워크는 [ParseParam을](#parseparam) 호출하여 이 개체의 데이터 멤버를 채웁니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a>CCommandLineInfo::m_bRunAutomated

명령줄에서 `/Automation` 플래그가 발견했음을 나타냅니다.

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>설명

TRUE인 경우 OLE 자동화 서버로 시작한다는 의미입니다.

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a>CCommandLineInfo::m_bRunEmbedded

명령줄에서 `/Embedding` 플래그가 발견했음을 나타냅니다.

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>설명

TRUE인 경우 포함된 OLE 항목을 편집하기 시작합니다.

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a>CCommandLineInfo::m_bShowSplash

시작 화면이 표시되어야 음을 나타냅니다.

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>설명

TRUE인 경우 시작 하는 동안이 응용 프로그램에 대 한 시작 화면 표시 해야 합니다. [ParseParam의](#parseparam) 기본 구현은 [m_nShellCommand](#m_nshellcommand) 와 같으면 이 `CCommandLineInfo::FileNew`데이터 멤버를 TRUE로 설정합니다.

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a>CCommandLineInfo::m_nShellCommand

응용 프로그램의 이 인스턴스에 대한 셸 명령을 나타냅니다.

```
m_nShellCommand;
```

### <a name="remarks"></a>설명

이 데이터 멤버의 형식은 `CCommandLineInfo` 클래스에 정의된 다음 수거된 형식입니다.

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

이러한 값에 대한 간략한 설명은 다음 목록을 참조하십시오.

- `CCommandLineInfo::FileNew`명령줄에서 파일 이름을 찾을 수 없음을 나타냅니다.

- `CCommandLineInfo::FileOpen`명령줄에서 파일 이름이 발견되었으며 명령줄에서 `/p` `/pt` `/dde`다음 플래그가 없음을 나타냅니다.

- `CCommandLineInfo::FilePrint`명령줄에서 `/p` 플래그가 발견했음을 나타냅니다.

- `CCommandLineInfo::FilePrintTo`명령줄에서 `/pt` 플래그가 발견했음을 나타냅니다.

- `CCommandLineInfo::FileDDE`명령줄에서 `/dde` 플래그가 발견했음을 나타냅니다.

- `CCommandLineInfo::AppRegister``/Register` 명령줄에서 `/Regserver` 또는 플래그가 발견되었고 응용 프로그램이 등록하라는 메시지가 표시되었습니다.

- `CCommandLineInfo::AppUnregister``/Unregister` 또는 `/Unregserver` 응용 프로그램이 등록을 취소하라는 메시지가 표시되어 있음을 나타냅니다.

- `CCommandLineInfo::RestartByRestartManager`다시 시작 관리자가 응용 프로그램을 다시 시작했음을 나타냅니다.

- `CCommandLineInfo::FileNothing`시작 시 새 MDI 자식 창의 표시를 끕니다. 응용 프로그램 마법사에서 생성한 MDI 응용 프로그램은 의도적으로 시작 시 새 자식 창을 표시합니다. 이 기능을 끄려면 `CCommandLineInfo::FileNothing` [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)를 호출할 때 응용 프로그램을 셸 명령으로 사용할 수 있습니다. `ProcessShellCommand`파생된 모든 `InitInstance( )` `CWinApp` 클래스에서 호출됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a>CCommandLineInfo::m_strDriverName

세 번째 비플래그 매개 변수 값을 명령줄에 저장합니다.

```
CString m_strDriverName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 인쇄 쉘 명령에 대한 프린터 드라이버의 이름입니다. [ParseParam의](#parseparam) 기본 구현은 명령줄에서 `/pt` 플래그가 발견된 경우에만 이 데이터 멤버를 설정합니다.

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a>CCommandLineInfo::m_strFileName

명령줄에 첫 번째 비플래그 매개 변수의 값을 저장합니다.

```
CString m_strFileName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 열 파일의 이름입니다.

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a>CCommandLineInfo::m_strPortName

명령줄에 네 번째 비플래그 매개 변수의 값을 저장합니다.

```
CString m_strPortName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 인쇄 쉘 명령에 대한 프린터 포트의 이름입니다. [ParseParam의](#parseparam) 기본 구현은 명령줄에서 `/pt` 플래그가 발견된 경우에만 이 데이터 멤버를 설정합니다.

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a>CCommandLineInfo::m_strPrinterName

두 번째 비플래그 매개 변수 값을 명령줄에 저장합니다.

```
CString m_strPrinterName;
```

### <a name="remarks"></a>설명

이 매개 변수는 일반적으로 인쇄 쉘 명령에 대한 프린터의 이름입니다. [ParseParam의](#parseparam) 기본 구현은 명령줄에서 `/pt` 플래그가 발견된 경우에만 이 데이터 멤버를 설정합니다.

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a>CCommandLineInfo::m_strRestartIdentifier

명령줄에서 고유한 다시 시작 식별자입니다.

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>설명

다시 시작 식별자는 응용 프로그램의 각 인스턴스에 대해 고유합니다.

다시 시작 관리자가 응용 프로그램을 종료하고 다시 시작하도록 구성된 경우 다시 시작 관리자는 다시 시작 식별자를 선택적 매개 변수로 명령줄에서 응용 프로그램을 실행합니다. 다시 시작 관리자가 다시 시작 식별자를 사용하는 경우 응용 프로그램은 이전에 열려 있는 문서를 다시 열고 자동 저장된 파일을 복구할 수 있습니다.

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a>CCommandLineInfo::P아르스파라임

프레임워크는 이 함수를 호출하여 명령줄에서 개별 매개 변수를 구문 분석/해석합니다. 두 번째 버전은 유니코드 프로젝트의 첫 번째 버전과 다릅니다.

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);

virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>매개 변수

*pszParam*<br/>
매개 변수 또는 플래그입니다.

*b플래그*<br/>
*pszParam이* 매개 변수인지 플래그인지 를 나타냅니다.

*폭발*<br/>
이것이 명령줄의 마지막 매개 변수 또는 플래그인지 를 나타냅니다.

### <a name="remarks"></a>설명

[CWinApp::ParseCommandLine은](../../mfc/reference/cwinapp-class.md#parsecommandline) 명령줄의 각 매개 변수 또는 플래그에 대해 한 번 호출하여 `ParseParam` 인수를 *pszParam에*전달합니다. 매개 변수의 첫 번째 문자가 '또는 **/**''인 **-** 경우 제거되고 *bFlag가* TRUE로 설정됩니다. 최종 매개변수를 구문 분석할 때 *bLast는* TRUE로 설정됩니다.

이 함수의 기본 구현은 다음 `/p`표와 `/Automation`같이 `/Embedding`다음과 `/pt` `/dde`같은 플래그를 인식합니다.

|명령줄 인수|실행된 명령|
|----------------------------|----------------------|
|*app*|새 파일입니다.|
|*앱* 파일 이름|파일을 엽니다.|
|*앱* `/p` 파일 이름|파일을 기본 프린터로 인쇄합니다.|
|*앱* `/pt` 파일 이름 프린터 드라이버 포트|지정된 프린터로 파일을 인쇄합니다.|
|*app* `/dde`|DDE 명령을 시작하고 기다립니다.|
|*app* `/Automation`|OLE 자동화 서버로 시작합니다.|
|*app* `/Embedding`|임베디드 OLE 항목을 편집하려면 시작합니다.|
|*app* `/Register`<br /><br /> *app* `/Regserver`|응용 프로그램에 등록 작업을 수행하도록 알립니다.|
|*app* `/Unregister`<br /><br /> *app* `/Unregserver`|등록 취소 작업을 수행하도록 응용 프로그램에 알립니다.|

이 정보는 [m_bRunAutomated,](#m_brunautomated) [m_bRunEmbedded](#m_brunembedded)및 [m_nShellCommand](#m_nshellcommand)에 저장됩니다. 플래그는 정방향 슬래시 ' **/** 또는 하이픈 ' **-**'로 표시됩니다.

기본 구현은 첫 번째 비플래그 매개 변수를 [m_strFileName.](#m_strfilename) `/pt` 플래그의 경우 기본 구현은 두 번째, 세 번째 및 네 번째 비플래그 매개 변수를 각각 [m_strPrinterName,](#m_strprintername) [m_strDriverName](#m_strdrivername)및 [m_strPortName](#m_strportname)에 넣습니다.

또한 기본 구현에서는 새 파일의 경우에만 [m_bShowSplash](#m_bshowsplash) TRUE로 설정합니다. 새 파일의 경우 사용자는 응용 프로그램 자체와 관련된 작업을 수행했습니다. 셸을 사용하여 기존 파일을 여는 것을 포함하여 다른 경우에는 사용자 작업에 파일이 직접 포함됩니다. 문서 중심의 관점에서 시작 화면에서는 응용 프로그램을 시작할 때 를 발표할 필요가 없습니다.

파생 클래스에서 이 함수를 재정의하여 다른 플래그 및 매개 변수 값을 처리합니다.

## <a name="see-also"></a>참고 항목

[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CWinApp::P거칠은 커맨드라인](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp::P로키스셸커맨드](../../mfc/reference/cwinapp-class.md#processshellcommand)
