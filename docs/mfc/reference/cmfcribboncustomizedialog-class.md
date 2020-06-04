---
title: CMFCRibbonCustomizeDialog 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: a66c0a19c04e0a900b91c0c28c45bb9c766d25c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375201"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog 클래스

리본 사용자 지정 페이지를 **표시합니다.**

## <a name="syntax"></a>구문

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|[CMFC리본커스터마이즈디아로그::CMFC리본커스터마이즈디아로그](#cmfcribboncustomizedialog)|`CMFCRibbonCustomizeDialog` 개체를 생성합니다.|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|

## <a name="remarks"></a>설명

MFC는 AFX_WM_ON_RIBBON_CUSTOMIZE 메시지를 처리하지 않거나 메시지 처리기에서 0을 반환하는 경우 이 클래스를 자동으로 인스턴스화합니다.

응용 프로그램에서 이 클래스를 사용하여 리본 **사용자 지정** 대화 상자를 표시하려면 대화 상자를 인스턴스화하고 메서드를 `DoModal` 호출하기만 하면 됩니다.

이 클래스는 [CMFCPropertySheet 클래스에서](../../mfc/reference/cmfcpropertysheet-class.md)파생되므로 API를 `CMFCPropertySheet` 사용하여 사용자 지정 페이지를 추가할 수 있습니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFC리본커스터마이즈디아로그](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbon사용자 지정.h

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a>CMFC리본커스터마이즈디아로그::CMFC리본커스터마이즈디아로그

`CMFCRibbonCustomizeDialog` 개체를 생성합니다.

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>매개 변수

*pWndParent*<br/>
【인】 부모 창(일반적으로 주 프레임)에 대한 포인터입니다.

*p리본*<br/>
【인】 그에 대한 `CMFCRibbonBar` 포인터는 사용자 지정할 수 있습니다.

### <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCRibbonCustomizeDialog` 구성하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>설명

생성자는 [CMFCRibbonCustomizePropertyPage 클래스](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) 개체를 인스턴스화하고 속성 시트 페이지의 컬렉션에 추가합니다.

## <a name="see-also"></a>참고 항목

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
