---
title: CTaskDialog Class
ms.date: 11/19/2018
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
helpviewer_keywords:
- CTaskDialog [MFC], CTaskDialog
- CTaskDialog [MFC], AddCommandControl
- CTaskDialog [MFC], AddRadioButton
- CTaskDialog [MFC], ClickCommandControl
- CTaskDialog [MFC], ClickRadioButton
- CTaskDialog [MFC], DoModal
- CTaskDialog [MFC], GetCommonButtonCount
- CTaskDialog [MFC], GetCommonButtonFlag
- CTaskDialog [MFC], GetCommonButtonId
- CTaskDialog [MFC], GetOptions
- CTaskDialog [MFC], GetSelectedCommandControlID
- CTaskDialog [MFC], GetSelectedRadioButtonID
- CTaskDialog [MFC], GetVerificationCheckboxState
- CTaskDialog [MFC], IsCommandControlEnabled
- CTaskDialog [MFC], IsRadioButtonEnabled
- CTaskDialog [MFC], IsSupported
- CTaskDialog [MFC], LoadCommandControls
- CTaskDialog [MFC], LoadRadioButtons
- CTaskDialog [MFC], NavigateTo
- CTaskDialog [MFC], OnCommandControlClick
- CTaskDialog [MFC], OnCreate
- CTaskDialog [MFC], OnDestroy
- CTaskDialog [MFC], OnExpandButtonClick
- CTaskDialog [MFC], OnHelp
- CTaskDialog [MFC], OnHyperlinkClick
- CTaskDialog [MFC], OnInit
- CTaskDialog [MFC], OnNavigatePage
- CTaskDialog [MFC], OnRadioButtonClick
- CTaskDialog [MFC], OnTimer
- CTaskDialog [MFC], OnVerificationCheckboxClick
- CTaskDialog [MFC], RemoveAllCommandControls
- CTaskDialog [MFC], RemoveAllRadioButtons
- CTaskDialog [MFC], SetCommandControlOptions
- CTaskDialog [MFC], SetCommonButtonOptions
- CTaskDialog [MFC], SetCommonButtons
- CTaskDialog [MFC], SetContent
- CTaskDialog [MFC], SetDefaultCommandControl
- CTaskDialog [MFC], SetDefaultRadioButton
- CTaskDialog [MFC], SetDialogWidth
- CTaskDialog [MFC], SetExpansionArea
- CTaskDialog [MFC], SetFooterIcon
- CTaskDialog [MFC], SetFooterText
- CTaskDialog [MFC], SetMainIcon
- CTaskDialog [MFC], SetMainInstruction
- CTaskDialog [MFC], SetOptions
- CTaskDialog [MFC], SetProgressBarMarquee
- CTaskDialog [MFC], SetProgressBarPosition
- CTaskDialog [MFC], SetProgressBarRange
- CTaskDialog [MFC], SetProgressBarState
- CTaskDialog [MFC], SetRadioButtonOptions
- CTaskDialog [MFC], SetVerificationCheckbox
- CTaskDialog [MFC], SetVerificationCheckboxText
- CTaskDialog [MFC], SetWindowTitle
- CTaskDialog [MFC], ShowDialog
- CTaskDialog [MFC], TaskDialogCallback
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
ms.openlocfilehash: 79f52d275d360cf8447b8977b8196ea5f95eacd8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752291"
---
# <a name="ctaskdialog-class"></a>CTaskDialog Class

메시지 상자처럼 작동하지만 사용자에게 추가 정보를 표시할 수 있는 팝업 대화 상자입니다. `CTaskDialog` 에는 사용자로부터 정보를 수집하는 기능을 포함합니다.

## <a name="syntax"></a>구문

```
class CTaskDialog : public CObject
```

## <a name="members"></a>멤버

### <a name="constructors"></a>생성자

|||
|-|-|
|[CTaskDialog::CTaskDialog](#ctaskdialog)|`CTaskDialog` 개체를 생성합니다.|

### <a name="methods"></a>메서드

|||
|-|-|
|[CTaskDialog::추가 명령 제어](#addcommandcontrol)|에 명령 단추 컨트롤을 `CTaskDialog`추가합니다.|
|[CTaskDialog::라디오 버튼 추가](#addradiobutton)|`CTaskDialog`에 라디오 단추를 추가합니다.|
|[CTaskDialog::클릭 명령 제어](#clickcommandcontrol)|명령 단추 컨트롤 또는 일반적인 단추를 프로그래밍 방식으로 클릭합니다.|
|[CTaskDialog::클릭라디오 버튼](#clickradiobutton)|프로그래밍 방식으로 라디오 버튼을 클릭합니다.|
|[CTaskDialog::DoModal](#domodal)|`CTaskDialog`를 표시합니다.|
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|사용 가능한 공통 단추 수를 검색합니다.|
|[CTaskDialog::GetCommonButton플래그](#getcommonbuttonflag)|표준 Windows 단추를 클래스와 연결된 공통 `CTaskDialog` 단추 유형으로 변환합니다.|
|[CTaskDialog::GetCommonButtonID](#getcommonbuttonid)|`CTaskDialog` 클래스와 연결된 일반적인 단추 유형 중 하나를 표준 Windows 단추로 변환합니다.|
|[CTaskDialog::Get옵션](#getoptions)|이 에 대한 `CTaskDialog`옵션 플래그를 반환합니다.|
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|선택한 명령 단추 컨트롤을 반환합니다.|
|[CTaskDialog::GetSelected라디오버튼ID](#getselectedradiobuttonid)|선택한 라디오 단추를 반환합니다.|
|[CTaskDialog::GetVerify확인확인란상태](#getverificationcheckboxstate)|확인 확인란의 상태를 검색합니다.|
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|명령 단추 컨트롤 또는 공통 단추를 사용할 수 있는지 여부를 결정합니다.|
|[CTaskDialog::IsRadioButton사용](#isradiobuttonenabled)|라디오 단추를 사용할 수 있는지 여부를 확인합니다.|
|[CTaskDialog::지원됩니다.](#issupported)|응용 프로그램을 실행 중인 컴퓨터가 `CTaskDialog`을 지원하는지 여부를 결정합니다.|
|[CTaskDialog::로드명령컨트롤](#loadcommandcontrols)|문자열 테이블의 데이터를 사용하여 명령 단추 컨트롤을 추가합니다.|
|[CTaskDialog::로드라디오 버튼](#loadradiobuttons)|문자열 테이블의 데이터를 사용하여 라디오 단추를 추가합니다.|
|[CTaskDialog::탐색](#navigateto)|포커스를 다른 `CTaskDialog`로 전송합니다.|
|[CTaskDialog::온명령 제어클릭](#oncommandcontrolclick)|사용자가 명령 단추 컨트롤을 클릭할 때 프레임워크는 이 메서드를 호출합니다.|
|[CTaskDialog::에 만들기](#oncreate)|프레임 워크는 `CTaskDialog`이 메서드를 만듭니다.|
|[CTaskDialog::온Destroy](#ondestroy)|프레임워크는 `CTaskDialog`을 삭제하기 직전에 이 메서드를 호출합니다.|
|[CTask Dialog::확장 단추클릭](#onexpandbuttonclick)|사용자가 확장 단추를 클릭할 때 프레임워크는 이 메서드를 호출합니다.|
|[CTaskDialog::On도움말](#onhelp)|프레임워크는 사용자가 도움을 요청할 때 이 메서드를 호출합니다.|
|[CTaskDialog::온하이퍼링크클릭](#onhyperlinkclick)|사용자가 하이퍼링크를 클릭할 때 프레임워크는 이 메서드를 호출합니다.|
|[CTaskDialog::OnInit](#oninit)|프레임워크는 초기화될 `CTaskDialog` 때 이 메서드를 호출합니다.|
|[CTaskDialog::탐색 페이지](#onnavigatepage)|프레임워크는 사용자가 의 컨트롤과 관련하여 포커스를 이동할 `CTaskDialog`때 이 메서드를 호출합니다.|
|[CTaskDialog::라디오 버튼클릭](#onradiobuttonclick)|사용자가 라디오 단추 컨트롤을 선택할 때 프레임워크는 이 메서드를 호출합니다.|
|[CTaskDialog::온타이머](#ontimer)|프레임워크는 타이머가 만료될 때 이 메서드를 호출합니다.|
|[CTaskDialog::확인 확인란클릭](#onverificationcheckboxclick)|사용자가 확인 확인란을 클릭할 때 프레임워크는 이 메서드를 호출합니다.|
|[CTaskDialog::제거AllCommandControls](#removeallcommandcontrols)|에서 모든 명령 컨트롤을 `CTaskDialog`제거합니다.|
|[CTaskDialog::제거모든라디오 버튼](#removeallradiobuttons)|`CTaskDialog`에서 모든 라디오 단추를 제거합니다.|
|[CTaskDialog::설정 명령 제어 옵션](#setcommandcontroloptions)|에서 명령 단추 컨트롤을 업데이트합니다. `CTaskDialog`|
|[CTaskDialog::공통 단추 옵션 설정](#setcommonbuttonoptions)|사용할 공통 단추의 하위 집합을 업데이트하고 UAC 높이가 필요합니다.|
|[CTaskDialog::일반 단추 설정](#setcommonbuttons)|`CTaskDialog`에 공통 단추를 추가합니다.|
|[CTaskDialog::설정 콘텐츠](#setcontent)|의 내용을 업데이트합니다. `CTaskDialog`|
|[CTaskDialog::설정기본 명령 제어](#setdefaultcommandcontrol)|기본 명령 단추 컨트롤을 지정합니다.|
|[CTask Dialog::설정기본라디오버튼](#setdefaultradiobutton)|기본 라디오 단추를 지정합니다.|
|[CTaskDialog::SetDialog폭](#setdialogwidth)|의 너비를 조정합니다. `CTaskDialog`|
|[CTaskDialog::세트확장영역](#setexpansionarea)|의 확장 영역을 `CTaskDialog`업데이트합니다.|
|[CTaskDialog::SetFooterIcon](#setfootericon)|에 대한 바닥글 `CTaskDialog`아이콘을 업데이트합니다.|
|[CTaskDialog::SetFooterText](#setfootertext)|의 바닥글에 있는 텍스트를 `CTaskDialog`업데이트합니다.|
|[CTaskDialog::SetMainicon](#setmainicon)|의 기본 아이콘을 `CTaskDialog`업데이트합니다.|
|[CTaskDialog::설정기본 지시](#setmaininstruction)|의 기본 지침을 `CTaskDialog`업데이트합니다.|
|[CTaskDialog::설정 옵션](#setoptions)|에 대한 옵션을 `CTaskDialog`구성합니다.|
|[CTask Dialog::설정진행률 바선택 윤곽](#setprogressbarmarquee)|에 대한 선택 윤곽 `CTaskDialog` 막대를 구성하고 대화 상자에 추가합니다.|
|[CTask Dialog::설정진행바 포지션](#setprogressbarposition)|진행률 표시줄의 위치를 조정합니다.|
|[CTask Dialog::설정진행률바레인지](#setprogressbarrange)|진행률 표시줄의 범위를 조정합니다.|
|[CTaskDialog::설정진행률바스테이트](#setprogressbarstate)|진행률 표시줄의 상태를 설정하고 `CTaskDialog`에 표시합니다.|
|[CTaskDialog::설정라디오 단추옵션](#setradiobuttonoptions)|라디오 단추를 활성화하거나 사용하지 않도록 설정합니다.|
|[CTaskDialog::확인 확인란](#setverificationcheckbox)|확인 확인란의 선택된 상태를 설정합니다.|
|[CTask Dialog::설정 확인확인백](#setverificationcheckboxtext)|확인 확인란의 오른쪽에 텍스트를 설정합니다.|
|[CTaskDialog::세트윈도우타이틀](#setwindowtitle)|의 제목을 `CTaskDialog`설정합니다.|
|[CTaskDialog::쇼디아로그](#showdialog)|`CTaskDialog`을 만들고 표시합니다.|
|[CTaskDialog::작업디아로그콜백](#taskdialogcallback)|프레임워크는 다양한 Windows 메시지에 대한 응답으로 이를 호출합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|`m_aButtons`|에 대한 명령 단추 `CTaskDialog`컨트롤의 배열입니다.|
|`m_aRadioButtons`|에 대한 라디오 단추 `CTaskDialog`컨트롤의 배열입니다.|
|`m_bVerified`|`TRUE`확인 확인란이 선택되어 있음을 나타냅니다. `FALSE` 을 나타내면 그렇지 않음을 나타냅니다.|
|`m_footerIcon`|의 바닥글에 있는 `CTaskDialog`아이콘입니다.|
|`m_hWnd`|의 창에 대한 `CTaskDialog`핸들입니다.|
|`m_mainIcon`|의 주요 아이콘입니다. `CTaskDialog`|
|`m_nButtonDisabled`|사용할 수 없는 공통 단추를 나타내는 마스크입니다.|
|`m_nButtonElevation`|UAC 상승이 필요한 공통 단추를 나타내는 마스크입니다.|
|`m_nButtonId`|선택한 명령 단추 컨트롤의 ID입니다.|
|`m_nCommonButton`|`CTaskDialog`에 표시되는 공통 단추를 나타내는 마스크입니다.|
|`m_nDefaultCommandControl`|표시 될 때 선택 되는 명령 `CTaskDialog` 단추 컨트롤의 ID입니다.|
|`m_nDefaultRadioButton`|표시 될 때 선택 되는 라디오 `CTaskDialog` 단추 컨트롤의 ID입니다.|
|`m_nFlags`|에 대한 옵션을 나타내는 `CTaskDialog`마스크입니다.|
|`m_nProgressPos`|진행률 표시줄의 현재 위치입니다.  이 값은 `m_nProgressRangeMin`와 `m_nProgressRangeMax` 사이의 값이어야 합니다.|
|`m_nProgressRangeMax`|진행률 표시줄의 최대값입니다.|
|`m_nProgressRangeMin`|진행률 표시줄의 최소값입니다.|
|`m_nProgressState`|진행률 표시줄의 상태입니다. 자세한 내용은 [CTaskDialog::SetProgressBarState](#setprogressbarstate)를 참조하십시오.|
|`m_nRadioId`|선택한 라디오 단추 컨트롤의 ID입니다.|
|`m_nWidth`|`CTaskDialog`의 너비(픽셀)입니다.|
|`m_strCollapse`|확장 정보가 `CTaskDialog` 숨겨져 있을 때 확장 상자의 오른쪽에 표시되는 문자열입니다.|
|`m_strContent`|의 내용 문자열입니다. `CTaskDialog`|
|`m_strExpand`|확장 정보가 `CTaskDialog` 표시될 때 확장 상자의 오른쪽에 표시되는 문자열입니다.|
|`m_strFooter`|의 바닥글입니다. `CTaskDialog`|
|`m_strInformation`|에 대한 확장된 정보입니다. `CTaskDialog`|
|`m_strMainInstruction`|의 주요 지침입니다. `CTaskDialog`|
|`m_strTitle`|`CTaskDialog`의 제목입니다.|
|`m_strVerification`|확인 확인란의 `CTaskDialog` 오른쪽에 표시되는 문자열입니다.|

## <a name="remarks"></a>설명

클래스는 `CTaskDialog` 표준 Windows 메시지 상자를 대체하며 사용자로부터 정보를 수집하는 새 컨트롤과 같은 추가 기능이 있습니다. 이 클래스는 Visual Studio 2010 이후의 MFC 라이브러리에 있습니다. Windows `CTaskDialog` Vista부터 사용할 수 있습니다. 이전 버전의 Windows는 `CTaskDialog` 개체를 표시할 수 없습니다. 런타임시 현재 사용자가 작업 대화 상자를 표시할 수 있는지 여부를 결정하는 데 사용합니다. `CTaskDialog::IsSupported` 표준 Windows 메시지 상자는 계속 지원됩니다.

유니코드 `CTaskDialog` 라이브러리를 사용하여 응용 프로그램을 빌드할 때만 사용할 수 있습니다.

두 `CTaskDialog` 개의 서로 다른 생성자가 있습니다. 하나의 생성자가 두 개의 명령 단추와 최대 6개의 일반 단추 컨트롤을 지정할 수 있습니다. `CTaskDialog`을 만든 후 명령 단추를 더 추가할 수 있습니다. 두 번째 생성자는 명령 단추를 지원하지 않지만 일반 단추 컨트롤을 무제한으로 추가할 수 있습니다. 생성자에 대한 자세한 내용은 [CTaskDialog::CTaskDialog](#ctaskdialog)를 참조하십시오.

다음 이미지는 일부 `CTaskDialog` 컨트롤의 위치를 설명하는 샘플을 보여 줍니다.

![CTaskDialog의 예](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialog의 예") <br/>
CTaskDialog 샘플

## <a name="requirements"></a>요구 사항

**최소 필수 운영 체제:** 윈도우 비스타

**헤더:** afxtaskdialog.h

## <a name="ctaskdialogaddcommandcontrol"></a><a name="addcommandcontrol"></a>CTaskDialog::추가 명령 제어

에 새 명령 단추 `CTaskDialog`컨트롤을 추가합니다.

```cpp
void AddCommandControl(
    int nCommandControlID,
    const CString& strCaption,
    BOOL bEnabled = TRUE,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>매개 변수

*n명령제어ID*<br/>
【인】 명령 제어 식별 번호입니다.

*스트캡션*<br/>
【인】 사용자에게 `CTaskDialog` 표시되는 문자열입니다. 이 문자열을 사용하여 명령의 용도를 설명합니다.

*bEnabled*<br/>
【인】 새 단추를 사용 하거나 사용 하지 않도록 설정 되어 있는지 나타내는 부울 매개 변수입니다.

*b필요고도*<br/>
【인】 명령에 표고가 필요한지 여부를 나타내는 부울 매개변수입니다.

### <a name="remarks"></a>설명

명령 `CTaskDialog Class` 버튼 컨트롤의 무제한 수를 표시 할 수 있습니다. 그러나 명령 `CTaskDialog` 단추 컨트롤을 표시 하는 경우 최대 6 개의 단추를 표시할 수 있습니다. 명령 `CTaskDialog` 단추 컨트롤이 없는 경우 무제한 의 단추를 표시할 수 있습니다.

사용자가 명령 단추 컨트롤을 선택하면 `CTaskDialog` 닫힙습니다. 응용 프로그램에서 [CTaskDialog::DoModal을](#domodal)사용하여 대화 상자를 `DoModal` 표시하는 경우 선택한 명령 단추 컨트롤의 *nCommandControlID를* 반환합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogaddradiobutton"></a><a name="addradiobutton"></a>CTaskDialog::라디오 버튼 추가

`CTaskDialog`에 라디오 단추를 추가합니다.

```cpp
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,
    const CString& strCaption,
    BOOL bEnabled = TRUE);
```

### <a name="parameters"></a>매개 변수

*n라디오버튼ID*<br/>
【인】 라디오 단추의 식별 번호입니다.

*스트캡션*<br/>
【인】 라디오 단추 `CTaskDialog` 옆에 표시되는 문자열입니다.

*bEnabled*<br/>
【인】 라디오 버튼이 활성화되어 있는지 여부를 나타내는 부울 매개 변수입니다.

### <a name="remarks"></a>설명

[CTaskDialog 클래스의](../../mfc/reference/ctaskdialog-class.md) 라디오 단추를 사용하면 사용자로부터 정보를 수집할 수 있습니다. [CTaskDialog 기능::GetSelectedRadioButtonID를](#getselectedradiobuttonid) 사용하여 선택한 라디오 단추를 결정합니다.

`CTaskDialog` *nRadioButtonID* 매개 변수가 각 라디오 단추에 대해 고유해야 하는 것은 아닙니다. 그러나 각 라디오 단추에 대해 고유한 식별자를 사용하지 않으면 예기치 않은 동작이 발생할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogclickcommandcontrol"></a><a name="clickcommandcontrol"></a>CTaskDialog::클릭 명령 제어

명령 단추 컨트롤 또는 일반적인 단추를 프로그래밍 방식으로 클릭합니다.

```
protected:
void ClickCommandControl(int nCommandControlID) const;
```

### <a name="parameters"></a>매개 변수

*n명령제어ID*<br/>
【인】 클릭할 컨트롤의 명령 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 TDM_CLICK_BUTTON windows 메시지를 생성 합니다.

## <a name="ctaskdialogclickradiobutton"></a><a name="clickradiobutton"></a>CTaskDialog::클릭라디오 버튼

프로그래밍 방식으로 라디오 버튼을 클릭합니다.

```
protected:
void ClickRadioButton(int nRadioButtonID) const;
```

### <a name="parameters"></a>매개 변수

*n라디오버튼ID*<br/>
【인】 클릭할 라디오 버튼의 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 TDM_CLICK_RADIO_BUTTON windows 메시지를 생성 합니다.

## <a name="ctaskdialogctaskdialog"></a><a name="ctaskdialog"></a>CTaskDialog::CTaskDialog

[CTaskDialog 클래스의](../../mfc/reference/ctaskdialog-class.md)인스턴스를 만듭니다.

```
CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));

CTaskDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>매개 변수

*스트콘텐츠*<br/>
【인】 의 내용에 사용할 문자열입니다. `CTaskDialog`

*스트메인 지시*<br/>
【인】 의 주요 지침입니다. `CTaskDialog`

*스트제목*<br/>
【인】 의 제목입니다. `CTaskDialog`

*n공통 단추*<br/>
【인】 에 추가할 공통 단추의 마스크입니다. `CTaskDialog`

*nTaskDialog옵션*<br/>
【인】 에 사용할 옵션 집합입니다. `CTaskDialog`

*스트풋터*<br/>
【인】 바닥글로서 사용할 끈.

*nID명령컨트롤우선*<br/>
【인】 첫 번째 명령의 문자열 ID입니다.

*니드커맨드컨트롤스마지막*<br/>
【인】 마지막 명령의 문자열 ID입니다.

### <a name="remarks"></a>설명

응용 프로그램에 a를 `CTaskDialog` 추가할 수 있는 방법에는 두 가지가 있습니다. 첫 번째 방법은 생성자 중 하나를 사용하여 `CTaskDialog` [CTaskDialog::DoModal을](#domodal)사용하여 생성자를 만들고 표시하는 것입니다. 두 번째 방법은 정적 함수 [CTaskDialog::ShowDialog를](#showdialog)사용 하 `CTaskDialog` 여 `CTaskDialog` 명시적으로 개체를 만들지 않고 표시 할 수 있습니다.

두 번째 생성자는 응용 프로그램의 리소스 파일의 데이터를 사용하여 명령 단추 컨트롤을 만듭니다. 리소스 파일의 문자열 테이블에는 연결된 문자열 이있는 여러 문자열이 있습니다. 이 메서드는 *nIDCommandControlsFirst* 와 *nCommandControlsLast,* 포함 사이의 문자열 테이블의 각 유효한 항목에 대한 명령 단추 컨트롤을 추가합니다. 이러한 명령 단추 컨트롤의 경우 문자열 테이블의 문자열은 컨트롤의 캡션이고 문자열 ID는 컨트롤의 ID입니다.

유효한 옵션 목록은 [CTaskDialog::Set옵션을](#setoptions) 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogdomodal"></a><a name="domodal"></a>CTaskDialog::DoModal

를 `CTaskDialog` 표시하고 모달합니다.

```
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```

### <a name="parameters"></a>매개 변수

*h부모*<br/>
【인】 의 부모 창입니다. `CTaskDialog`

### <a name="return-value"></a>Return Value

사용자가 선택한 값에 해당하는 정수입니다.

### <a name="remarks"></a>설명

[CTaskDialog의](../../mfc/reference/ctaskdialog-class.md)이 인스턴스를 표시합니다. 그런 다음 응용 프로그램은 사용자가 대화 상자를 닫을 때까지 기다립니다.

사용자가 `CTaskDialog` 공통 단추, 명령 링크 컨트롤을 선택하거나 `CTaskDialog`을 닫을 때 닫힙니다. 반환 값은 사용자가 대화 상자를 닫은 방법을 나타내는 식별자입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetcommonbuttoncount"></a><a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButtonCount

공통 단추 수를 검색합니다.

```
int GetCommonButtonCount() const;
```

### <a name="return-value"></a>Return Value

사용 가능한 공통 단추 수입니다.

### <a name="remarks"></a>설명

일반적인 단추는 [CTaskDialog::CTaskDialog](#ctaskdialog)에 제공하는 기본 단추입니다. [CTaskDialog 클래스는](../../mfc/reference/ctaskdialog-class.md) 대화 상자 아래쪽에 있는 단추를 표시합니다.

단추의 나열된 목록은 CommCtrl.h에서 제공됩니다.

## <a name="ctaskdialoggetcommonbuttonflag"></a><a name="getcommonbuttonflag"></a>CTaskDialog::GetCommonButton플래그

표준 Windows 단추를 [CTaskDialog 클래스와](../../mfc/reference/ctaskdialog-class.md)연결된 공통 단추 유형으로 변환합니다.

```
int GetCommonButtonFlag(int nButtonId) const;
```

### <a name="parameters"></a>매개 변수

*nButtonId*<br/>
【인】 표준 Windows 단추 값입니다.

### <a name="return-value"></a>Return Value

해당 `CTaskDialog` 공통 단추의 값입니다. 해당 공통 단추가 없는 경우 이 메서드는 0을 반환합니다.

## <a name="ctaskdialoggetcommonbuttonid"></a><a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonID

[CTaskDialog 클래스와](../../mfc/reference/ctaskdialog-class.md) 연결된 일반적인 단추 유형 중 하나를 표준 Windows 단추로 변환합니다.

```
int GetCommonButtonId(int nFlag);
```

### <a name="parameters"></a>매개 변수

*n 플래그*<br/>
【인】 클래스와 연결된 공통 `CTaskDialog` 단추 유형입니다.

### <a name="return-value"></a>Return Value

해당 표준 Windows 단추의 값입니다. 해당 Windows 단추가 없는 경우 메서드는 0을 반환합니다.

## <a name="ctaskdialoggetoptions"></a><a name="getoptions"></a>CTaskDialog::Get옵션

이 에 대한 `CTaskDialog`옵션 플래그를 반환합니다.

```
int GetOptions() const;
```

### <a name="return-value"></a>Return Value

의 플래그입니다. `CTaskDialog`

### <a name="remarks"></a>설명

[CTaskDialog 클래스에서](../../mfc/reference/ctaskdialog-class.md)사용할 수 있는 옵션에 대한 자세한 내용은 [CTaskDialog::SetOptions](#setoptions)를 참조하십시오.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialoggetselectedcommandcontrolid"></a><a name="getselectedcommandcontrolid"></a>CTaskDialog::GetSelectedCommandControlID

선택한 명령 단추 컨트롤을 반환합니다.

```
int GetSelectedCommandControlID() const;
```

### <a name="return-value"></a>Return Value

현재 선택한 명령 단추 컨트롤의 ID입니다.

### <a name="remarks"></a>설명

사용자가 선택한 명령 단추의 ID를 검색하기 위해 이 메서드를 사용할 필요가 없습니다. 해당 ID는 [CTaskDialog::DoModal](#domodal) 또는 [CTaskDialog::ShowDialog](#showdialog).

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialoggetselectedradiobuttonid"></a><a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelected라디오버튼ID

선택한 라디오 단추를 반환합니다.

```
int GetSelectedRadioButtonID() const;
```

### <a name="return-value"></a>Return Value

선택한 라디오 버튼의 ID입니다.

### <a name="remarks"></a>설명

사용자가 대화 상자를 닫은 후 선택한 라디오 단추를 검색할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialoggetverificationcheckboxstate"></a><a name="getverificationcheckboxstate"></a>CTaskDialog::GetVerify확인확인란상태

확인 확인란의 상태를 검색합니다.

```
BOOL GetVerificationCheckboxState() const;
```

### <a name="return-value"></a>Return Value

TRUE 확인란을 선택하면 FALSE가 아닌 경우.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogiscommandcontrolenabled"></a><a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled

명령 단추 컨트롤 또는 단추를 사용할 수 있는지 여부를 결정합니다.

```
BOOL IsCommandControlEnabled(int nCommandControlID) const;
```

### <a name="parameters"></a>매개 변수

*n명령제어ID*<br/>
【인】 테스트할 명령 단추 컨트롤 또는 단추의 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 컨트롤을 사용 하는 경우, FALSE 그렇지 않은 경우.

### <a name="remarks"></a>설명

이 메서드를 사용하여 명령 단추 컨트롤과 `CTaskDialog` Class*의 공통 단추의 가용성을 확인할 수 있습니다.

*nCommandControlID가* 공통 `CTaskDialog` 단추 또는 명령 단추 컨트롤에 대한 유효한 식별자가 아닌 경우 이 메서드는 예외를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogisradiobuttonenabled"></a><a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButton사용

라디오 단추를 사용할 수 있는지 여부를 확인합니다.

```
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;
```

### <a name="parameters"></a>매개 변수

*n라디오버튼ID*<br/>
【인】 테스트할 라디오 버튼의 ID입니다.

### <a name="return-value"></a>Return Value

TRUE 라디오 버튼이 활성화되어 있으면 FALSE가 아닌 경우 FALSE입니다.

### <a name="remarks"></a>설명

*nRadioButtonID가* 라디오 단추에 대한 유효한 식별자가 아닌 경우 이 메서드는 예외를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogissupported"></a><a name="issupported"></a>CTaskDialog::지원됩니다.

응용 프로그램을 실행 중인 컴퓨터가 `CTaskDialog`을 지원하는지 여부를 결정합니다.

```
static BOOL IsSupported();
```

### <a name="return-value"></a>Return Value

TRUE 컴퓨터가 다음을 `CTaskDialog`지원하는 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 함수를 사용하여 런타임시 응용 프로그램을 실행하는 컴퓨터가 `CTaskDialog` 클래스를 지원하는지 확인합니다. 컴퓨터가 `CTaskDialog`을 지원하지 않는 경우 사용자에게 정보를 전달하는 다른 방법을 제공해야 합니다. 클래스를 지원하지 않는 컴퓨터에서 를 `CTaskDialog` 사용하려고 하면 응용 프로그램이 충돌합니다. `CTaskDialog`

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogloadcommandcontrols"></a><a name="loadcommandcontrols"></a>CTaskDialog::로드명령컨트롤

문자열 테이블의 데이터를 사용하여 명령 단추 컨트롤을 추가합니다.

```cpp
void LoadCommandControls(
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast);
```

### <a name="parameters"></a>매개 변수

*nID명령컨트롤우선*<br/>
【인】 첫 번째 명령의 문자열 ID입니다.

*니드커맨드컨트롤스마지막*<br/>
【인】 마지막 명령의 문자열 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일의 문자열 테이블에는 연결된 문자열 이있는 여러 문자열이 있습니다. 이 메서드를 사용하여 추가된 새 명령 단추 컨트롤은 컨트롤의 캡션에 대한 문자열과 컨트롤ID의 문자열 ID를 사용합니다. 선택한 문자열의 범위는 *nIDCommandControlsFirst* 및 *nCommandControlsLast,* 포함에 의해 제공됩니다. 범위에 빈 항목이 있는 경우 메서드는 해당 항목에 대한 명령 단추 컨트롤을 추가하지 않습니다.

기본적으로 새 명령 단추 컨트롤이 활성화되어 있으며 고도가 필요하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogloadradiobuttons"></a><a name="loadradiobuttons"></a>CTaskDialog::로드라디오 버튼

문자열 테이블의 데이터를 사용하여 라디오 단추 컨트롤을 추가합니다.

```cpp
void LoadRadioButtons(
    int nIDRadioButtonsFirst,
    int nIDRadioButtonsLast);
```

### <a name="parameters"></a>매개 변수

*니디드라디오버튼첫번째*<br/>
【인】 첫 번째 라디오 단추의 문자열 ID입니다.

*니디드라디오버튼지속*<br/>
【인】 마지막 라디오 단추의 문자열 ID입니다.

### <a name="remarks"></a>설명

이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 라디오 단추를 만듭니다. 리소스 파일의 문자열 테이블에는 연결된 문자열 이있는 여러 문자열이 있습니다. 이 메서드를 사용하여 추가된 새 라디오 단추는 라디오 단추의 캡션에 대한 문자열과 라디오 단추의 ID에 대한 문자열 ID를 사용합니다. 선택한 문자열의 범위는 *nIDRadioButtons첫* 번째 및 *nRadioButtonsLast,* 포함에 의해 제공됩니다. 범위에 빈 항목이 있는 경우 메서드는 해당 항목에 대한 라디오 단추를 추가하지 않습니다.

기본적으로 새 라디오 버튼이 활성화됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialognavigateto"></a><a name="navigateto"></a>CTaskDialog::탐색

포커스를 다른 `CTaskDialog`로 전송합니다.

```
protected:
void NavigateTo(CTaskDialog& oTaskDialog) const;
```

### <a name="parameters"></a>매개 변수

*oTaskDialog*<br/>
【인】 포커스를 받는 `CTaskDialog` 것입니다.

### <a name="remarks"></a>설명

이 메서드는 `CTaskDialog` *oTaskDialog를*표시할 때 현재를 숨깁니다. *oTaskDialog는* 현재와 `CTaskDialog`동일한 위치에 표시됩니다.

## <a name="ctaskdialogoncommandcontrolclick"></a><a name="oncommandcontrolclick"></a>CTaskDialog::온명령 제어클릭

사용자가 명령 단추 컨트롤을 클릭할 때 프레임워크는 이 메서드를 호출합니다.

```
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```

### <a name="parameters"></a>매개 변수

*n명령제어ID*<br/>
【인】 사용자가 선택한 명령 단추 컨트롤의 ID입니다.

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogoncreate"></a><a name="oncreate"></a>CTaskDialog::에 만들기

프레임 워크는 `CTaskDialog`이 메서드를 만듭니다.

```
virtual HRESULT OnCreate();
```

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogondestroy"></a><a name="ondestroy"></a>CTaskDialog::온Destroy

프레임워크는 `CTaskDialog`을 삭제하기 직전에 이 메서드를 호출합니다.

```
virtual HRESULT OnDestroy();
```

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogonexpandbuttonclick"></a><a name="onexpandbuttonclick"></a>CTask Dialog::확장 단추클릭

사용자가 확장 단추를 클릭할 때 프레임워크는 이 메서드를 호출합니다.

```
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```

### <a name="parameters"></a>매개 변수

*b확장*<br/>
【인】 영하지 않은 값은 추가 정보가 표시되고 있음을 나타냅니다. 0은 추가 정보가 숨겨져 있음을 나타냅니다.

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogonhelp"></a><a name="onhelp"></a>CTaskDialog::On도움말

프레임워크는 사용자가 도움을 요청할 때 이 메서드를 호출합니다.

```
virtual HRESULT OnHelp();
```

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogonhyperlinkclick"></a><a name="onhyperlinkclick"></a>CTaskDialog::온하이퍼링크클릭

사용자가 하이퍼링크를 클릭할 때 프레임워크는 이 메서드를 호출합니다.

```
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```

### <a name="parameters"></a>매개 변수

*스트라이프 (strHref)*<br/>
【인】 하이퍼링크를 나타내는 문자열입니다.

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

이 메서드는 S_OK 반환하기 전에 [ShellExecute를](/windows/win32/api/shellapi/nf-shellapi-shellexecutew) 호출합니다.

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogoninit"></a><a name="oninit"></a>CTaskDialog::OnInit

프레임워크는 초기화될 `CTaskDialog` 때 이 메서드를 호출합니다.

```
virtual HRESULT OnInit();
```

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogonnavigatepage"></a><a name="onnavigatepage"></a>CTaskDialog::탐색 페이지

프레임워크는 [CTaskDialog::NavigateTo](#navigateto) 메서드에 대한 응답으로 이 메서드를 호출합니다.

```
virtual HRESULT OnNavigatePage();
```

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogonradiobuttonclick"></a><a name="onradiobuttonclick"></a>CTaskDialog::라디오 버튼클릭

사용자가 라디오 단추 컨트롤을 선택할 때 프레임워크는 이 메서드를 호출합니다.

```
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```

### <a name="parameters"></a>매개 변수

*n라디오버튼ID*<br/>
【인】 사용자가 클릭한 라디오 단추 컨트롤의 ID입니다.

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogontimer"></a><a name="ontimer"></a>CTaskDialog::온타이머

프레임워크는 타이머가 만료될 때 이 메서드를 호출합니다.

```
virtual HRESULT OnTimer(long lTime);
```

### <a name="parameters"></a>매개 변수

*l시간 (1)*<br/>
【인】 타이머가 `CTaskDialog` 생성되었지만 타이머가 재설정된 이후의 시간(밀리초)입니다.

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogonverificationcheckboxclick"></a><a name="onverificationcheckboxclick"></a>CTaskDialog::확인 확인란클릭

사용자가 확인 확인란을 클릭할 때 프레임워크는 이 메서드를 호출합니다.

```
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```

### <a name="parameters"></a>매개 변수

*b 확인됨*<br/>
【인】 TRUE는 확인 확인란이 선택되어 있음을 나타냅니다. FALSE는 그렇지 않음을 나타냅니다.

### <a name="return-value"></a>Return Value

기본 구현은 S_OK 반환합니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 동작을 구현합니다.

## <a name="ctaskdialogremoveallcommandcontrols"></a><a name="removeallcommandcontrols"></a>CTaskDialog::제거AllCommandControls

에서 모든 명령 단추 컨트롤을 `CTaskDialog`제거합니다.

```cpp
void RemoveAllCommandControls();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogremoveallradiobuttons"></a><a name="removeallradiobuttons"></a>CTaskDialog::제거모든라디오 버튼

`CTaskDialog`에서 모든 라디오 단추를 제거합니다.

```cpp
void RemoveAllRadioButtons();
```

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetcommandcontroloptions"></a><a name="setcommandcontroloptions"></a>CTaskDialog::설정 명령 제어 옵션

에서 명령 단추 컨트롤을 업데이트합니다. `CTaskDialog`

```cpp
void SetCommandControlOptions(
    int nCommandControlID,
    BOOL bEnabled,
    BOOL bRequiresElevation = FALSE);
```

### <a name="parameters"></a>매개 변수

*n명령제어ID*<br/>
【인】 업데이트할 명령 컨트롤의 ID입니다.

*bEnabled*<br/>
【인】 지정된 명령 단추 컨트롤이 활성화되어 있거나 비활성화되어 있는지 를 나타내는 부울 매개 변수입니다.

*b필요고도*<br/>
【인】 지정된 명령 단추 컨트롤에 표고가 필요한지 나타내는 부울 매개변수입니다.

### <a name="remarks"></a>설명

이 메서드를 사용 하 여 명령 단추 컨트롤을 사용 하는 `CTaskDialog` 지 또는 클래스에 추가 된 후 고도 필요 여부를 변경 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetcommonbuttonoptions"></a><a name="setcommonbuttonoptions"></a>CTaskDialog::공통 단추 옵션 설정

사용할 공통 단추의 하위 집합을 업데이트하고 UAC 높이를 요구합니다.

```cpp
void SetCommonButtonOptions(
    int nDisabledButtonMask,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>매개 변수

*n 비활성화 단추 마스크*<br/>
【인】 사용하지 않도록 설정할 공통 단추에 대한 마스크입니다.

*nelevationButton마스크*<br/>
【인】 고도가 필요한 공통 단추에 대한 마스크입니다.

### <a name="remarks"></a>설명

생성자 [CTaskDialog:::CTaskDialog](#ctaskdialog) 및 [CTaskDialog::SetCommonButton을](#setcommonbuttons)사용하여 [CTaskDialog 클래스의](../../mfc/reference/ctaskdialog-class.md) 인스턴스에서 사용할 수 있는 공통 단추를 설정할 수 있습니다. `CTaskDialog::SetCommonButtonOptions`는 새 공통 단추 추가를 지원하지 않습니다.

이 메서드를 사용 하 여 사용 하지 않도록 설정 하거나이 `CTaskDialog`에 사용할 수 없는 공통 단추를 상승 하는 경우이 메서드는 [ENSURE](diagnostic-services.md#ensure) 매크로를 사용 하 여 예외를 throw 합니다.

이 메서드를 사용하면 이전에 사용하지 `CTaskDialog` 않도록 설정한 경우에도 *nDisabledButtonMask에*없는 단추를 사용할 수 있습니다. 이 메서드는 고도를 비슷한 방식으로 처리합니다: 공통 단추를 사용할 수 있지만 *nElevationButtonMask에*포함되지 않은 경우 공통 단추를 입면이 필요하지 않은 것으로 기록합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcommonbuttons"></a><a name="setcommonbuttons"></a>CTaskDialog::일반 단추 설정

`CTaskDialog`에 공통 단추를 추가합니다.

```cpp
void SetCommonButtons(
    int nButtonMask,
    int nDisabledButtonMask = 0,
    int nElevationButtonMask = 0);
```

### <a name="parameters"></a>매개 변수

*n버튼 마스크*<br/>
【인】 에 추가할 단추의 마스크입니다. `CTaskDialog`

*n 비활성화 단추 마스크*<br/>
【인】 비활성화할 단추의 마스크입니다.

*nelevationButton마스크*<br/>
【인】 입면이 필요한 단추의 마스크입니다.

### <a name="remarks"></a>설명

클래스의 이 인스턴스에 대한 표시 창이 `CTaskDialog` 만들어진 후에는 이 메서드를 호출할 수 없습니다. 이렇게 하면 이 메서드는 예외를 throw합니다.

*nButtonMask로* 표시된 단추는 이전에 에 추가된 일반적인 `CTaskDialog`단추를 재정의합니다. *nButtonMask에* 표시된 단추만 사용할 수 있습니다.

*n장애인ButtonMask* 또는 *nElevationButtonMaskn에* *nButtonMask에*없는 단추를 포함 하는 경우이 메서드는 [ENSURE](diagnostic-services.md#ensure) 매크로를 사용 하 여 예외를 throw 합니다.

기본적으로 모든 공통 단추가 활성화되어 있으며 고도가 필요하지 않습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]

## <a name="ctaskdialogsetcontent"></a><a name="setcontent"></a>CTaskDialog::설정 콘텐츠

의 내용을 업데이트합니다. `CTaskDialog`

```cpp
void SetContent(const CString& strContent);
```

### <a name="parameters"></a>매개 변수

*스트콘텐츠*<br/>
【인】 사용자에게 표시할 문자열입니다.

### <a name="remarks"></a>설명

`CTaskDialog` 클래스의 내용은 대화 상자의 기본 섹션에 있는 사용자에게 표시되는 텍스트입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetdefaultcommandcontrol"></a><a name="setdefaultcommandcontrol"></a>CTaskDialog::설정기본 명령 제어

기본 명령 단추 컨트롤을 지정합니다.

```cpp
void SetDefaultCommandControl(int nCommandControlID);
```

### <a name="parameters"></a>매개 변수

*n명령제어ID*<br/>
【인】 명령 단추 컨트롤의 ID가 기본값입니다.

### <a name="remarks"></a>설명

기본 명령 단추 컨트롤은 사용자에게 처음 `CTaskDialog` 표시될 때 선택되는 컨트롤입니다.

이 메서드는 *nCommandControlID*에 의해 지정 된 명령 단추 컨트롤을 찾을 수 없는 경우 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]

## <a name="ctaskdialogsetdefaultradiobutton"></a><a name="setdefaultradiobutton"></a>CTask Dialog::설정기본라디오버튼

기본 라디오 단추를 지정합니다.

```cpp
void SetDefaultRadioButton(int nRadioButtonID);
```

### <a name="parameters"></a>매개 변수

*n라디오버튼ID*<br/>
【인】 라디오 버튼의 ID가 기본값입니다.

### <a name="remarks"></a>설명

기본 라디오 단추는 사용자에게 처음 표시될 때 `CTaskDialog` 선택된 단추입니다.

이 메서드는 *nRadioButtonID에서*지정한 라디오 단추를 찾을 수 없는 경우 예외를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetdialogwidth"></a><a name="setdialogwidth"></a>CTaskDialog::SetDialog폭

의 너비를 조정합니다. `CTaskDialog`

```cpp
void SetDialogWidth(int nWidth = 0);
```

### <a name="parameters"></a>매개 변수

*nWidth*<br/>
【인】 대화 상자의 너비(픽셀)입니다.

### <a name="remarks"></a>설명

*매개변수 nWidth는* 0보다 크거나 같아야 합니다. 그렇지 않으면 이 메서드는 예외를 throw합니다.

*nWidth가* 0으로 설정된 경우 이 메서드는 대화 상자를 기본 크기로 설정합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetexpansionarea"></a><a name="setexpansionarea"></a>CTaskDialog::세트확장영역

의 확장 영역을 `CTaskDialog`업데이트합니다.

```cpp
void SetExpansionArea(
    const CString& strExpandedInformation,
    const CString& strCollapsedLabel = _T(""),
    const CString& strExpandedLabel = _T(""));
```

### <a name="parameters"></a>매개 변수

*strExpanded정보*<br/>
【인】 사용자가 확장 `CTaskDialog` 단추를 클릭할 때 대화 상자의 본문에 표시되는 문자열입니다.

*strCollapsed레이블*<br/>
【인】 확장 영역이 `CTaskDialog` 축소될 때 확장 단추 옆에 표시되는 문자열입니다.

*strExpandedLabel*<br/>
【인】 확장 영역이 `CTaskDialog` 표시될 때 확장 단추 옆에 표시되는 문자열입니다.

### <a name="remarks"></a>설명

클래스의 확장 `CTaskDialog` 영역을 사용하면 사용자에게 추가 정보를 제공할 수 있습니다. 확장 영역은 제목 및 콘텐츠 `CTaskDialog`문자열 바로 아래에 있는 의 주요 부분에 있습니다.

를 `CTaskDialog` 처음 표시하면 확장 된 정보가 표시되지 `strCollapsedLabel` 않고 확장 버튼 옆에 놓습니다. 사용자가 확장 단추를 클릭하면 `CTaskDialog` *strExpanded정보가* 표시되고 레이블을 *strExpandedLabel*로 변경합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootericon"></a><a name="setfootericon"></a>CTaskDialog::SetFooterIcon

의 바닥글 아이콘을 `CTaskDialog`업데이트합니다.

```cpp
void SetFooterIcon(HICON hFooterIcon);
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```

### <a name="parameters"></a>매개 변수

*h풋터아이콘*<br/>
【인】 에 대한 새 `CTaskDialog`아이콘입니다.

*lpsz풋터아이콘*<br/>
【인】 에 대한 새 `CTaskDialog`아이콘입니다.

### <a name="remarks"></a>설명

바닥글 아이콘은 [CTaskDialog 클래스의](../../mfc/reference/ctaskdialog-class.md)맨 아래에 표시됩니다. 연관된 바닥글 텍스트를 가질 수 있습니다. [CTaskDialog::SetFooterText](#setfootertext)를 사용하면 바닥글 텍스트를 변경할 수 있습니다.

이 메서드는 [표시](diagnostic-services.md#ensure) 또는 입력 매개 `CTaskDialog` 변수가 NULL인 경우 ENSURE 매크로에 대한 예외를 throw합니다.

A는 `CTaskDialog` `HICON` 바닥글 `LPCWSTR` 아이콘으로만 허용할 수 있습니다. 이는 생성자 또는 CTaskDialog에서 TDF_USE_HICON_FOOTER 옵션을 설정하여 [구성됩니다.:SetOptions](#setoptions). 기본적으로 는 `CTaskDialog` 바닥글 아이콘의 `LPCWSTR` 입력 유형으로 사용하도록 구성됩니다. 이 메서드는 부적절한 형식을 사용하여 아이콘을 설정하려고 하면 예외를 생성합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetfootertext"></a><a name="setfootertext"></a>CTaskDialog::SetFooterText

의 바닥글에 있는 텍스트를 `CTaskDialog`업데이트합니다.

```cpp
void SetFooterText(const CString& strFooterText);
```

### <a name="parameters"></a>매개 변수

*스트라터텍스트*<br/>
【인】 바닥글의 새 텍스트입니다.

### <a name="remarks"></a>설명

바닥글 아이콘은 `CTaskDialog`의 하단에 있는 바닥글 텍스트 옆에 나타납니다. [CTaskDialog::SetFooterIcon을](#setfootericon)사용 하 고 바닥글 아이콘을 변경할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmainicon"></a><a name="setmainicon"></a>CTaskDialog::SetMainicon

의 기본 아이콘을 `CTaskDialog`업데이트합니다.

```cpp
void SetMainIcon(HICON hMainIcon);
void SetMainIcon(LPCWSTR lpszMainIcon);
```

### <a name="parameters"></a>매개 변수

*hMainIcon*<br/>
【인】 새 아이콘입니다.

*lpszMainIcon*<br/>
【인】 새 아이콘입니다.

### <a name="remarks"></a>설명

이 메서드는 [표시](diagnostic-services.md#ensure) 또는 입력 매개 `CTaskDialog` 변수가 NULL인 경우 ENSURE 매크로에 대한 예외를 throw합니다.

A는 `CTaskDialog` `HICON` 또는 `LPCWSTR` 주 아이콘으로만 허용할 수 있습니다. 생성자 또는 [CTaskDialog::SetOptions](#setoptions) 메서드에서 TDF_USE_HICON_MAIN 옵션을 설정 하여이 작업을 구성할 수 있습니다. 기본적으로 는 `CTaskDialog` 기본 아이콘의 `LPCWSTR` 입력 유형으로 사용하도록 구성됩니다. 이 메서드는 부적절한 형식을 사용하여 아이콘을 설정하려고 하면 예외를 생성합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetmaininstruction"></a><a name="setmaininstruction"></a>CTaskDialog::설정기본 지시

의 기본 지침을 `CTaskDialog`업데이트합니다.

```cpp
void SetMainInstruction(const CString& strInstructions);
```

### <a name="parameters"></a>매개 변수

*스트어드어*<br/>
【인】 새 기본 명령어입니다.

### <a name="remarks"></a>설명

`CTaskDialog` 클래스의 주요 명령은 큰 굵은 글꼴로 사용자에게 표시되는 텍스트입니다. 제목 표시줄 아래의 대화 상자에 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetoptions"></a><a name="setoptions"></a>CTaskDialog::설정 옵션

에 대한 옵션을 `CTaskDialog`구성합니다.

```cpp
void SetOptions(int nOptionFlag);
```

### <a name="parameters"></a>매개 변수

*n옵션플래그*<br/>
【인】 에 사용할 플래그 집합입니다. `CTaskDialog`

### <a name="remarks"></a>설명

이 메서드는 의 모든 현재 `CTaskDialog`옵션을 지웁울 수 있습니다. 현재 옵션을 유지하려면 [먼저 CTaskDialog::GetOptions를](#getoptions) 사용하여 검색하고 설정하려는 옵션과 결합해야 합니다.

다음 표에는 유효한 모든 옵션이 나열되어 있습니다.

|||
|-|-|
|TDF_ENABLE_HYPERLINKS|에서 하이퍼링크를 `CTaskDialog`활성화합니다.|
|TDF_USE_HICON_MAIN|메인 아이콘에 `CTaskDialog` 사용할 `HICON` 을 구성합니다. 다른 방법은 `LPCWSTR`을 사용하는 것입니다.|
|TDF_USE_HICON_FOOTER|`CTaskDialog` 바닥글 아이콘에 `HICON` 사용할 을 구성합니다. 다른 방법은 `LPCWSTR`을 사용하는 것입니다.|
|TDF_ALLOW_DIALOG_CANCELLATION|취소 단추를 사용하지 `CTaskDialog` 않은 경우에도 키보드를 사용하거나 대화 상자의 오른쪽 상단 모서리에 있는 **Cancel** 아이콘을 사용하여 사용자가 닫을 수 있습니다. 이 플래그가 설정되지 않고 **취소** 단추를 사용하지 않으면 Alt+F4, 이스케이프 키 또는 제목 표시줄의 닫기 단추를 사용하여 대화 상자를 닫을 수 없습니다.|
|TDF_USE_COMMAND_LINKS|명령 단추 `CTaskDialog` 컨트롤을 사용하도록 구성됩니다.|
|TDF_USE_COMMAND_LINKS_NO_ICON|컨트롤 옆에 `CTaskDialog` 아이콘을 표시하지 않고 명령 단추 컨트롤을 사용하도록 구성합니다. TDF_USE_COMMAND_LINKS TDF_USE_COMMAND_LINKS_NO_ICON 재정의합니다.|
|TDF_EXPAND_FOOTER_AREA|확장 영역이 현재 확장중임을 나타냅니다.|
|TDF_EXPANDED_BY_DEFAULT|확장 영역이 기본적으로 확장되는지 여부를 결정합니다.|
|TDF_VERIFICATION_FLAG_CHECKED|확인 확인 란이 현재 선택되어 있음을 나타냅니다.|
|TDF_SHOW_PROGRESS_BAR|진행률 `CTaskDialog` 표시줄을 표시하도록 구성합니다.|
|TDF_SHOW_MARQUEE_PROGRESS_BAR|진행률 표시줄을 선택 윤곽 진행률 표시줄로 구성합니다. 이 옵션을 사용하도록 설정하면 TDF_SHOW_PROGRESS_BAR 예상된 동작이 있도록 설정해야 합니다.|
|TDF_CALLBACK_TIMER|`CTaskDialog` 콜백 간격이 약 200밀리초로 설정되어 있음을 나타냅니다.|
|TDF_POSITION_RELATIVE_TO_WINDOW|`CTaskDialog` 상위 창을 기준으로 가운데에 있도록 구성합니다. 이 플래그를 사용하지 않으면 `CTaskDialog` 모니터를 기준으로 가운데에 표시됩니다.|
|TDF_RTL_LAYOUT|오른쪽에서 `CTaskDialog` 왼쪽 읽기 레이아웃에 대해 구성합니다.|
|TDF_NO_DEFAULT_RADIO_BUTTON|`CTaskDialog` 라디오 버튼이 나타날 때 선택되지 않은 것을 나타냅니다.|
|TDF_CAN_BE_MINIMIZED|사용자가 `CTaskDialog`을 최소화할 수 있습니다. 이 옵션을 지원하려면 `CTaskDialog` 모달이 될 수 없습니다. MFC는 모덜리스를 `CTaskDialog`지원하지 않으므로 이 옵션을 지원하지 않습니다.|

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogsetprogressbarmarquee"></a><a name="setprogressbarmarquee"></a>CTask Dialog::설정진행률 바선택 윤곽

에 대한 선택 윤곽 `CTaskDialog` 막대를 구성하고 대화 상자에 추가합니다.

```cpp
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,
    int nMarqueeSpeed = 0);
```

### <a name="parameters"></a>매개 변수

*bEnabled*<br/>
【인】 TRUE는 선택 윤곽 막대를 활성화합니다. FALSE를 사용하여 선택 윤곽 막대를 `CTaskDialog`비활성화하고 에서 제거합니다.

*nMarqueeSpeed*<br/>
【인】 선택 윤곽 막대의 속도를 나타내는 정수입니다.

### <a name="remarks"></a>설명

선택 윤곽 막대는 `CTaskDialog` 클래스의 주 텍스트 아래에 나타납니다.

*nMarqueeSpeed를* 사용하여 선택 윤곽 막대의 속도를 설정합니다. 값이 클수록 속도가 느려집니다. *nMarqueeSpeed에* 대한 값이 0이면 선택 윤곽 막대가 Windows의 기본 속도로 이동합니다.

이 메서드는 *nMarqueeSpeed가* 0보다 큰 경우 [ENSURE](diagnostic-services.md#ensure) 매크로에 예외를 throw합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarposition"></a><a name="setprogressbarposition"></a>CTask Dialog::설정진행바 포지션

진행률 표시줄의 위치를 조정합니다.

```cpp
void SetProgressBarPosition(int nProgressPos);
```

### <a name="parameters"></a>매개 변수

*nProgressPos*<br/>
【인】 진행률 표시줄의 위치입니다.

### <a name="remarks"></a>설명

*이* 메서드는 진행률 표시줄 범위에 없는 경우 [ENSURE](diagnostic-services.md#ensure) 매크로에 예외를 throw합니다. [CTaskDialog::SetProgressBarRange를](#setprogressbarrange)사용하면 진행률 표시줄 범위를 변경할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarrange"></a><a name="setprogressbarrange"></a>CTask Dialog::설정진행률바레인지

진행률 표시줄의 범위를 조정합니다.

```cpp
void SetProgressBarRange(
    int nRangeMin,
    int nRangeMax);
```

### <a name="parameters"></a>매개 변수

*nRangeMin*<br/>
【인】 진행률 표시줄의 하한입니다.

*nRangeMax*<br/>
【인】 진행률 표시줄의 상한입니다.

### <a name="remarks"></a>설명

진행률 표시줄의 위치는 *nRangeMin* 및 *nRangeMax를*기준으로 합니다. 예를 들어 *nRangeMin이* 50이고 *nRangeMax가* 100인 경우 75의 위치는 진행률 표시줄의 중간입니다. [CTaskDialog::SetProgressBarPosition를](#setprogressbarposition) 사용하여 진행률 표시줄의 위치를 설정합니다.

진행률 표시줄을 표시하려면 TDF_SHOW_PROGRESS_BAR 옵션을 사용하도록 설정해야 하며 TDF_SHOW_MARQUEE_PROGRESS_BAR 활성화할 수 없습니다. 이 메서드는 자동으로 TDF_SHOW_PROGRESS_BAR 설정 하 고 TDF_SHOW_MARQUEE_PROGRESS_BAR 지웁을 지웁히습니다. [CTaskDialog::SetOptions를](#setoptions) 사용하여 [CTaskDialog 클래스의](../../mfc/reference/ctaskdialog-class.md)이 인스턴스에 대한 옵션을 수동으로 변경합니다.

이 메서드는 *nRangeMin nRangeMax* 보다 적은 경우 [ENSURE](diagnostic-services.md#ensure) 매크로에 대 한 *예외를*throw 합니다. 이 `CTaskDialog` 메서드는 이미 표시 되어 있고 선택 윤곽 진행률 표시줄이 있는 경우 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetprogressbarstate"></a><a name="setprogressbarstate"></a>CTaskDialog::설정진행률바스테이트

진행률 표시줄의 상태를 설정하고 `CTaskDialog`에 표시합니다.

```cpp
void SetProgressBarState(int nState = PBST_NORMAL);
```

### <a name="parameters"></a>매개 변수

*nState*<br/>
【인】 진행률 표시줄의 상태입니다. 가능한 값은 비고 섹션을 참조하십시오.

### <a name="remarks"></a>설명

이 메서드는 [이미](diagnostic-services.md#ensure) 표시 `CTaskDialog` 되어 있고 선택 윤곽 진행률 표시줄이 있는 경우 ENSURE 매크로에 대 한 예외를 throw 합니다.

다음 표에는 nState 에 대한 가능한 값이 *나열되어*있습니다. 이러한 모든 경우에 진행률 표시줄은 지정된 정지 위치에 도달할 때까지 일반 색상으로 채워집니다. 이 시점에서 상태에 따라 색상이 변경됩니다.

|||
|-|-|
|PBST_NORMAL|진행률 표시줄이 채워진 후에는 `CTaskDialog` 막대의 색상이 변경되지 않습니다. 기본적으로 일반 색상은 녹색입니다.|
|PBST_ERROR|진행률 표시줄이 채우면 막대의 색상이 오류 색상으로 `CTaskDialog` 변경됩니다. 기본적으로 빨간색입니다.|
|PBST_PAUSED|진행률 표시줄이 채우면 막대의 색상이 일시 중지된 색상으로 `CTaskDialog` 변경됩니다. 기본적으로 노란색입니다.|

[CTaskDialog::SetProgressBarPosition를](#setprogressbarposition)통해 진행률 표시줄이 중지되는 위치를 설정할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]

## <a name="ctaskdialogsetradiobuttonoptions"></a><a name="setradiobuttonoptions"></a>CTaskDialog::설정라디오 단추옵션

라디오 단추를 활성화하거나 사용하지 않도록 설정합니다.

```cpp
void SetRadioButtonOptions(
    int nRadioButtonID,
    BOOL bEnabled);
```

### <a name="parameters"></a>매개 변수

*n라디오버튼ID*<br/>
【인】 라디오 버튼 컨트롤의 ID입니다.

*bEnabled*<br/>
【인】 TRUE라디오 버튼을 활성화; FALSE를 클릭하여 라디오 단추를 비활성화합니다.

### <a name="remarks"></a>설명

이 메서드는 *nRadioButtonID가* 라디오 단추에 대 한 유효한 ID인 경우 [ENSURE](diagnostic-services.md#ensure) 매크로에 대 한 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]

## <a name="ctaskdialogsetverificationcheckbox"></a><a name="setverificationcheckbox"></a>CTaskDialog::확인 확인란

확인 확인란의 선택된 상태를 설정합니다.

```cpp
void SetVerificationCheckbox(BOOL bChecked);
```

### <a name="parameters"></a>매개 변수

*b 확인됨*<br/>
【인】 를 표시할 때 확인 확인란을 선택하도록 하는 `CTaskDialog` 경우; FALSE가 표시될 때 확인 확인란을 선택하지 않은 `CTaskDialog` 것으로 간주됩니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetverificationcheckboxtext"></a><a name="setverificationcheckboxtext"></a>CTask Dialog::설정 확인확인백

확인 확인란의 오른쪽에 표시되는 텍스트를 설정합니다.

```cpp
void SetVerificationCheckboxText(CString& strVerificationText);
```

### <a name="parameters"></a>매개 변수

*str검증텍스트*<br/>
【인】 확인 확인 란 옆에 이 메서드가 표시되는 텍스트입니다.

### <a name="remarks"></a>설명

이 메서드는 클래스의 [ENSURE](diagnostic-services.md#ensure) 이 인스턴스가 이미 `CTaskDialog` 표시 된 경우 ENSURE 매크로에 대 한 예외를 throw 합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]

## <a name="ctaskdialogsetwindowtitle"></a><a name="setwindowtitle"></a>CTaskDialog::세트윈도우타이틀

의 제목을 `CTaskDialog`설정합니다.

```cpp
void SetWindowTitle(CString& strWindowTitle);
```

### <a name="parameters"></a>매개 변수

*스트윈도우타이틀*<br/>
【인】 의 새 제목입니다. `CTaskDialog`

### <a name="remarks"></a>설명

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]

## <a name="ctaskdialogshowdialog"></a><a name="showdialog"></a>CTaskDialog::쇼디아로그

`CTaskDialog`을 만들고 표시합니다.

```
static INT_PTR ShowDialog(
    const CString& strContent,
    const CString& strMainInstruction,
    const CString& strTitle,
    int nIDCommandControlsFirst,
    int nIDCommandControlsLast,
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,
    const CString& strFooter = _T(""));
```

### <a name="parameters"></a>매개 변수

*스트콘텐츠*<br/>
【인】 의 내용에 사용할 문자열입니다. `CTaskDialog`

*스트메인 지시*<br/>
【인】 의 주요 지침입니다. `CTaskDialog`

*스트제목*<br/>
【인】 의 제목입니다. `CTaskDialog`

*nID명령컨트롤우선*<br/>
【인】 첫 번째 명령의 문자열 ID입니다.

*니드커맨드컨트롤스마지막*<br/>
【인】 마지막 명령의 문자열 ID입니다.

*n공통 단추*<br/>
【인】 에 추가할 단추의 마스크입니다. `CTaskDialog`

*nTaskDialog옵션*<br/>
【인】 에 사용할 옵션 집합입니다. `CTaskDialog`

*스트풋터*<br/>
【인】 바닥글로서 사용할 끈.

### <a name="return-value"></a>Return Value

사용자가 선택한 값에 해당하는 정수입니다.

### <a name="remarks"></a>설명

이 정적 메서드를 사용하면 코드에서 `CTaskDialog` 개체를 명시적으로 `CTaskDialog` 만들지 않고 클래스의 인스턴스를 만들 수 있습니다. 개체가 없기 `CTaskDialog` 때문에 이 메서드를 사용하여 `CTaskDialog` 사용자에게 a를 `CTaskDialog` 표시하는 경우의 다른 메서드를 호출할 수 없습니다.

이 메서드는 응용 프로그램의 리소스 파일에서 데이터를 사용 하 여 명령 단추 컨트롤을 만듭니다. 리소스 파일의 문자열 테이블에는 연결된 문자열 이있는 여러 문자열이 있습니다. 이 메서드는 *nIDCommandControlsFirst* 와 *nCommandControlsLast,* 포함 사이의 문자열 테이블의 각 유효한 항목에 대한 명령 단추 컨트롤을 추가합니다. 이러한 명령 단추 컨트롤의 경우 문자열 테이블의 문자열은 컨트롤의 캡션이고 문자열 ID는 컨트롤의 ID입니다.

유효한 옵션 목록은 [CTaskDialog::Set옵션을](#setoptions) 참조하십시오.

사용자가 `CTaskDialog` 공통 단추, 명령 링크 컨트롤을 선택하거나 `CTaskDialog`을 닫을 때 닫힙니다. 반환 값은 사용자가 대화 상자를 닫은 방법을 나타내는 식별자입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFC_CTaskDialog#1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]

## <a name="ctaskdialogtaskdialogcallback"></a><a name="taskdialogcallback"></a>CTaskDialog::작업디아로그콜백

프레임워크는 다양한 Windows 메시지에 대한 응답으로 이 메서드를 호출합니다.

```
friend:
HRESULT TaskDialogCallback(
    HWND hWnd,
    UINT uNotification,
    WPARAM wParam,
    LPARAM lParam,
    LONG_PTR dwRefData);
```

### <a name="parameters"></a>매개 변수

*Hwnd*<br/>
【인】 의 구조에 `m_hWnd` 대한 `CTaskDialog`핸들입니다.

*u 알림*<br/>
【인】 생성된 메시지를 지정하는 알림 코드입니다.

*wParam*<br/>
【인】 메시지에 대한 자세한 정보입니다.

*lParam*<br/>
【인】 메시지에 대한 자세한 정보입니다.

*dwRefData*<br/>
【인】 콜백 메시지가 `CTaskDialog` 적용되는 개체에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

특정 알림 코드에 따라 다릅니다. 자세한 내용은 주의 섹션을 참조하십시오.

### <a name="remarks"></a>설명

기본 구현은 `TaskDialogCallback` 특정 메시지를 처리한 다음 [CTaskDialog 클래스의](../../mfc/reference/ctaskdialog-class.md)적절한 On 메서드를 호출합니다. 예를 들어 TDN_BUTTON_CLICKED 메시지에 대한 `TaskDialogCallback` 응답으로 [CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)을 호출합니다.

*wParam* 및 *lParam의* 값은 생성된 특정 메시지에 따라 달라집니다. 이러한 값 중 하나 또는 둘 다 비어 있을 수 있습니다. 다음 표에는 지원되는 기본 알림과 *wParam* 및 *lParam의* 값이 나타내는 내용이 나열되어 있습니다. 파생 클래스에서 이 메서드를 재정의하는 경우 다음 표의 각 메시지에 대한 콜백 코드를 구현해야 합니다.

|알림 메시지|*wParam* 값|*l파라임* 값|
|--------------------------|--------------------|--------------------|
|TDN_CREATED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_NAVIGATED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_BUTTON_CLICKED|명령 단추 제어 ID입니다.|사용되지 않습니다.|
|TDN_HYPERLINK_CLICKED|사용되지 않습니다.|링크를 포함하는 [LPCWSTR](/windows/win32/WinProg/windows-data-types) 구조입니다.|
|TDN_TIMER|타이머가 `CTaskDialog` 생성되었지만 타이머가 재설정된 이후의 시간(밀리초)입니다.|사용되지 않습니다.|
|TDN_DESTROYED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_RADIO_BUTTON_CLICKED|라디오 버튼 ID입니다.|사용되지 않습니다.|
|TDN_DIALOG_CONSTRUCTED|사용되지 않습니다.|사용되지 않습니다.|
|TDN_VERIFICATION_CLICKED|1 확인란을 선택하면 0이 아닌 경우.|사용되지 않습니다.|
|TDN_HELP|사용되지 않습니다.|사용되지 않습니다.|
|TDN_EXPANDO_BUTTON_CLICKED|확장 영역이 축소된 경우 0; 확장 텍스트가 표시되는 경우 0이 아닙니다.|사용되지 않습니다.|

## <a name="see-also"></a>참조

[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[연습: 애플리케이션에 CTaskDialog 추가](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)
