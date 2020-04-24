---
title: CCmdUI 클래스
ms.date: 09/06/2019
f1_keywords:
- CCmdUI
- AFXWIN/CCmdUI
- AFXWIN/CCmdUI::ContinueRouting
- AFXWIN/CCmdUI::Enable
- AFXWIN/CCmdUI::SetCheck
- AFXWIN/CCmdUI::SetRadio
- AFXWIN/CCmdUI::SetText
- AFXWIN/CCmdUI::m_nID
- AFXWIN/CCmdUI::m_nIndex
- AFXWIN/CCmdUI::m_pMenu
- AFXWIN/CCmdUI::m_pOther
- AFXWIN/CCmdUI::m_pSubMenu
helpviewer_keywords:
- CCmdUI [MFC], ContinueRouting
- CCmdUI [MFC], Enable
- CCmdUI [MFC], SetCheck
- CCmdUI [MFC], SetRadio
- CCmdUI [MFC], SetText
- CCmdUI [MFC], m_nID
- CCmdUI [MFC], m_nIndex
- CCmdUI [MFC], m_pMenu
- CCmdUI [MFC], m_pOther
- CCmdUI [MFC], m_pSubMenu
ms.assetid: 04eaaaf5-f510-48ab-b425-94665ba24766
ms.openlocfilehash: 3e167d9e305481e05808f5e553222c10abbc88de
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752731"
---
# <a name="ccmdui-class"></a>CCmdUI 클래스

`CCmdTarget`-derived 클래스의 `ON_UPDATE_COMMAND_UI` 처리기 내에서만 사용됩니다.

## <a name="syntax"></a>구문

```
class CCmdUI
```

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CCmdUI::계속 라우팅](#continuerouting)|명령 라우팅 메커니즘에 현재 메시지를 처리기 체인 아래로 계속 라우팅하도록 지시합니다.|
|[CCmdui::사용](#enable)|이 명령에 대한 사용자 인터페이스 항목을 활성화하거나 사용하지 않도록 설정합니다.|
|[CCmdUI::세트 체크](#setcheck)|이 명령에 대한 사용자 인터페이스 항목의 확인 상태를 설정합니다.|
|[CCmdUI ::세트 라디오](#setradio)|`SetCheck` 멤버 기능처럼, 하지만 라디오 그룹에서 작동합니다.|
|[CCmdUI::SetText](#settext)|이 명령에 대한 사용자 인터페이스 항목의 텍스트를 설정합니다.|

### <a name="public-data-members"></a>공용 데이터 멤버

|속성|Description|
|----------|-----------------|
|[CCmdui::m_nID](#m_nid)|사용자 인터페이스 개체의 ID입니다.|
|[CCmdui::m_nIndex](#m_nindex)|사용자 인터페이스 개체의 인덱스입니다.|
|[CCmdui::m_pMenu](#m_pmenu)|개체로 표시되는 메뉴를 `CCmdUI` 가리킵니다.|
|[CCmdui::m_pOther](#m_pother)|알림을 보낸 창 개체를 가리킵니다.|
|[CCmdui::m_pSubMenu](#m_psubmenu)|개체로 표시되는 포함된 하위 메뉴를 `CCmdUI` 가리킵니다.|

## <a name="remarks"></a>설명

`CCmdUI`기본 클래스가 없습니다.

응용 프로그램의 사용자가 메뉴를 아래로 당기면 각 메뉴 항목은 메뉴를 사용 설정 또는 사용 중지로 표시할지 여부를 알아야 합니다. 메뉴 명령의 대상은 ON_UPDATE_COMMAND_UI 처리기를 구현하여 이 정보를 제공합니다. 응용 프로그램의 각 명령 사용자 인터페이스 개체에 대해 [클래스 마법사](mfc-class-wizard.md) 또는 **속성** 창(클래스 **보기)을**사용하여 각 처리기에 대한 메시지 맵 항목 및 함수 프로토타입을 만듭니다.

메뉴가 아래로 당겨지면 프레임워크는 각 ON_UPDATE_COMMAND_UI 처리기를 검색하고 `CCmdUI` 호출하며, 각 `Enable` `Check`처리기는 및 및 및 의 멤버 함수를 호출한 다음 프레임워크는 각 메뉴 항목을 적절하게 표시합니다.

메뉴 항목은 `ON_UPDATE_COMMAND_UI` 처리기 내에서 코드를 변경하지 않고 컨트롤 바 단추 또는 기타 명령 사용자 인터페이스 개체로 바꿀 수 있습니다.

다음 표에는 멤버 함수가 다양한 명령 사용자 인터페이스 항목에 미치는 영향을 `CCmdUI`요약합니다.

|사용자 인터페이스 항목|사용|세트 체크|세트 라디오|Settext|
|--------------------------|------------|--------------|--------------|-------------|
|메뉴 항목|사용 설정 또는 비활성화|검사 또는 체크 취소|점을 사용한 검사|항목 텍스트 설정|
|도구 모음 단추|사용 설정 또는 비활성화|선택, 선택 취소 또는 확정되지 않음|`SetCheck`과 동일|(해당 없음)|
|상태 표시줄 창|텍스트를 표시하거나 보이지 않게 합니다.|팝업 또는 일반 테두리 설정|`SetCheck`과 동일|창 텍스트 설정|
|일반 버튼 의 경우`CDialogBar`|사용 설정 또는 비활성화|확인함 선택 또는 선택 취소 확인란|`SetCheck`과 동일|단추 텍스트 설정|
|정상적인 제어`CDialogBar`|사용 설정 또는 비활성화|(해당 없음)|(해당 없음)|창 텍스트 설정|

이 클래스의 사용에 대한 자세한 내용은 [사용자 인터페이스 개체를 업데이트하는 방법을](../../mfc/how-to-update-user-interface-objects.md)참조하십시오.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`CCmdUI`

## <a name="requirements"></a>요구 사항

**헤더:** afxwin.h

## <a name="ccmduicontinuerouting"></a><a name="continuerouting"></a>CCmdUI::계속 라우팅

이 멤버 함수를 호출하여 명령 라우팅 메커니즘에 현재 메시지를 처리기 체인 아래로 계속 라우팅하도록 지시합니다.

```cpp
void ContinueRouting();
```

### <a name="remarks"></a>설명

FALSE를 반환 하는 ON_COMMAND_EX 처리기와 함께 사용 해야 하는 고급 멤버 함수입니다. 자세한 내용은 [기술 참고 6을](../../mfc/tn006-message-maps.md)참조하십시오.

## <a name="ccmduienable"></a><a name="enable"></a>CCmdui::사용

이 명령에 대한 사용자 인터페이스 항목을 사용하거나 사용하지 않도록 설정하려면 이 멤버 함수를 호출합니다.

```
virtual void Enable(BOOL bOn = TRUE);
```

### <a name="parameters"></a>매개 변수

*본*<br/>
TRUE 항목을 활성화하려면 FALSE를 사용하여 비활성화합니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#46](../../mfc/codesnippet/cpp/ccmdui-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#47](../../mfc/codesnippet/cpp/ccmdui-class_2.cpp)]

## <a name="ccmduim_nid"></a><a name="m_nid"></a>CCmdui::m_nID

메뉴 항목, 도구 모음 단추 또는 개체로 표시되는 기타 `CCmdUI` 사용자 인터페이스 개체의 ID입니다.

```
UINT m_nID;
```

## <a name="ccmduim_nindex"></a><a name="m_nindex"></a>CCmdui::m_nIndex

메뉴 항목, 도구 모음 단추 또는 개체로 표시되는 기타 `CCmdUI` 사용자 인터페이스 개체의 인덱스입니다.

```
UINT m_nIndex;
```

## <a name="ccmduim_pmenu"></a><a name="m_pmenu"></a>CCmdui::m_pMenu

개체로 `CMenu` 표시되는 메뉴에 대한 포인터(형식)입니다. `CCmdUI`

```
CMenu* m_pMenu;
```

### <a name="remarks"></a>설명

항목이 메뉴가 아닌 경우 NULL입니다.

## <a name="ccmduim_psubmenu"></a><a name="m_psubmenu"></a>CCmdui::m_pSubMenu

개체로 `CMenu` 표시되는 포함된 하위 메뉴에 대한 `CCmdUI` 포인터(형식)입니다.

```
CMenu* m_pSubMenu;
```

### <a name="remarks"></a>설명

항목이 메뉴가 아닌 경우 NULL입니다. 하위 메뉴가 팝업인 경우 *m_nID* 팝업 메뉴의 첫 번째 항목의 ID를 포함합니다. 자세한 내용은 [기술 참고 21을](../../mfc/tn021-command-and-message-routing.md)참조하십시오.

## <a name="ccmduim_pother"></a><a name="m_pother"></a>CCmdui::m_pOther

알림(형식)을 `CWnd`도구 또는 상태 표시줄과 같은 창 개체에 대한 포인터입니다.

```
CWnd* m_pOther;
```

### <a name="remarks"></a>설명

항목이 메뉴 또는 개체가 아닌 `CWnd` 경우 NULL입니다.

## <a name="ccmduisetcheck"></a><a name="setcheck"></a>CCmdUI::세트 체크

이 멤버 함수를 호출하여 이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다.

```
virtual void SetCheck(int nCheck = 1);
```

### <a name="parameters"></a>매개 변수

*nCheck*<br/>
설정할 검사 상태를 지정합니다. 0이면 체크를 취소합니다. 경우 1, 확인; 및 경우 2, 설정 불확정.

### <a name="remarks"></a>설명

이 멤버 함수는 메뉴 항목 및 도구 모음 단추에 대해 작동합니다. 확정되지 않은 상태는 도구 모음 단추에만 적용됩니다.

## <a name="ccmduisetradio"></a><a name="setradio"></a>CCmdUI ::세트 라디오

이 멤버 함수를 호출하여 이 명령에 대한 사용자 인터페이스 항목을 적절한 검사 상태로 설정합니다.

```
virtual void SetRadio(BOOL bOn = TRUE);
```

### <a name="parameters"></a>매개 변수

*본*<br/>
TRUE 항목을 활성화합니다. 그렇지 않으면 거짓.

### <a name="remarks"></a>설명

이 멤버 함수는 `SetCheck`무선 그룹의 일부로 작동하는 사용자 인터페이스 항목에서 작동한다는 점을 제외하면 와 같이 작동합니다. 항목 자체가 무선 그룹 동작을 유지하지 않는 한 그룹의 다른 항목 선택을 취소하는 것은 자동으로 수행되지 않습니다.

## <a name="ccmduisettext"></a><a name="settext"></a>CCmdUI::SetText

이 명령에 대한 사용자 인터페이스 항목의 텍스트를 설정하려면 이 멤버 함수를 호출합니다.

```
virtual void SetText(LPCTSTR lpszText);
```

### <a name="parameters"></a>매개 변수

*lpszText*<br/>
텍스트 문자열에 대한 포인터입니다.

### <a name="example"></a>예제

[!code-cpp[NVC_MFCDocView#48](../../mfc/codesnippet/cpp/ccmdui-class_3.cpp)]

## <a name="see-also"></a>참조

[MFC 샘플 MDI](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)
