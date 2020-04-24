---
title: C키보드관리자 클래스
ms.date: 11/04/2016
f1_keywords:
- CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CKeyboardManager
- AFXKEYBOARDMANAGER/CKeyboardManager::CleanUp
- AFXKEYBOARDMANAGER/CKeyboardManager::FindDefaultAccelerator
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyHandled
- AFXKEYBOARDMANAGER/CKeyboardManager::IsKeyPrintable
- AFXKEYBOARDMANAGER/CKeyboardManager::IsShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::LoadState
- AFXKEYBOARDMANAGER/CKeyboardManager::ResetAll
- AFXKEYBOARDMANAGER/CKeyboardManager::SaveState
- AFXKEYBOARDMANAGER/CKeyboardManager::ShowAllAccelerators
- AFXKEYBOARDMANAGER/CKeyboardManager::TranslateCharToUpper
- AFXKEYBOARDMANAGER/CKeyboardManager::UpdateAccelTable
helpviewer_keywords:
- CKeyboardManager [MFC], CKeyboardManager
- CKeyboardManager [MFC], CleanUp
- CKeyboardManager [MFC], FindDefaultAccelerator
- CKeyboardManager [MFC], IsKeyHandled
- CKeyboardManager [MFC], IsKeyPrintable
- CKeyboardManager [MFC], IsShowAllAccelerators
- CKeyboardManager [MFC], LoadState
- CKeyboardManager [MFC], ResetAll
- CKeyboardManager [MFC], SaveState
- CKeyboardManager [MFC], ShowAllAccelerators
- CKeyboardManager [MFC], TranslateCharToUpper
- CKeyboardManager [MFC], UpdateAccelTable
ms.assetid: 4809ece6-89df-4479-8b53-9bf476ee107b
ms.openlocfilehash: a8053ab33a2b49eb2c447cdaa1cb2b9e356bc696
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754922"
---
# <a name="ckeyboardmanager-class"></a>C키보드관리자 클래스

주 프레임 창 및 자식 프레임 창에 대한 바로 가기 키 테이블을 관리합니다.

## <a name="syntax"></a>구문

```
class CKeyboardManager : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[C키보드 관리자::C키보드 관리자](#ckeyboardmanager)|`CKeyboardManager` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[C키보드 관리자::정리](#cleanup)|바로 가기 키 테이블을 지웁니다.|
|[C키보드 관리자::찾기기본 가속기](#finddefaultaccelerator)|지정된 명령 및 창에 대한 기본 바로 가기 키를 검색합니다.|
|[C키보드 관리자::IsKeyHandled](#iskeyhandled)|가속기 테이블에서 키를 처리하는지 여부를 결정합니다.|
|[C키보드 관리자::키인쇄 가능](#iskeyprintable)|문자를 인쇄할 수 있는지 여부를 나타냅니다.|
|[C키보드 매니저::IsShowAllAccelerators](#isshowallaccelerators)|메뉴에 명령의 모든 바로 가기 키또는 기본 바로 가기 키만 표시되는지 여부를 나타냅니다.|
|[C키보드 관리자::로드스테이트](#loadstate)|Windows 레지스트리에서 바로 가기 키 테이블을 로드합니다.|
|[C키보드 관리자::모두 재설정](#resetall)|응용 프로그램 리소스에서 바로 가기 키 테이블을 다시 로드합니다.|
|[C키보드 관리자::저장 상태](#savestate)|바로 가기 키 테이블을 Windows 레지스트리에 저장합니다.|
|[C키보드 매니저::쇼알아셀러레이터](#showallaccelerators)|프레임워크에 모든 명령에 대한 모든 바로 가기 키또는 각 명령에 대한 단일 바로 가기 키가 표시되는지 여부를 지정합니다. 이 메서드는 연결된 바로 가기 키가 하나만 있는 명령에는 영향을 주지 않습니다.|
|[C키보드 관리자::번역차토어퍼](#translatechartoupper)|문자를 상위 레지스터로 변환합니다.|
|[C 키보드 관리자::업데이트Acceltable](#updateacceltable)|바로 가기 키 테이블을 새 바로 가기 키 테이블로 업데이트합니다.|

## <a name="remarks"></a>설명

이 클래스의 멤버를 사용하면 바로 가기 키 테이블을 저장하고 Windows 레지스트리에 로드하고, 템플릿을 사용하여 바로 가기 키 테이블을 업데이트하고, 프레임 창에서 명령에 대한 기본 바로 가기 키를 찾을 수 있습니다. 또한 개체를 `CKeyboardManager` 사용하면 바로 가기 키가 사용자에게 표시되는 방법을 제어할 수 있습니다.

개체를 `CKeyboardManager` 수동으로 만들지 않아야 합니다. 응용 프로그램의 프레임워크에 의해 자동으로 만들어집니다. 그러나 응용 프로그램의 초기화 프로세스 중에 [CWinAppEx::InitKeyboardManager를](../../mfc/reference/cwinappex-class.md#initkeyboardmanager) 호출해야 합니다. 응용 프로그램에 대한 키보드 관리자에 대한 포인터를 얻으려면 [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)로 전화하십시오.

## <a name="example"></a>예제

다음 예제에서는 `CKeyboardManager` `CWinAppEx` 클래스에서 개체에 대한 포인터를 검색하는 방법과 메뉴 명령과 관련된 모든 바로 가기 키를 표시하는 방법을 보여 줍니다. 이 코드 조각은 사용자 [지정 페이지 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_CustomPages#5](../../mfc/reference/codesnippet/cpp/ckeyboardmanager-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CKeyboardManager](../../mfc/reference/ckeyboardmanager-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx키보드매니저.h

## <a name="ckeyboardmanagerckeyboardmanager"></a><a name="ckeyboardmanager"></a>C키보드 관리자::C키보드 관리자

`CKeyboardManager` 개체를 생성합니다.

```
CKeyboardManager();
```

### <a name="remarks"></a>설명

대부분의 경우 `CKeyboardManager` 직접 만들 필요가 없습니다. 기본적으로 프레임 워크는 당신을 위해 하나를 만듭니다. 에 대한 포인터를 `CKeyboardManager`얻으려면 [CWinAppEx::GetKeyboardManager](../../mfc/reference/cwinappex-class.md#getkeyboardmanager)를 호출하십시오. 수동으로 만드는 경우 [CWinAppEx::InitKeyboardManager](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)메서드를 사용하여 초기화해야 합니다.

## <a name="ckeyboardmanagercleanup"></a><a name="cleanup"></a>C키보드 관리자::정리

리소스를 `CKeyboardManager` 해제하고 모든 바로 가기 키 매핑을 지웁니다.

```
static void CleanUp();
```

### <a name="remarks"></a>설명

바로 가기 키에 대한 자세한 내용은 [키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)을 참조하십시오.

프레임워크가 응용 프로그램 종료 중에 자동으로 호출되므로 응용 프로그램이 종료될 때 이 함수를 호출할 필요가 없습니다.

## <a name="ckeyboardmanagerfinddefaultaccelerator"></a><a name="finddefaultaccelerator"></a>C키보드 관리자::찾기기본 가속기

지정된 명령 및 창에 대한 기본 바로 가기 키를 검색합니다.

```
static BOOL FindDefaultAccelerator(
    UINT uiCmd,
    CString& str,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>매개 변수

*uiCmd*<br/>
【인】 명령 ID입니다.

*Str*<br/>
[out] `CString` 개체에 대한 참조입니다.

*pWnd프레임*<br/>
【인】 프레임 창에 대한 포인터입니다.

*비스디폴디프레임*<br/>
【인】 프레임 창이 기본 프레임 창인지 여부를 지정합니다.

### <a name="return-value"></a>Return Value

바로 가기를 발견하면 비영; 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 메서드는 *uiCmd에서* 지정한 명령을 검색하고 기본 바로 가기 키를 검색합니다. 그런 다음 메서드는 이 바로 가기 키와 연결된 문자열을 가져와 *str* 매개 변수에 값을 씁니다.

## <a name="ckeyboardmanageriskeyhandled"></a><a name="iskeyhandled"></a>C키보드 관리자::IsKeyHandled

지정된 키가 [CKeyboardManager 클래스에서](../../mfc/reference/ckeyboardmanager-class.md)처리되는지 여부를 결정합니다.

```
static BOOL __stdcall IsKeyHandled(
    WORD nKey,
    BYTE fVirt,
    CFrameWnd* pWndFrame,
    BOOL bIsDefaultFrame);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*nKey*|【인】 확인할 키입니다.|
|*fVirt*|【인】 바로 가기 키의 동작을 지정합니다. 가능한 값 목록은 [ACCEL 구조를](/windows/win32/api/winuser/ns-winuser-accel)참조하십시오.|
|*pWnd프레임*|【인】 프레임 창입니다. 이 메서드는 바로 가기 키가 이 프레임에서 처리되는지 여부를 결정합니다.|
|*비스디폴디프레임*|【인】 *pWndFrame이* 기본 프레임 창인지 여부를 나타내는 부울 매개 변수입니다.|

### <a name="return-value"></a>Return Value

바로 가기 키가 처리되는 경우 TRUE입니다. 키가 처리되지 않거나 *pWndFrame이* NULL인 경우 FALSE입니다.

### <a name="remarks"></a>설명

입력 매개 변수는 nKey 및 *fVirt에* 대해 *가속기* 테이블의 항목과 일치해야 *pWndFrame에서*바로 가기 키가 처리되는지 여부를 확인합니다.

## <a name="ckeyboardmanageriskeyprintable"></a><a name="iskeyprintable"></a>C키보드 관리자::키인쇄 가능

문자를 인쇄할 수 있는지 여부를 나타냅니다.

```
static BOOL __stdcall IsKeyPrintable(const UINT nChar);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*Nchar*|【인】 이 메서드가 검사하는 문자입니다.|

### <a name="return-value"></a>Return Value

문자를 인쇄할 수 있는 경우 0이 아닌 경우 0입니다.

### <a name="remarks"></a>설명

[GetKeyboardState에](/windows/win32/api/winuser/nf-winuser-getkeyboardstate) 대 한 호출에 대 한 호출이 실패 하는 경우이 메서드가 실패 합니다.

## <a name="ckeyboardmanagerisshowallaccelerators"></a><a name="isshowallaccelerators"></a>C키보드 매니저::IsShowAllAccelerators

메뉴에 메뉴 명령과 연결된 모든 바로 가기 키가 표시되는지 아니면 기본 바로 가기 키만 표시할지 여부를 나타냅니다.

```
static BOOL IsShowAllAccelerators();
```

### <a name="return-value"></a>Return Value

응용 프로그램이 메뉴 명령에 대한 모든 바로 가기 키를 나열하는 경우 Nonzero; 응용 프로그램에 기본 바로 가기 키만 표시되는 경우 0입니다.

### <a name="remarks"></a>설명

응용 프로그램은 메뉴 모음에 메뉴 명령에 대한 바로 가기 키를 나열합니다. [CKeyboardManager::ShowAllAccelerators](#showallaccelerators) 함수를 사용하여 응용 프로그램이 모든 바로 가기 키또는 기본 바로 가기 키를 나열하는지 여부를 제어합니다.

## <a name="ckeyboardmanagerloadstate"></a><a name="loadstate"></a>C키보드 관리자::로드스테이트

Windows 레지스트리에서 바로 가기 키 테이블을 로드합니다.

```
BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 데이터가 저장되는 `CKeyboardManager` 레지스트리 경로입니다.

*pDefaultFrame*<br/>
【인】 기본 창으로 사용할 프레임 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

상태가 성공적으로 로드된 경우 0이 아닌 경우

### <a name="remarks"></a>설명

*lpszProfileName* 매개 변수가 NULL인 경우 이 메서드는 `CKeyboardManager` 데이터에 대한 기본 레지스트리 위치를 확인합니다. 기본 레지스트리 위치는 [CWinAppEx 클래스에](../../mfc/reference/cwinappex-class.md)의해 지정됩니다. 데이터는 이전에 [CKeyboardManager::SaveState](#savestate)메서드로 작성해야 합니다.

기본 창을 지정하지 않으면 응용 프로그램의 주 프레임 창이 사용됩니다.

## <a name="ckeyboardmanagerresetall"></a><a name="resetall"></a>C키보드 관리자::모두 재설정

응용 프로그램 리소스에서 바로 가기 키 테이블을 다시 로드합니다.

```cpp
void ResetAll();
```

### <a name="remarks"></a>설명

이 함수는 `CKeyboardManager` 인스턴스에 저장된 바로 가기를 지웁힙으로 지웁힙입니다. 그런 다음 응용 프로그램 리소스에서 키보드 관리자의 상태를 다시 로드합니다.

## <a name="ckeyboardmanagersavestate"></a><a name="savestate"></a>C키보드 관리자::저장 상태

바로 가기 키 테이블을 Windows 레지스트리에 저장합니다.

```
BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>매개 변수

*lpszProfileName*<br/>
【인】 상태를 저장하기 위한 `CKeyboardManager` 레지스트리 경로입니다.

*pDefaultFrame*<br/>
【인】 기본 창이 되는 프레임 창에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

키보드 관리자 상태가 성공적으로 저장된 경우 비영또는 0이 면

### <a name="remarks"></a>설명

*lpszProfileName* 매개 변수가 NULL인 경우 `CKeyboardManager` 이 메서드는 [CWinAppEx 클래스에서](../../mfc/reference/cwinappex-class.md)지정한 기본 위치에 상태를 작성합니다. 위치를 지정하는 경우 나중에 [CKeyboardManager::LoadState](#loadstate)메서드를 사용하여 데이터를 로드할 수 있습니다.

기본 창을 지정하지 않으면 기본 프레임 창이 기본 창으로 사용됩니다.

## <a name="ckeyboardmanagershowallaccelerators"></a><a name="showallaccelerators"></a>C키보드 매니저::쇼알아셀러레이터

메뉴 명령과 연결된 모든 바로 가기 키를 표시합니다.

```
static void ShowAllAccelerators(
    BOOL bShowAll = TRUE,
    LPCTSTR lpszDelimiter = _afxDefaultAcceleratorDelimiter);
```

### <a name="parameters"></a>매개 변수

*bShowAll*<br/>
【인】 TRUE이면 모든 바로 가기 키가 표시됩니다. FALSE인 경우 첫 번째 바로 가기 키만 표시됩니다.

*lpszDelimiter*<br/>
【인】 바로 가기 키 사이에 삽입할 문자열입니다. 이 구분 기호는 하나의 바로 가기 키만 표시 하는 경우 영향을 주지 않습니다.

### <a name="remarks"></a>설명

기본적으로 명령에 연결된 바로 가기 키가 두 개 이상 있는 경우 첫 번째 바로 가기 키만 표시됩니다. 이 기능을 사용하면 모든 명령과 연결된 모든 바로 가기 키를 나열할 수 있습니다.

바로 가기 키는 메뉴 모음의 명령 옆에 나열됩니다. 모든 바로 가기 키가 표시 되면 *lpszDelimiter에서* 제공 하는 문자열 개별 바로 가기 키를 분리 합니다.

## <a name="ckeyboardmanagertranslatechartoupper"></a><a name="translatechartoupper"></a>C키보드 관리자::번역차토어퍼

문자를 상위 레지스터로 변환합니다.

```
static UINT TranslateCharToUpper(const UINT nChar);
```

### <a name="parameters"></a>매개 변수

*Nchar*<br/>
【인】 변환할 문자입니다.

### <a name="return-value"></a>Return Value

입력 매개 변수의 상위 레지스터인 문자입니다.

## <a name="ckeyboardmanagerupdateacceltable"></a><a name="updateacceltable"></a>C 키보드 관리자::업데이트Acceltable

바로 가기 키 테이블을 새 바로 가기 키 테이블로 업데이트합니다.

```
BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    LPACCEL lpAccel,
    int nSize,
    CFrameWnd* pDefaultFrame = NULL);

BOOL UpdateAccelTable(
    CMultiDocTemplate* pTemplate,
    HACCEL hAccelNew,
    CFrameWnd* pDefaultFrame = NULL);
```

### <a name="parameters"></a>매개 변수

*템플릿*<br/>
【인】 문서 템플릿에 대한 포인터입니다.

*lpAccel*<br/>
【인】 새 바로 가기 키에 대한 포인터입니다.

*nSize*<br/>
【인】 새 바로 가기 테이블의 크기입니다.

*pDefaultFrame*<br/>
【인】 기본 프레임 창에 대한 포인터입니다.

*하셀뉴*<br/>
【인】 새 바로 가기 테이블에 대한 핸들입니다.

### <a name="return-value"></a>Return Value

메서드가 성공하면 0이 아닙니다. 그렇지 않으면 0.

### <a name="remarks"></a>설명

이 함수를 사용하여 기존 바로 가기 테이블을 여러 프레임 창 개체에 대한 새 바로 가기 키로 바꿉습니다. 이 함수는 지정된 문서 템플릿에 연결된 모든 프레임 창 개체에 대한 액세스를 얻기 위한 매개 변수로 문서 템플릿을 수신합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx 클래스](../../mfc/reference/cwinappex-class.md)<br/>
[CWinAppEx::이니트 키보드 관리자](../../mfc/reference/cwinappex-class.md#initkeyboardmanager)<br/>
[키보드 및 마우스 사용자 지정](../../mfc/keyboard-and-mouse-customization.md)
