---
title: CMFCRibbonCustomizePropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 57fbd1e1f574beebff8baab014e7ab615f56333f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754168"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage 클래스

리본 기반 응용 프로그램에서 사용자 지정 대화 상자에 대한 **사용자 지정** 페이지를 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|[CMFC리본사용자 정의속성 페이지::CMFC리본사용자 정의속성 페이지](#cmfcribboncustomizepropertypage)|`CMFCRibbonCustomizePropertyPage` 개체를 생성합니다.|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC리본사용자 정의속성 페이지::사용자 지정 범주 추가](#addcustomcategory)|명령 콤보 상자에 사용자 지정 **범주를 추가합니다.**|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC리본 커스터마이징속성 페이지::OnOK](#onok)|사용자가 **사용자 지정** 대화 상자에서 **확인을** 클릭하면 시스템에서 호출됩니다.|

## <a name="remarks"></a>설명

**사용자 지정** 대화 상자에 사용자 지정 명령을 추가하려면 AFX_WM_ON_RIBBON_CUSTOMIZE 메시지를 처리해야 합니다. 메시지 처리기에서 스택에 개체를 `CMFCRibbonCustomizePropertyPage` 인스턴스화합니다. 사용자 지정 명령 목록을 만든 다음 `AddCustomCategory` 호출하여 **사용자 지정** 대화 상자에 새 페이지를 추가합니다.

## <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCRibbonCustomizePropertyPage` 생성하고 사용자 지정 범주를 추가하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFC리본사용자 정의속성 페이지](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxribbon사용자 지정.h

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a>CMFC리본사용자 정의속성 페이지::사용자 지정 범주 추가

명령 콤보 상자에 사용자 지정 **범주를 추가합니다.**

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*lpszName*|【인】 사용자 지정 범주 이름을 지정합니다.|
|*lstIDS*|【인】 사용자 지정 범주에 표시할 리본 명령 아이디를 포함합니다.|

### <a name="remarks"></a>설명

이 메서드는 명령 콤보 상자에 *lpszName이라는* **범주를 추가합니다.** 사용자가 범주를 선택하면 *lstIDS에* 지정된 명령이 명령 목록에 나타납니다.

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a>CMFC리본사용자 정의속성 페이지::CMFC리본사용자 정의속성 페이지

`CMFCRibbonCustomizePropertyPage` 개체를 생성합니다.

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>매개 변수

*pRibbonBar*<br/>
【인】 옵션을 사용자 지정할 수 있는 리본 컨트롤에 대한 포인터입니다.

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a>CMFC리본 커스터마이징속성 페이지::OnOK

사용자가 **사용자 정의** 대화 상자에서 **확인을** 클릭하면 시스템에 의해 calleld.

```
virtual void OnOK();
```

### <a name="remarks"></a>설명

기본 구현은 **사용자 지정** 대화 상자에서 선택한 옵션을 빠른 액세스 도구 모음에 적용합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)
