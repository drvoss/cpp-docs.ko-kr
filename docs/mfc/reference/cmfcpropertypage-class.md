---
title: CMFC프로퍼티페이지 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage
- AFXPROPERTYPAGE/CMFCPropertyPage::CMFCPropertyPage
helpviewer_keywords:
- CMFCPropertyPage [MFC], CMFCPropertyPage
ms.assetid: d279d7f2-2d81-418d-9f23-6147d6e8df09
ms.openlocfilehash: e493f016b6384a768935186c31e3fc71ade6382f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81361763"
---
# <a name="cmfcpropertypage-class"></a>CMFC프로퍼티페이지 클래스

클래스는 `CMFCPropertyPage` 속성 페이지에서 팝업 메뉴의 표시를 지원합니다.

## <a name="syntax"></a>구문

```
class CMFCPropertyPage : public CPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFCPropertyPage::CMFCPropertyPage](#cmfcpropertypage)|`CMFCPropertyPage` 개체를 생성합니다.|
|`CMFCPropertyPage::~CMFCPropertyPage`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCPropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCPropertyPage::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|`CMFCPropertyPage::OnSetActive`|이 멤버 함수는 사용자가 페이지를 선택하고 활성 페이지가 될 때 프레임워크에서 호출됩니다. [(CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive)재정의.)|
|`CMFCPropertyPage::PreTranslateMessage`|창 메시지가 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 및 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 함수로 전달되기 전에 변환합니다. 자세한 정보 및 메서드 구문은 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)를 참조하십시오. ( `CPropertyPage::PreTranslateMessage`을 재정의합니다.)|

## <a name="remarks"></a>설명

클래스는 `CMFCPropertyPage` 속성 시트의 개별 페이지를 나타내며 탭 대화 상자라고도 합니다.

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md) 클래스와 함께 `CMFCPropertyPage` 클래스를 사용합니다. 속성 페이지에서 메뉴를 사용하려면 클래스의 모든 발생을 `CPropertyPage` 클래스로 바꿉습니다. `CMFCPropertyPage`

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpropertypage.h

## <a name="cmfcpropertypagecmfcpropertypage"></a><a name="cmfcpropertypage"></a>CMFC속성 페이지::CMFC속성 페이지

`CMFCPropertyPage` 개체를 생성합니다.

```
CMFCPropertyPage(
    UINT nIDTemplate,
    UINT nIDCaption=0);

CMFCPropertyPage(
    LPCTSTR lpszTemplateName,
    UINT nIDCaption=0);
```

### <a name="parameters"></a>매개 변수

*nIDTemplate*<br/>
이 페이지의 템플릿의 리소스 ID입니다.

*nIDCaption*<br/>
이 페이지의 탭에 넣을 레이블의 리소스 ID입니다. 0이면 이 페이지의 대화 상자 템플릿에서 이름을 가져옵니다. 기본값은 0입니다.

*lpszTemplateName*<br/>
이 페이지의 템플릿 이름을 가리킵니다. NULL이 될 수 없습니다.

### <a name="return-value"></a>Return Value

### <a name="remarks"></a>설명

생성자 매개 변수에 대한 자세한 내용은 [CPropertyPage::CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage)를 참조하십시오.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC프로퍼티시트 클래스](../../mfc/reference/cmfcpropertysheet-class.md)
