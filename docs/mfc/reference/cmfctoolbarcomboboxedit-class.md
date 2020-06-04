---
title: CMFCToolBarComboBoxEdit 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit
- AFXTOOLBARCOMBOBOXBUTTON/CMFCToolBarComboBoxEdit::CMFCToolBarComboBoxEdit
helpviewer_keywords:
- CMFCToolBarComboBoxEdit [MFC], CMFCToolBarComboBoxEdit
ms.assetid: 4789c34a-ce58-48ba-a26f-38748b601352
ms.openlocfilehash: dfbf24f5833d143adc6d21b6cb54dd9ac81c2f0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372199"
---
# <a name="cmfctoolbarcomboboxedit-class"></a>CMFCToolBarComboBoxEdit 클래스

프레임워크는 클래스를 `CMFCToolBarComboBoxEdit` 사용하여 편집 가능한 콤보 상자 컨트롤처럼 작동되는 도구 모음 단추를 만듭니다.

## <a name="syntax"></a>구문

```
class CMFCToolBarComboBoxEdit : public CEdit
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC툴바콤보박스편집::CMFC툴바콤보박스편집](#cmfctoolbarcomboboxedit)|`CMFCToolBarComboBoxEdit` 개체를 생성합니다.|
|`CMFCToolBarComboBoxEdit::~CMFCToolBarComboBoxEdit`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCToolBarComboBoxEdit::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 재정의합니다.)|

### <a name="remarks"></a>설명

클래스에서 클래스를 `CMFCToolBarComboBoxEdit` 파생하여 편집 작업을 사용자 지정합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

[CMFCToolBarComboBoxEdit](../../mfc/reference/cmfctoolbarcomboboxedit-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxtoolbarcomboboxbutton.h

## <a name="cmfctoolbarcomboboxeditcmfctoolbarcomboboxedit"></a><a name="cmfctoolbarcomboboxedit"></a>CMFC툴바콤보박스편집::CMFC툴바콤보박스편집

`CMFCToolBarComboBoxEdit` 개체를 생성합니다.

```
CMFCToolBarComboBoxEdit(CMFCToolBarComboBoxButton& combo);
```

### <a name="parameters"></a>매개 변수

*콤보*<br/>
【인】 콤보 상자 컨트롤을 포함 하는 도구 모음 단추는 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md) 개체에 대 한 참조입니다.

### <a name="example"></a>예제

다음 예제에서는 `CMFCToolBarComboBoxEdit` 클래스의 개체를 생성 하는 방법을 보여 줍니다. 이 코드 조각은 IE [데모 샘플의](../../overview/visual-cpp-samples.md)일부입니다.

[!code-cpp[NVC_MFC_IEDemo#5](../../mfc/reference/codesnippet/cpp/cmfctoolbarcomboboxedit-class_1.cpp)]

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC툴바콤보박스버튼 클래스](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)
