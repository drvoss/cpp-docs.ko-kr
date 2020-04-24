---
title: C스플릿버튼 클래스
ms.date: 11/19/2018
f1_keywords:
- CSplitButton
- AFXCMN/CSplitButton
- AFXCMN/CSplitButton::CSplitButton
- AFXCMN/CSplitButton::Create
- AFXCMN/CSplitButton::SetDropDownMenu
- AFXCMN/CSplitButton::OnDropDown
helpviewer_keywords:
- CSplitButton [MFC], CSplitButton
- CSplitButton [MFC], Create
- CSplitButton [MFC], SetDropDownMenu
- CSplitButton [MFC], OnDropDown
ms.assetid: 6844d0a9-6408-4e44-9b5f-57628ed8bad6
ms.openlocfilehash: 38fceed1cc42ca0aac2e6ddaf145db273c95771d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753137"
---
# <a name="csplitbutton-class"></a>C스플릿버튼 클래스

클래스는 `CSplitButton` 분할 단추 컨트롤을 나타냅니다. 분할 단추 컨트롤은 사용자가 단추의 주요 부분을 클릭할 때 기본 동작을 수행하고 사용자가 단추의 드롭다운 화살표를 클릭하면 드롭다운 메뉴를 표시합니다.

## <a name="syntax"></a>구문

```
class CSplitButton : public CButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[C분할 단추::C분할 단추](#csplitbutton)|`CSplitButton` 개체를 생성합니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[C분할 단추::만들기](#create)|지정된 스타일로 분할 단추 컨트롤을 만들고 현재 `CSplitButton` 개체에 연결합니다.|
|[C분할 단추::설정 드롭다운 메뉴](#setdropdownmenu)|사용자가 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시되는 드롭다운 메뉴를 설정합니다.|

### <a name="protected-methods"></a>Protected 메서드

|속성|Description|
|----------|-----------------|
|[C스플릿 버튼::드롭다운](#ondropdown)|사용자가 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 시스템이 보내는 BCN_DROPDOWN 알림을 처리합니다.|

## <a name="remarks"></a>설명

`CSplitButton` 클래스는 [CButton](../../mfc/reference/cbutton-class.md) 클래스에서 파생됩니다. 분할 버튼 컨트롤은 스타일이 BS_SPLITBUTTON 버튼 컨트롤입니다. 사용자가 드롭다운 화살표를 클릭하면 사용자 지정 메뉴가 표시됩니다. 자세한 내용은 [단추 스타일에서](/windows/win32/Controls/button-styles)BS_SPLITBUTTON 및 BS_DEFSPLITBUTTON 스타일을 참조하십시오.

다음 그림에서는 호출기 컨트롤과 (1) 분할 단추 컨트롤이 포함된 대화 상자가 표시됩니다. (2) 드롭다운 화살표가 이미 클릭되었으며 (3) 하위 메뉴가 표시됩니다.

![splitbutton 및 pager 컨트롤이 있는 대화 상자](../../mfc/reference/media/splitbutton_pager.png "splitbutton 및 pager 컨트롤이 있는 대화 상자")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

`CSplitButton`

## <a name="requirements"></a>요구 사항

**헤더:** afxcmn.h

이 클래스는 Windows Vista 및 이후에서 지원됩니다.

이 클래스에 대한 추가 요구 사항은 [Windows Vista 공용 컨트롤에 대한 빌드 요구 사항에](../../mfc/build-requirements-for-windows-vista-common-controls.md)설명되어 있습니다.

## <a name="csplitbuttoncreate"></a><a name="create"></a>C분할 단추::만들기

지정된 스타일로 분할 단추 컨트롤을 만들고 현재 `CSplitButton` 개체에 연결합니다.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*dwStyle*|【인】 컨트롤에 적용할 스타일의 비트 조합(OR)입니다. 자세한 내용은 [단추 스타일을](../../mfc/reference/styles-used-by-mfc.md#button-styles)참조하십시오.|
|*rect*|【인】 컨트롤의 위치와 크기를 포함하는 [RECT](/windows/win32/api/windef/ns-windef-rect) 구조에 대한 참조입니다.|
|*pParentWnd*|【인】 컨트롤의 상위 창인 [CWnd](../../mfc/reference/cwnd-class.md) 개체에 대한 null이 아닌 포인터입니다.|
|*nID*|【인】 컨트롤의 ID입니다.|

### <a name="return-value"></a>Return Value

이 메서드가 성공하면 TRUE입니다. 그렇지 않으면 false입니다.

## <a name="csplitbuttoncsplitbutton"></a><a name="csplitbutton"></a>C분할 단추::C분할 단추

`CSplitButton` 개체를 생성합니다. 생성자의 매개 변수는 사용자가 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시되는 하위 메뉴를 지정합니다.

```
CSplitButton();

CSplitButton(
    UINT nMenuId,
    UINT nSubMenuId)
CSplitButton(CMenu* pMenu)
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*n메뉴Id*|【인】 메뉴 모음의 리소스 ID입니다.|
|*n서브메뉴이드*|【인】 하위 메뉴의 리소스 ID입니다.|
|*p메뉴*|【인】 하위 메뉴를 지정하는 [CMenu](../../mfc/reference/cmenu-class.md) 개체에 대한 포인터입니다. 개체가 `CSplitButton` 범위를 `CMenu` 벗어날 때 개체와 관련 `CSplitButton` 된 HMENU를 삭제 합니다.|

### <a name="remarks"></a>설명

[CSplitButton::만들기](#create) 메서드를 사용하여 분할 단추 컨트롤을 만들고 `CSplitButton` 개체에 연결합니다.

## <a name="csplitbuttonondropdown"></a><a name="ondropdown"></a>C스플릿 버튼::드롭다운

사용자가 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 시스템이 보내는 BCN_DROPDOWN 알림을 처리합니다.

```
afx_msg void OnDropDown(
    NMHDR* pNMHDR,
    LRESULT* pResult);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*pNMHDR*|【인】 [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) 알림에 대한 정보가 포함된 [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) 구조에 대한 포인터입니다.|
|*p결과*|【아웃】 (사용되지 않음; 값이 반환되지 않습니다.) [BCN_DROPDOWN](/windows/win32/Controls/bcn-dropdown) 알림의 반환 값입니다.|

### <a name="remarks"></a>설명

사용자가 분할 단추 컨트롤에서 드롭다운 화살표를 클릭하면 시스템이 메서드가 `OnDropDown` 처리하는 BCN_DROPDOWN 알림 메시지를 보냅니다. 그러나 개체는 `CSplitButton` 분할 단추 컨트롤을 포함 하는 컨트롤에 BCN_DROPDOWN 알림을 전달 하지 않습니다. 따라서 포함 된 컨트롤 알림에 대 한 응답으로 사용자 지정 작업을 지원할 수 없습니다.

포함된 컨트롤이 지원하는 사용자 지정 작업을 구현하려면 개체 대신 BS_SPLITBUTTON 스타일로 [CButton](../../mfc/reference/cbutton-class.md) 개체를 `CSplitButton` 사용합니다. 그런 다음 개체에서 BCN_DROPDOWN 알림에 대한 처리기를 구현합니다. `CButton` 자세한 내용은 [단추 스타일을](../../mfc/reference/styles-used-by-mfc.md#button-styles)참조하십시오.

분할 단추 컨트롤 자체가 지원하는 사용자 지정 작업을 구현하려면 [메시지 리플렉션을](../../mfc/tn062-message-reflection-for-windows-controls.md)사용합니다. 클래스에서 사용자 고유의 클래스를 `CSplitButton` 파생하고 이름을 지정합니다(예: CMySplitButton). 그런 다음 다음 메시지 맵을 응용 프로그램에 추가하여 BCN_DROPDOWN 알림을 처리합니다.

```
BEGIN_MESSAGE_MAP(CMySplitButton,
    CSplitButton)
    ON_NOTIFY_REFLECT(BCN_DROPDOWN, &CMySplitButton::OnDropDown)
END_MESSAGE_MAP()
```

## <a name="csplitbuttonsetdropdownmenu"></a><a name="setdropdownmenu"></a>C분할 단추::설정 드롭다운 메뉴

사용자가 현재 분할 단추 컨트롤의 드롭다운 화살표를 클릭할 때 표시되는 드롭다운 메뉴를 설정합니다.

```cpp
void SetDropDownMenu(
    UINT nMenuId,
    UINT nSubMenuId);

void SetDropDownMenu(CMenu* pMenu);
```

### <a name="parameters"></a>매개 변수

|매개 변수|Description|
|---------------|-----------------|
|*n메뉴Id*|【인】 메뉴 모음의 리소스 ID입니다.|
|*n서브메뉴이드*|【인】 하위 메뉴의 리소스 ID입니다.|
|*p메뉴*|【인】 하위 메뉴를 지정하는 [CMenu](../../mfc/reference/cmenu-class.md) 개체에 대한 포인터입니다. 개체가 `CSplitButton` 범위를 `CMenu` 벗어날 때 개체와 관련 `CSplitButton` 된 HMENU를 삭제 합니다.|

### <a name="remarks"></a>설명

*nMenuId* 매개 변수는 메뉴 막대 항목의 가로 목록인 메뉴 모음을 식별합니다. *nSubMenuId* 매개 변수는 하위 메뉴를 식별하는 0기반 인덱스 번호로, 각 메뉴 막대 항목과 연결된 메뉴 항목의 드롭다운 목록입니다. 예를 들어 일반적인 응용 프로그램에는 메뉴 모음 항목인 "파일", "편집"및 "도움말"이 포함된 메뉴가 있습니다. "파일" 메뉴 모음 항목에는 메뉴 항목인 "열기", "닫기" 및 "종료"가 포함된 하위 메뉴가 있습니다. 분할 단추 컨트롤의 드롭다운 화살표를 클릭하면 컨트롤에 메뉴 막대가 아닌 지정된 하위 메뉴가 표시됩니다.

다음 그림에서는 호출기 컨트롤과 (1) 분할 단추 컨트롤이 포함된 대화 상자가 표시됩니다. (2) 드롭다운 화살표가 이미 클릭되었으며 (3) 하위 메뉴가 표시됩니다.

![splitbutton 및 pager 컨트롤이 있는 대화 상자](../../mfc/reference/media/splitbutton_pager.png "splitbutton 및 pager 컨트롤이 있는 대화 상자")

### <a name="example"></a>예제

다음 코드 예제의 첫 번째 문은 [CSplitButton:SetDropDownMenu](#setdropdownmenu) 메서드를 보여 줍니다. 메뉴 모음 ID의 이름을 자동으로 지정하는 Visual Studio 리소스 편집기에서 IDR_MENU1 메뉴를 만들었습니다. *0인 nSubMenuId* 매개 변수는 메뉴 모음의 유일한 하위 메뉴를 나타냅니다.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/csplitbutton-class_1.cpp)]

## <a name="see-also"></a>참조

[C스플릿버튼 클래스](../../mfc/reference/csplitbutton-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CButton 클래스](../../mfc/reference/cbutton-class.md)
