---
title: CMFCEditBrowseCtrl 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
helpviewer_keywords:
- CMFCEditBrowseCtrl [MFC], EnableBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFileBrowseButton
- CMFCEditBrowseCtrl [MFC], EnableFolderBrowseButton
- CMFCEditBrowseCtrl [MFC], GetMode
- CMFCEditBrowseCtrl [MFC], OnAfterUpdate
- CMFCEditBrowseCtrl [MFC], OnBrowse
- CMFCEditBrowseCtrl [MFC], OnChangeLayout
- CMFCEditBrowseCtrl [MFC], OnDrawBrowseButton
- CMFCEditBrowseCtrl [MFC], OnIllegalFileName
- CMFCEditBrowseCtrl [MFC], SetBrowseButtonImage
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
ms.openlocfilehash: d542af4a87b6f0a33c0344d1d3da76980f8c1a91
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752371"
---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl 클래스

클래스는 `CMFCEditBrowseCtrl` 선택적으로 찾아보기 단추를 포함하는 편집 가능한 텍스트 상자인 편집 찾아보기 컨트롤을 지원합니다. 사용자가 찾아보기 단추를 클릭하면 컨트롤은 사용자 지정 작업을 수행하거나 파일 브라우저 또는 폴더 브라우저가 포함된 표준 대화 상자를 표시합니다.

## <a name="syntax"></a>구문

```
class CMFCEditBrowseCtrl : public CEdit
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|기본 생성자입니다.|
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFCEdit찾아보기Ctrl:::인에이블브라우시블 버튼](#enablebrowsebutton)|찾아보기 단추를 활성화 하거나 사용하지 않도록 설정합니다.|
|[CMFCEdit찾아보기Ctrl:::인에이블파일 찾아보기 버튼](#enablefilebrowsebutton)|찾아보기 단추를 활성화하고 편집 찾아보기 컨트롤을 *파일 찾아보기* 모드로 넣습니다.|
|[CMFCEdit찾아보기Ctrl:::인에이블폴더찾아보기 버튼](#enablefolderbrowsebutton)|찾아보기 단추를 활성화하고 폴더 찾아보기 모드에서 편집 찾아보기 컨트롤을 *넣습니다.*|
|[CMFCEditBrowseCtrl::GetMode](#getmode)|현재 찾아보기 모드를 반환합니다.|
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|편집 찾아보기 컨트롤이 찾아보기 작업의 결과로 업데이트된 후 프레임워크에서 호출됩니다.|
|[CMFCEditBrowseCtrl:::온브라우트](#onbrowse)|사용자가 찾아보기 단추를 클릭한 후 프레임워크에서 호출됩니다.|
|[CMFCEditBrowseCtrl:::온체인지 레이아웃](#onchangelayout)|현재 편집 찾아보기 컨트롤을 다시 그립니다.|
|[CMFCEditBrowseCtrl:::온드로우브라우찾아보기 버튼](#ondrawbrowsebutton)|찾아보기 단추를 그리는 프레임 워크에 의해 호출 됩니다.|
|[CMFCEditBrowseCtrl:::에불법 파일 이름](#onillegalfilename)|편집 컨트롤에 잘못된 파일 이름을 입력할 때 프레임워크에서 호출됩니다.|
|`CMFCEditBrowseCtrl::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. 구문 및 자세한 내용은 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 참조하십시오.|
|[CMFCEdit찾아보기Ctrl:::세트 찾아보기 버튼이미지](#setbrowsebuttonimage)|찾아보기 단추에 대한 사용자 지정 이미지를 설정합니다.|

## <a name="remarks"></a>설명

편집 찾아보기 컨트롤을 사용하여 파일 또는 폴더 이름을 선택합니다. 선택적으로 컨트롤을 사용하여 대화 상자를 표시하는 등의 사용자 지정 작업을 수행합니다. 찾아보기 단추를 표시하거나 표시하지 않을 수 있으며 단추에 사용자 지정 레이블 또는 이미지를 적용할 수 있습니다.

편집 찾아보기 컨트롤의 *찾아보기 모드는* 찾아보기 단추를 표시할지 여부와 단추를 클릭할 때 발생하는 작업을 결정합니다. 자세한 내용은 [GetMode](#getmode) 메서드를 참조하십시오.

클래스는 `CMFCEditBrowseCtrl` 다음 모드를 지원합니다.

- **사용자 지정 모드**

   사용자 지정 작업은 사용자가 찾아보기 단추를 클릭할 때 수행됩니다. 예를 들어 응용 프로그램별 대화 상자를 표시할 수 있습니다.

- **파일 모드**

   사용자가 찾아보기 단추를 클릭하면 표준 파일 선택 대화 상자가 표시됩니다.

- **폴더 모드**

   사용자가 찾아보기 단추를 클릭하면 표준 폴더 선택 대화 상자가 표시됩니다.

## <a name="how-to-specify-an-edit-browse-control"></a>방법: 편집 찾아보기 컨트롤 지정

다음 단계를 수행하여 응용 프로그램에 편집 찾아보기 컨트롤을 통합합니다.

1. 사용자 지정 찾아보기 모드를 구현하려면 `CMFCEditBrowseCtrl` 클래스에서 고유한 클래스를 파생한 다음 [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) 메서드를 재정의합니다. 재정의된 메서드에서 사용자 지정 찾아보기 작업을 실행하고 결과로 편집 찾아보기 컨트롤을 업데이트합니다.

1. `CMFCEditBrowseCtrl` 개체 또는 파생된 편집 컨트롤 개체를 부모 창 개체에 포함합니다.

1. **클래스 마법사를** 사용하여 대화 상자를 만드는 경우 대화 상자 `CEdit`양식에 편집 컨트롤()을 추가합니다. 또한 변수를 추가하여 헤더 파일의 컨트롤에 액세스합니다. 헤더 파일에서 변수의 형식을 `CEdit` 에서 로 `CMFCEditBrowseCtrl`변경합니다. 편집 찾아보기 컨트롤이 자동으로 만들어집니다. **클래스 마법사를**사용하지 않는 경우 `CMFCEditBrowseCtrl` 헤더 파일에 변수를 추가한 `Create` 다음 해당 메서드를 호출합니다.

1. 대화 상자에 편집 찾아보기 컨트롤을 추가하는 경우 **ClassWizard** 도구를 사용하여 데이터 교환을 설정합니다.

1. [인에이블폴더찾아보기 버튼,](#enablefolderbrowsebutton) [인에이블파일브라우찾아버튼](#enablefilebrowsebutton)또는 [인에이블브라우지버튼](#enablebrowsebutton) 메서드를 호출하여 찾아보기 모드를 설정하고 찾아보기 버튼을 표시합니다. [GetMode](#getmode) 메서드를 호출하여 현재 찾아보기 모드를 가져옵니다.

1. 찾아보기 단추에 대한 사용자 지정 이미지를 제공하려면 [SetBrowseButtonImage](#setbrowsebuttonimage) 메서드를 호출하거나 [OnDrawBrowseButton](#ondrawbrowsebutton) 메서드를 재정의합니다.

1. 편집 찾아보기 컨트롤에서 찾아보기 단추를 제거하려면 *bEnable* 매개 변수가 FALSE로 설정된 [EnableBrowseButton](#enablebrowsebutton) 메서드를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)

## <a name="example"></a>예제

다음 예제에서는 클래스에서 두 메서드를 `CMFCEditBrowseCtrl` 사용 `EnableFolderBrowseButton` `EnableFileBrowseButton`하는 방법을 보여 줍니다. 이 예제는 [새 컨트롤 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_NewControls#6](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#7](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]

## <a name="requirements"></a>요구 사항

**헤더:** afxeditbrowsectrl.h

## <a name="cmfceditbrowsectrlenablebrowsebutton"></a><a name="enablebrowsebutton"></a>CMFCEdit찾아보기Ctrl:::인에이블브라우시블 버튼

현재 편집 찾아보기 컨트롤에 찾아보기 단추를 표시하거나 표시되지 않습니다.

```cpp
void EnableBrowseButton(
    BOOL bEnable=TRUE,
    LPCTSTR szLabel=_T("..."));
```

### <a name="parameters"></a>매개 변수

*bEnable*<br/>
TRUE 찾아보기 버튼을 표시합니다. FALSE는 찾아보기 버튼을 표시하지 않습니다. 기본값은 TRUE입니다.

*szLabel*<br/>
찾아보기 단추에 표시되는 레이블입니다. 기본값은 " **...**"입니다.

### <a name="remarks"></a>설명

*bEnable* 매개 변수가 TRUE이면 찾아보기 단추를 클릭할 때 수행할 사용자 지정 작업을 구현합니다. 사용자 지정 작업을 구현하려면 클래스에서 `CMFCEditBrowseCtrl` 클래스를 파생한 다음 [OnBrowse](#onbrowse) 메서드를 재정의합니다.

*bEnable* 매개 변수가 TRUE이면 컨트롤의 `BrowseMode_Default`찾아보기 모드는 ; 그렇지 않으면 찾아보기 `BrowseMode_None`모드는 . 찾아보기 모드에 대한 자세한 내용은 [GetMode](#getmode) 메서드를 참조하십시오.

## <a name="cmfceditbrowsectrlenablefilebrowsebutton"></a><a name="enablefilebrowsebutton"></a>CMFCEdit찾아보기Ctrl:::인에이블파일 찾아보기 버튼

현재 편집 찾아보기 컨트롤에 찾아보기 단추를 표시하고 *컨트롤을 파일 찾아보기* 모드로 넣습니다.

```cpp
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,
    LPCTSTR lpszFilter=NULL,
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```

### <a name="parameters"></a>매개 변수

*lpsz데프엑스트*<br/>
파일 선택 대화 상자에서 사용되는 기본 파일 이름 확장명을 지정합니다. 기본값은 NULL입니다.

*lpsz필터*<br/>
파일 선택 대화 상자에서 사용되는 기본 필터 문자열을 지정합니다. 기본값은 NULL입니다.

*dwFlags*<br/>
대화 상자 플래그입니다. 기본값은 OFN_HIDEREADONLY와 OFN_OVERWRITEPROMPT의 비트 조합(OR)입니다.

### <a name="remarks"></a>설명

편집 찾아보기 컨트롤이 파일 찾아보기 모드에 있고 사용자가 찾아보기 단추를 클릭하는 경우 컨트롤이 표준 파일 선택 대화 상자를 표시합니다.

사용 가능한 플래그의 전체 목록은 [OPENFILENAME 구조를](/windows/win32/api/commdlg/ns-commdlg-openfilenamew)참조하십시오.

## <a name="cmfceditbrowsectrlenablefolderbrowsebutton"></a><a name="enablefolderbrowsebutton"></a>CMFCEdit찾아보기Ctrl:::인에이블폴더찾아보기 버튼

현재 편집 찾아보기 컨트롤에 찾아보기 단추를 표시하고 *폴더 찾아보기* 모드로 컨트롤을 넣습니다.

```cpp
void EnableFolderBrowseButton();
```

### <a name="remarks"></a>설명

편집 찾아보기 컨트롤이 폴더 찾아보기 모드에 있고 사용자가 찾아보기 단추를 클릭하면 컨트롤에 표준 폴더 선택 대화 상자가 표시됩니다.

## <a name="cmfceditbrowsectrlgetmode"></a><a name="getmode"></a>CMFCEditBrowseCtrl::GetMode

현재 편집 찾아보기 컨트롤의 찾아보기 모드를 검색합니다.

```
CMFCEditBrowseCtrl::BrowseMode GetMode() const;
```

### <a name="return-value"></a>Return Value

편집 찾아보기 컨트롤의 현재 모드를 지정하는 열거형 값 중 하나입니다. 찾아보기 모드는 프레임워크에 찾아보기 단추를 표시할지 여부와 사용자가 해당 단추를 클릭할 때 발생하는 작업을 결정합니다.

다음 표에서는 가능한 반환 값을 보여 줍니다.

|값|Description|
|-----------|-----------------|
|`BrowseMode_Default`|**사용자 지정 모드**. 프로그래머 정의 작업이 수행됩니다.|
|`BrowseMode_File`|**파일 모드**. 표준 파일 브라우저 대화 상자가 표시됩니다.|
|`BrowseMode_Folder`|**폴더 모드**. 표준 폴더 브라우저 대화 상자가 표시됩니다.|
|`BrowseMode_None`|찾아보기 버튼이 표시되지 않습니다.|

### <a name="remarks"></a>설명

기본적으로 `CMFCEditBrowseCtrl` 개체는 모드로 `BrowseMode_None` 초기화됩니다. [CMFCEditBrowseCtrl::인에이블브라우시블브라우턴:](#enablebrowsebutton) [CMFCEditBrowseCtrl::인에이블파일브라우찾아볼버튼](#enablefilebrowsebutton)및 [CMFCEditBrowseCtrl::인에이블폴더찾아버튼](#enablefolderbrowsebutton) 메소드를 사용하여 찾아보기 모드를 수정합니다.

## <a name="cmfceditbrowsectrlonafterupdate"></a><a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate

편집 찾아보기 컨트롤이 찾아보기 작업의 결과로 업데이트된 후 프레임워크에서 호출됩니다.

```
virtual void OnAfterUpdate();
```

### <a name="remarks"></a>설명

파생 클래스에서 이 메서드를 재정의하여 사용자 지정 작업을 구현합니다.

## <a name="cmfceditbrowsectrlonbrowse"></a><a name="onbrowse"></a>CMFCEditBrowseCtrl:::온브라우트

사용자가 편집 찾아보기 컨트롤의 찾아보기 단추를 클릭한 후 프레임워크에서 호출합니다.

```
virtual void OnBrowse();
```

### <a name="remarks"></a>설명

사용자가 편집 찾아보기 컨트롤의 찾아보기 단추를 클릭할 때 이 메서드를 사용하여 사용자 지정 코드를 실행합니다. 클래스에서 사용자 고유의 클래스를 파생하고 메서드를 `CMFCEditBrowseCtrl` 재정의합니다. `OnBrowse` 이 메서드에서 사용자 지정 찾아보기 작업을 구현 하 고 선택적으로 편집 찾아보기 컨트롤의 텍스트 상자를 업데이트 합니다. 응용 프로그램에서 [EnableBrowseButton](#enablebrowsebutton) 메서드를 사용하여 편집 찾아보기 컨트롤을 *사용자 지정 찾아보기* 모드로 넣습니다.

## <a name="cmfceditbrowsectrlonchangelayout"></a><a name="onchangelayout"></a>CMFCEditBrowseCtrl:::온체인지 레이아웃

현재 편집 찾아보기 컨트롤을 다시 그립니다.

```
virtual void OnChangeLayout();
```

### <a name="remarks"></a>설명

프레임워크는 편집 찾아보기 컨트롤의 찾아보기 모드가 변경될 때 이 메서드를 호출합니다. 자세한 내용은 [CMFCEditBrowseCtrl::GetMode](#getmode)를 참조하십시오.

## <a name="cmfceditbrowsectrlondrawbrowsebutton"></a><a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl:::온드로우브라우찾아보기 버튼

편집 찾아보기 컨트롤에서 찾아보기 단추를 그리는 프레임워크에서 호출합니다.

```
virtual void OnDrawBrowseButton(
    CDC* pDC,
    CRect rect,
    BOOL bIsButtonPressed,
    BOOL bIsButtonHot);
```

### <a name="parameters"></a>매개 변수

*pDC*<br/>
디바이스 컨텍스트에 대한 포인터입니다.

*Rect*<br/>
찾아보기 단추의 경계 사각형입니다.

*비스버튼 누른*<br/>
버튼을 누르면 TRUE; 그렇지 않으면 false입니다.

*비스버튼핫*<br/>
TRUE 단추를 강조 표시 하는 경우; 그렇지 않으면 false입니다.

### <a name="remarks"></a>설명

파생 클래스에서 이 함수를 재정의하여 찾아보기 단추의 모양을 사용자 지정합니다.

## <a name="cmfceditbrowsectrlsetbrowsebuttonimage"></a><a name="setbrowsebuttonimage"></a>CMFCEdit찾아보기Ctrl:::세트 찾아보기 버튼이미지

편집 찾아보기 컨트롤의 찾아보기 단추에 사용자 지정 이미지를 설정합니다.

```cpp
void SetBrowseButtonImage(
    HICON hIcon,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(
    HBITMAP hBitmap,
    BOOL bAutoDestroy= TRUE);

void SetBrowseButtonImage(UINT uiBmpResId);
```

### <a name="parameters"></a>매개 변수

*hIcon*<br/>
아이콘의 핸들입니다.

*hBitmap*<br/>
비트맵의 핸들입니다.

*uiBmpResId*<br/>
비트맵의 리소스 ID입니다.

*b오토파괴*<br/>
TRUE이 메서드가 종료 될 때 지정된 아이콘 또는 비트 맵을 삭제합니다. 그렇지 않으면 false입니다. 기본값은 TRUE입니다.

### <a name="remarks"></a>설명

이 방법을 사용하여 사용자 지정 이미지를 찾아보기 단추에 적용합니다. 기본적으로 프레임워크는 편집 찾아보기 컨트롤이 *파일 찾아보기* 또는 *폴더 찾아보기* 모드에 있을 때 표준 이미지를 가져옵니다.

## <a name="cmfceditbrowsectrlonillegalfilename"></a><a name="onillegalfilename"></a>CMFCEditBrowseCtrl:::에불법 파일 이름

편집 컨트롤에 잘못된 파일 이름을 입력할 때 프레임워크에서 호출됩니다.

```
virtual BOOL OnIllegalFileName(CString& strFileName);
```

### <a name="parameters"></a>매개 변수

*strFileName*<br/>
잘못된 파일 이름을 지정합니다.

### <a name="return-value"></a>Return Value

이 파일 이름을 파일 대화 상자에 더 이상 전달할 수 없는 경우 FALSE를 반환 해야 합니다. 이 경우 포커스가 편집 컨트롤로 다시 설정되고 사용자는 편집을 계속해야 합니다. 기본 구현에는 잘못된 파일 이름에 대해 사용자에게 알리는 메시지 상자가 표시되고 FALSE를 반환합니다. 이 메서드를 재정의하고 파일 이름을 수정한 다음 추가 처리를 위해 TRUE를 반환할 수 있습니다.

### <a name="remarks"></a>설명

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
