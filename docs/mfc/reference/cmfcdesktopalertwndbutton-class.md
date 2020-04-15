---
title: CMFCDesktopAlertWndButton 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 5b18a15f8bfd98396acae0558d121b32bc4127c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367621"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton 클래스

단추를 데스크톱 경고 대화 상자에 추가할 수 있습니다.

## <a name="syntax"></a>구문

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|기본 생성자입니다.|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC데스크톱 경고 해제 단추::IsCaptionButton](#iscaptionbutton)|경고 대화 상자의 캡션 영역에 단추가 표시되는지 여부를 결정합니다.|
|[CMFC데스크톱 경고 해제 단추::닫기 단추](#isclosebutton)|단추를 닫는지 여부를 확인 합니다 경고 대화 상자입니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|속성|Description|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|경고 대화 상자의 캡션 영역에 단추가 표시되는지 여부를 지정하는 부울 값입니다.|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|단추경고 대화 상자를 닫는지 여부를 지정하는 부울 값입니다.|

### <a name="remarks"></a>설명

기본적으로 생성자는 및 `m_bIsCaptionButton` `m_bIsCloseButton` 데이터 멤버를 FALSE로 설정합니다. 단추경고 `CMFCDesktopAlertDialog` 대화 `m_bIsCaptionButton` 상자의 캡션 영역에 위치하는 경우 상위 개체가 TRUE로 설정됩니다. 클래스는 `CMFCDesktopAlertDialog` 경고 `CMFCDesktopAlertWndButton` 대화 상자를 닫고 TRUE로 설정하는 `m_bIsCloseButton` 단추 역할을 하는 개체를 만듭니다.

단추를 `CMFCDesktopAlertWndButton` 추가하는 `CMFCDesktopAlertDialog` 것처럼 개체에 개체를 추가합니다. 자세한 `CMFCDesktopAlertDialog`내용은 [CMFCDesktopAlertDialog 클래스를](../../mfc/reference/cmfcdesktopalertdialog-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 `SetImage` `CMFCDesktopAlertWndButton` 클래스에서 메서드를 사용 하는 방법을 보여 줍니다. 이 코드 조각은 데스크톱 [경고 데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFC데스크탑경고해제버튼](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxdesktopalertwnd.h

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a>CMFC데스크톱 경고 해제 단추::IsCaptionButton

경고 대화 상자의 캡션 영역에 단추가 표시되는지 여부를 결정합니다.

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>Return Value

경고 대화 상자의 캡션 영역에 단추가 표시되는 경우 0이 아닙니다. 그렇지 않으면 0입니다.

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a>CMFC데스크톱 경고 해제 단추::닫기 단추

단추를 닫는지 여부를 확인 합니다 경고 대화 상자입니다.

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>Return Value

버튼이 경고 대화 상자를 닫으면 0이 아닙니다. 그렇지 않으면 0입니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC데스크탑경고디아로그 클래스](../../mfc/reference/cmfcdesktopalertdialog-class.md)
