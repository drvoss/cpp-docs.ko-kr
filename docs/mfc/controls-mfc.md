---
title: 컨트롤(MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- Windows common controls [MFC]
- common controls [MFC]
- controls [MFC]
ms.assetid: b2842884-6435-4b8f-933b-21671bf8af95
ms.openlocfilehash: 454a76e8fdf55f43d75abb63d7d98a9fe4926127
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365319"
---
# <a name="controls-mfc"></a>컨트롤(MFC)

컨트롤은 사용자가 데이터를 입력하거나 조작하기 위해 상호 작용할 수 있는 개체입니다. 일반적으로 대화 상자 또는 도구 모음에 나타납니다. 이 항목 군에서는 다음 세 가지 주요 컨트롤 종류를 설명합니다.

- 소유자가 그린 컨트롤을 비롯한 Windows 공용 컨트롤

- ActiveX 컨트롤

- MFC(Microsoft Foundation Class) 라이브러리에서 제공하는 다른 컨트롤 클래스

## <a name="windows-common-controls"></a>Windows 공용 컨트롤

Windows 운영 체제는 항상 많은 Windows 공용 컨트롤을 제공합니다. 이러한 컨트롤 개체는 프로그래밍이 가능하며, Visual C++ 대화 상자 편집기는 컨트롤 개체를 대화 상자에 추가하는 것을 지원합니다. MFC(Microsoft Foundation Class) 라이브러리는 [Windows 공용 컨트롤 및 MFC 클래스](#_core_windows_common_controls_and_mfc_classes)표에 나와 있는 것처럼 각 컨트롤을 캡슐화하는 클래스를 지원합니다. 표의 일부 항목에는 자세히 설명하는 관련 항목이 있습니다. 관련 항목이 없는 컨트롤은 MFC 클래스에 대한 설명서를 참조하세요.

[CWnd](../mfc/reference/cwnd-class.md) 클래스는 모든 컨트롤 클래스를 포함하는 모든 창 클래스의 기본 클래스입니다.

## <a name="activex-controls"></a>ActiveX 컨트롤

이전에 OLE 컨트롤로 알려진 ActiveX 컨트롤은 Windows 애플리케이션의 대화 상자 또는 World Wide Web의 HTML 페이지에서 사용할 수 있습니다. 자세한 내용은 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)을 참조하세요.

## <a name="other-mfc-control-classes"></a>다른 MFC 컨트롤 클래스

모든 Windows 공용 컨트롤을 캡슐화하고 사용자 고유의 ActiveX 컨트롤 프로그래밍(또는 다른 사용자가 제공하는 ActiveX 컨트롤 사용)을 지원하는 클래스 외에 MFC는 다음과 같은 자체 컨트롤 클래스를 제공합니다.

- [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)

- [CCheckListBox](../mfc/reference/cchecklistbox-class.md)

- [CDragListBox](../mfc/reference/cdraglistbox-class.md)

## <a name="finding-information-about-windows-common-controls"></a><a name="_core_finding_information_about_windows_common_controls"></a> Windows 공용 컨트롤에 대한 정보 찾기

아래 표에서는 각 컨트롤의 MFC 래퍼 클래스를 포함하여 각 Windows 공용 컨트롤을 간략하게 설명합니다.

### <a name="windows-common-controls-and-mfc-classes"></a><a name="_core_windows_common_controls_and_mfc_classes"></a>윈도우 공통 컨트롤 및 MFC 클래스

|제어|MFC 클래스|Description|윈도우 95의 새로운 제품|
|-------------|---------------|-----------------|------------------------|
|[애니메이션](../mfc/using-canimatectrl.md)|[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)|AVI 비디오 클립의 연속 프레임을 표시합니다.|예|
|단추|[CButton](../mfc/reference/cbutton-class.md)|동작을 발생시키는 누름 단추입니다. 확인란, 라디오 단추 및 그룹 상자에도 사용됩니다.|예|
|콤보 상자|[CComboBox](../mfc/reference/ccombobox-class.md)|편집 상자와 목록 상자의 조합|예|
|[날짜 및 시간 선택](../mfc/using-cdatetimectrl.md)|[CDateTimeCtrl](../mfc/reference/cdatetimectrl-class.md)|사용자가 특정 날짜 또는 시간 값을 선택할 수 있습니다.|예|
|편집 상자|[CEdit](../mfc/reference/cedit-class.md)|텍스트 입력 상자|예|
|[확장된 콤보 상자](../mfc/using-ccomboboxex.md)|[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)|이미지를 표시할 수 있는 콤보 상자 컨트롤|예|
|[헤더](../mfc/using-cheaderctrl.md)|[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)|텍스트 열 위에 표시되는 단추로서, 표시되는 텍스트의 너비를 제어합니다.|예|
|[단축키](../mfc/using-chotkeyctrl.md)|[CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)|사용자가 작업을 빠르게 수행하기 위해 "바로 가기 키"를 만들 수 있는 창|예|
|[이미지 목록](../mfc/using-cimagelist.md)|[CImageList](../mfc/reference/cimagelist-class.md)|이미지의 컬렉션은 많은 아이콘이나 비트맵을 관리하는 데 사용됩니다(이미지 목록은 실제로 컨트롤이 아니며, 다른 컨트롤에서 사용되는 목록을 지원함).|예|
|[list](../mfc/using-clistctrl.md)|[CListCtrl](../mfc/reference/clistctrl-class.md)|아이콘을 사용하여 텍스트 목록을 표시하는 창|예|
|목록 상자|[CListBox](../mfc/reference/clistbox-class.md)|문자열 목록이 들어 있는 상자|예|
|[월 캘린더](../mfc/using-cmonthcalctrl.md)|[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)|날짜 정보를 표시하는 컨트롤|예|
|[진행률](../mfc/using-cprogressctrl.md)|[CProgressCtrl](../mfc/reference/cprogressctrl-class.md)|긴 작업의 진행률을 나타내는 창|예|
|[크기 조정 막대](../mfc/using-crebarctrl.md)|[CRebarCtrl](../mfc/reference/crebarctrl-class.md)|컨트롤 형식으로 추가 자식 창을 포함할 수 있는 도구 모음|예|
|[서식 있는 편집](../mfc/using-cricheditctrl.md)|[CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)|사용자가 문자와 단락 형식을 사용하여 편집할 수 있는 창( [Rich Edit 컨트롤 관련 클래스](../mfc/classes-related-to-rich-edit-controls.md)참조)|예|
|스크롤 막대|[CScrollBar](../mfc/reference/cscrollbar-class.md)|대화 상자(창이 아님) 내의 컨트롤로 사용되는 스크롤 막대|예|
|[슬라이더](../mfc/using-csliderctrl.md)|[CSliderCtrl](../mfc/reference/csliderctrl-class.md)|선택적 눈금이 있는 슬라이더 컨트롤을 포함하는 창|예|
|[스핀 단추](../mfc/using-cspinbuttonctrl.md)|[CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)|사용자가 클릭하여 값을 증가시키거나 감소시킬 수 있는 화살표 단추 쌍|예|
|정적 텍스트|[CStatic](../mfc/reference/cstatic-class.md)|다른 컨트롤에 레이블을 지정하기 위한 텍스트|예|
|[상태 표시줄](../mfc/using-cstatusbarctrl.md)|[CStatusBarCtrl](../mfc/reference/cstatusbarctrl-class.md)|MFC 클래스 `CStatusBar`와 유사한 상태 정보를 표시하는 창|예|
|[탭](../mfc/using-ctabctrl.md)|[CTabCtrl](../mfc/reference/ctabctrl-class.md)|전자 필기장의 구분선과 유사하며, "탭 대화 상자" 또는 속성 시트에 사용됨|예|
|[도구 모음](../mfc/using-ctoolbarctrl.md)|[CToolBarCtrl](../mfc/reference/ctoolbarctrl-class.md)|MFC 클래스 `CToolBar`와 유사한 명령 생성 단추가 있는 창|예|
|[도구 설명](../mfc/using-ctooltipctrl.md)|[CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)|도구 모음 단추 또는 다른 도구의 용도를 설명하는 작은 팝업 창|예|
|[트리](../mfc/using-ctreectrl.md)|[CTreeCtrl](../mfc/reference/ctreectrl-class.md)|항목의 계층 목록을 표시하는 창|예|

### <a name="what-do-you-want-to-know-more-about"></a>더 알고 싶으신가요?

- 개별 컨트롤: 모든 컨트롤에 대한 링크는 이 항목에서 [Windows 공용 컨트롤 및 MFC 클래스](#_core_windows_common_controls_and_mfc_classes) 표를 참조하세요.

- [컨트롤 만들기 및 사용](../mfc/making-and-using-controls.md)

- [대화 상자 편집기를 사용하여 컨트롤 추가](../mfc/using-the-dialog-editor-to-add-controls.md)

- [대화 상자에 컨트롤을 직접 추가](../mfc/adding-controls-by-hand.md)

- [MFC 컨트롤 클래스에서 컨트롤 클래스 파생](../mfc/deriving-controls-from-a-standard-control.md)

- [공용 컨트롤을 자식 창으로 사용](../mfc/using-a-common-control-as-a-child-window.md)

- [공용 컨트롤에서 알림](../mfc/receiving-notification-from-common-controls.md)

- [대화 상자에 일반 컨트롤 추가](../mfc/using-common-controls-in-a-dialog-box.md)

- [표준 Windows 컨트롤에서 컨트롤 파생](../mfc/deriving-controls-from-a-standard-control.md)

- [형식 안전성을 사용한 대화 상자 컨트롤 액세스](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)

- [공용 컨트롤에서 알림 메시지 받기](../mfc/receiving-notification-from-common-controls.md)

- [샘플](../mfc/common-control-sample-list.md)

Windows SDK의 Windows 일반 컨트롤에 대한 자세한 내용은 [일반 컨트롤](/windows/win32/Controls/common-controls-intro)을 참조하십시오.

## <a name="see-also"></a>참고 항목

[사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)<br/>
[대화 상자 편집기](../windows/dialog-editor.md)
