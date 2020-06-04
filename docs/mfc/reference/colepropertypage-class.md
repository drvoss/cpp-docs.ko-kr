---
title: COlePropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::OVERWRITEApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
helpviewer_keywords:
- COlePropertyPage [MFC], COlePropertyPage
- COlePropertyPage [MFC], GetControlStatus
- COlePropertyPage [MFC], GetObjectArray
- COlePropertyPage [MFC], GetPageSite
- COlePropertyPage [MFC], IgnoreApply
- COlePropertyPage [MFC], IsModified
- COlePropertyPage [MFC], OnEditProperty
- COlePropertyPage [MFC], OnHelp
- COlePropertyPage [MFC], OnInitDialog
- COlePropertyPage [MFC], OnObjectsChanged
- COlePropertyPage [MFC], OnSetPageSite
- COlePropertyPage [MFC], SetControlStatus
- COlePropertyPage [MFC], SetDialogResource
- COlePropertyPage [MFC], SetHelpInfo
- COlePropertyPage [MFC], SetModifiedFlag
- COlePropertyPage [MFC], SetPageName
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
ms.openlocfilehash: 872ade08438e54098da730012f98cdd906483887
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753794"
---
# <a name="colepropertypage-class"></a>COlePropertyPage 클래스

대화 상자와 유사한 그래픽 인터페이스의 사용자 지정 컨트롤의 속성을 표시하는 데 사용됩니다.

## <a name="syntax"></a>구문

```
class AFX_NOVTABLE COlePropertyPage : public CDialog
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[콜레프로퍼티페이지::콜레프로퍼티페이지](#colepropertypage)|`COlePropertyPage` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[COle속성 페이지::GetControlStatus](#getcontrolstatus)|사용자가 컨트롤의 값을 수정했는지 여부를 나타냅니다.|
|[COlePropertyPage::GetObjectArray](#getobjectarray)|속성 페이지에서 편집중인 개체의 배열을 반환합니다.|
|[콜레프로퍼티페이지::겟페이지사이트](#getpagesite)|속성 페이지의 인터페이스에 대한 `IPropertyPageSite` 포인터를 반환합니다.|
|[COle속성 페이지::무시 적용](#ignoreapply)|적용 단추를 사용하지 않는 컨트롤을 결정합니다.|
|[COle속성 페이지::수정되었습니다.](#ismodified)|사용자가 속성 페이지를 수정했는지 여부를 나타냅니다.|
|[콜레프로퍼티페이지::온더티프로퍼티](#oneditproperty)|사용자가 속성을 편집할 때 프레임워크에서 호출됩니다.|
|[콜레프로퍼티페이지::온헬프](#onhelp)|사용자가 도움을 호출할 때 프레임워크에서 호출됩니다.|
|[COlePropertyPage::IninitDialog](#oninitdialog)|속성 페이지가 초기화될 때 프레임워크에서 호출됩니다.|
|[COle속성 페이지::개체 변경](#onobjectschanged)|새 속성을 사용하는 다른 OLE 컨트롤이 선택될 때 프레임워크에서 호출됩니다.|
|[콜레속성 페이지::온셋 페이지사이트](#onsetpagesite)|속성 프레임이 페이지의 사이트를 제공하는 경우 프레임워크에서 호출됩니다.|
|[COle속성 페이지::설정 제어 상태](#setcontrolstatus)|사용자가 컨트롤의 값을 수정했는지 여부를 나타내는 플래그를 설정합니다.|
|[COlePropertyPage::SetDialogResource](#setdialogresource)|속성 페이지의 대화 상자 리소스를 설정합니다.|
|[콜레속성 페이지::세트도움말정보](#sethelpinfo)|속성 페이지의 간략한 도움말 텍스트, 도움말 파일 이름 및 도움말 컨텍스트를 설정합니다.|
|[콜레속성 페이지::집합수정 플래그](#setmodifiedflag)|사용자가 속성 페이지를 수정했는지 여부를 나타내는 플래그를 설정합니다.|
|[콜레속성 페이지::집합 페이지 이름](#setpagename)|속성 페이지의 이름(캡션)을 설정합니다.|

## <a name="remarks"></a>설명

예를 들어 속성 페이지에는 사용자가 컨트롤의 캡션 속성을 보고 수정할 수 있는 편집 컨트롤이 포함될 수 있습니다.

각 사용자 지정 또는 주식 제어 속성에는 컨트롤의 사용자가 현재 속성 값을 보고 필요한 경우 해당 값을 수정할 수 있는 대화 상자 컨트롤이 있을 수 있습니다.

사용에 `COlePropertyPage`대한 자세한 내용은 [ActiveX 컨트롤: 속성 페이지를](../../mfc/mfc-activex-controls-property-pages.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`COlePropertyPage`

## <a name="requirements"></a>요구 사항

**헤더:** afxctl.h

## <a name="colepropertypagecolepropertypage"></a><a name="colepropertypage"></a>콜레프로퍼티페이지::콜레프로퍼티페이지

`COlePropertyPage` 개체를 생성합니다.

```
COlePropertyPage(
    UINT idDlg,
    UINT idCaption);
```

### <a name="parameters"></a>매개 변수

*idDlg*<br/>
대화 상자 템플릿의 리소스 ID입니다.

*id캡션*<br/>
속성 페이지의 캡션의 리소스 ID입니다.

### <a name="remarks"></a>설명

`COlePropertyPage`의 하위 클래스를 구현할 때 하위 클래스의 생성자는 `COlePropertyPage` 생성기를 사용하여 속성 페이지의 기반이 되는 대화 상자 템플릿 리소스와 캡션을 포함하는 문자열 리소스를 식별해야 합니다.

## <a name="colepropertypagegetcontrolstatus"></a><a name="getcontrolstatus"></a>COle속성 페이지::GetControlStatus

사용자가 지정된 리소스 ID를 사용하여 속성 페이지 컨트롤의 값을 수정했는지 여부를 확인합니다.

```
BOOL GetControlStatus(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
속성 페이지 컨트롤의 리소스 ID입니다.

### <a name="return-value"></a>Return Value

컨트롤 값이 수정된 경우 TRUE입니다. 그렇지 않으면 거짓.

## <a name="colepropertypagegetobjectarray"></a><a name="getobjectarray"></a>COlePropertyPage::GetObjectArray

속성 페이지에서 편집중인 개체의 배열을 반환합니다.

```
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```

### <a name="parameters"></a>매개 변수

*pn개체*<br/>
페이지에서 편집중인 개체 수를 받을 수 있는 서명되지 않은 긴 정수에 대한 포인터입니다.

### <a name="return-value"></a>Return Value

속성 페이지에서 각 `IDispatch` 컨트롤의 속성에 액세스하는 데 사용되는 포인터 배열에 대한 포인터입니다. 호출자는 이러한 인터페이스 포인터를 해제해서는 안 됩니다.

### <a name="remarks"></a>설명

각 속성 페이지 개체는 페이지에서 편집중인 `IDispatch` 개체의 인터페이스에 대한 포인터 배열을 유지 관리합니다. 이 함수는 *pnObjects* 인수를 해당 배열의 요소 수로 설정하고 배열의 첫 번째 요소에 대한 포인터를 반환합니다.

## <a name="colepropertypagegetpagesite"></a><a name="getpagesite"></a>콜레프로퍼티페이지::겟페이지사이트

속성 페이지의 인터페이스에 대한 `IPropertyPageSite` 포인터를 가져옵니다.

```
LPPROPERTYPAGESITE GetPageSite();
```

### <a name="return-value"></a>Return Value

속성 페이지의 인터페이스에 대한 `IPropertyPageSite` 포인터입니다.

### <a name="remarks"></a>설명

컨트롤과 컨테이너는 사용자가 컨트롤 속성을 찾아보고 편집할 수 있도록 협력합니다. 컨트롤은 사용자가 관련 속성 집합을 편집할 수 있는 OLE 개체인 속성 페이지를 제공합니다. 컨테이너는 속성 페이지를 표시하는 속성 프레임을 제공합니다. 각 페이지에 대해 속성 프레임은 `IPropertyPageSite` 인터페이스를 지원하는 페이지 사이트를 제공합니다.

## <a name="colepropertypageignoreapply"></a><a name="ignoreapply"></a>COle속성 페이지::무시 적용

적용 단추를 사용하지 않는 컨트롤을 결정합니다.

```cpp
void IgnoreApply(UINT nID);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
무시할 컨트롤의 ID입니다.

### <a name="remarks"></a>설명

속성 페이지의 적용 단추는 속성 페이지 컨트롤의 값이 변경된 경우에만 활성화됩니다. 이 함수를 사용하여 값이 변경될 때 적용 단추를 사용하도록 설정하지 않는 컨트롤을 지정합니다.

## <a name="colepropertypageismodified"></a><a name="ismodified"></a>COle속성 페이지::수정되었습니다.

사용자가 속성 페이지에서 값을 변경했는지 여부를 확인합니다.

```
BOOL IsModified();
```

### <a name="return-value"></a>Return Value

속성 페이지가 수정된 경우 TRUE입니다.

## <a name="colepropertypageoneditproperty"></a><a name="oneditproperty"></a>콜레프로퍼티페이지::온더티프로퍼티

프레임워크는 특정 속성을 편집할 때 이 함수를 호출합니다.

```
virtual BOOL OnEditProperty(DISPID dispid);
```

### <a name="parameters"></a>매개 변수

*디스피드 (것)들*<br/>
편집 중인 속성의 디스패치 ID입니다.

### <a name="return-value"></a>Return Value

기본 구현은 FALSE를 반환합니다. 이 함수의 재정의는 TRUE를 반환해야 합니다.

### <a name="remarks"></a>설명

재정의하여 페이지의 적절한 컨트롤로 포커스를 설정할 수 있습니다. 기본 구현은 아무 것도 수행하지 않으며 FALSE를 반환합니다.

## <a name="colepropertypageonhelp"></a><a name="onhelp"></a>콜레프로퍼티페이지::온헬프

사용자가 온라인 도움말을 요청할 때 프레임워크는 이 함수를 호출합니다.

```
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```

### <a name="parameters"></a>매개 변수

*lpszHelpDir*<br/>
속성 페이지의 도움말 파일이 포함된 디렉터리입니다.

### <a name="return-value"></a>Return Value

기본 구현은 FALSE를 반환합니다.

### <a name="remarks"></a>설명

사용자가 도움을 받을 때 속성 페이지에서 특별한 작업을 수행해야 하는 경우 재정의합니다. 기본 구현은 아무 것도 하지 않으며 FALSE를 반환하여 프레임워크에서 WinHelp를 호출하도록 지시합니다.

## <a name="colepropertypageoninitdialog"></a><a name="oninitdialog"></a>COlePropertyPage::IninitDialog

프레임워크는 속성 페이지의 대화 상자가 초기화될 때 이 함수를 호출합니다.

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>Return Value

기본 구현은 FALSE를 반환합니다.

### <a name="remarks"></a>설명

대화 상자를 초기화할 때 특별한 작업이 필요한 경우 재정의합니다. 기본 구현 `CDialog::OnInitDialog` 호출 하 고 FALSE를 반환 합니다.

## <a name="colepropertypageonobjectschanged"></a><a name="onobjectschanged"></a>COle속성 페이지::개체 변경

새 속성을 사용하는 다른 OLE 컨트롤이 선택될 때 프레임워크에서 호출됩니다.

```
virtual void OnObjectsChanged();
```

### <a name="remarks"></a>설명

개발자 환경에서 OLE 컨트롤의 속성을 볼 때 모덜리스 대화 상자가 해당 속성 페이지를 표시하는 데 사용됩니다. 다른 컨트롤을 선택한 경우 새 속성 집합에 대해 다른 속성 페이지 집합이 표시되어야 합니다. 프레임워크는 이 함수를 호출하여 변경 의 속성 페이지를 알립니다.

이 함수를 재정의하여 이 작업에 대한 알림을 받고 특별한 작업을 수행합니다.

## <a name="colepropertypageonsetpagesite"></a><a name="onsetpagesite"></a>콜레속성 페이지::온셋 페이지사이트

속성 프레임이 속성 페이지의 페이지 사이트를 제공할 때 프레임워크는 이 함수를 호출합니다.

```
virtual void OnSetPageSite();
```

### <a name="remarks"></a>설명

기본 구현은 페이지의 캡션을 로드하고 대화 상자 리소스에서 페이지 크기를 확인하려고 시도합니다. 속성 페이지에 추가 작업이 필요한 경우 이 함수를 재정의합니다. 재정의는 기본 클래스 구현을 호출해야 합니다.

## <a name="colepropertypagesetcontrolstatus"></a><a name="setcontrolstatus"></a>COle속성 페이지::설정 제어 상태

속성 페이지 컨트롤의 상태를 변경합니다.

```
BOOL SetControlStatus(
    UINT nID,
    BOOL bDirty);
```

### <a name="parameters"></a>매개 변수

*nID*<br/>
속성 페이지 컨트롤의 ID를 포함합니다.

*bDirty*<br/>
속성 페이지의 필드가 수정되었는지 지정합니다. 필드가 수정된 경우 TRUE로 설정하고 수정되지 않은 경우 FALSE로 설정합니다.

### <a name="return-value"></a>Return Value

TRUE, 지정된 컨트롤이 설정된 경우; 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

속성 페이지가 닫히거나 적용 단추를 선택할 때 속성 페이지 컨트롤의 상태가 더러워지면 컨트롤의 속성이 적절한 값으로 업데이트됩니다.

## <a name="colepropertypagesetdialogresource"></a><a name="setdialogresource"></a>COlePropertyPage::SetDialogResource

속성 페이지의 대화 상자 리소스를 설정합니다.

```cpp
void SetDialogResource(HGLOBAL hDialog);
```

### <a name="parameters"></a>매개 변수

*hDialog*<br/>
속성 페이지의 대화 상자 리소스를 처리합니다.

## <a name="colepropertypagesethelpinfo"></a><a name="sethelpinfo"></a>콜레속성 페이지::세트도움말정보

도구 설명 정보, 도움말 파일 이름 및 속성 페이지에 대한 도움말 컨텍스트를 지정합니다.

```cpp
void SetHelpInfo(
    LPCTSTR lpszDocString,
    LPCTSTR lpszHelpFile = NULL,
    DWORD dwHelpContext = 0);
```

### <a name="parameters"></a>매개 변수

*lpszDocString*<br/>
상태 표시줄 또는 기타 위치에 표시하기 위한 간단한 도움말 정보가 포함된 문자열입니다.

*lpszHelpFile*<br/>
속성 페이지의 도움말 파일 의 이름입니다.

*dw도움말컨텍스트*<br/>
속성 페이지에 대한 컨텍스트 를 도와줍니다.

## <a name="colepropertypagesetmodifiedflag"></a><a name="setmodifiedflag"></a>콜레속성 페이지::집합수정 플래그

사용자가 속성 페이지를 수정했는지 여부를 나타냅니다.

```cpp
void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>매개 변수

*bModified*<br/>
속성 페이지의 수정된 플래그에 대한 새 값을 지정합니다.

## <a name="colepropertypagesetpagename"></a><a name="setpagename"></a>콜레속성 페이지::집합 페이지 이름

속성 페이지의 이름을 설정합니다.

```cpp
void SetPageName(LPCTSTR lpszPageName);
```

### <a name="parameters"></a>매개 변수

*lpszPageName*<br/>
속성 페이지의 이름이 포함된 문자열에 대한 포인터입니다.

## <a name="see-also"></a>참조

[MFC 샘플 CIRC3](../../overview/visual-cpp-samples.md)<br/>
[MFC 샘플 테스트도움말](../../overview/visual-cpp-samples.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클리언로그 클래스](../../mfc/reference/cdialog-class.md)
