---
title: CMFCCustomColorsPropertyPage 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage
- AFXCUSTOMCOLORSPROPERTYPAGE/CMFCCustomColorsPropertyPage::Setup
helpviewer_keywords:
- CMFCCustomColorsPropertyPage [MFC], Setup
ms.assetid: 46a45ba2-1fda-440d-8018-d4dcd44f5816
ms.openlocfilehash: 468d947947fc89f9ebc832cda722d854bb8b4be2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752469"
---
# <a name="cmfccustomcolorspropertypage-class"></a>CMFCCustomColorsPropertyPage 클래스

색상 대화 상자에서 사용자 지정 색상을 선택할 수 있는 속성 페이지를 나타냅니다.

## <a name="syntax"></a>구문

```
class CMFCCustomColorsPropertyPage : public CPropertyPage
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|`CMFCCustomColorsPropertyPage::CMFCCustomColorsPropertyPage`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|`CMFCCustomColorsPropertyPage::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|`CMFCCustomColorsPropertyPage::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|
|[CMFC 사용자 정의 색상속성 페이지::설정](#setup)|속성 페이지의 색상 구성 요소를 설정합니다.|

### <a name="remarks"></a>설명

클래스는 `CMFCColorDialog` 이 클래스를 사용하여 사용자 지정 색상 속성 페이지를 표시합니다. 자세한 `CMFCColorDialog`내용은 [CMFCColorDialog 클래스를](../../mfc/reference/cmfccolordialog-class.md)참조하십시오.

## <a name="example"></a>예제

다음 예제에서는 개체를 `CMFCCustomColorsPropertyPage` 생성 하고 속성 페이지의 색상 구성 요소를 설정 하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_RibbonApp#35](../../mfc/reference/codesnippet/cpp/cmfccustomcolorspropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFC커스텀컬러프로퍼페이지](../../mfc/reference/cmfccustomcolorspropertypage-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxcustomcolors속성 페이지.h

## <a name="cmfccustomcolorspropertypagesetup"></a><a name="setup"></a>CMFC 사용자 정의 색상속성 페이지::설정

속성 페이지의 색상 구성 요소를 설정합니다.

```cpp
void Setup(
    BYTE R,
    BYTE G,
    BYTE B);
```

### <a name="parameters"></a>매개 변수

|||
|-|-|
|매개 변수|Description|
|*R*|【인】 RGB 값의 빨간색 구성 요소입니다.|
|*G*|【인】 RGB 값의 녹색 구성 요소입니다.|
|*B*|【인】 RGB 값의 파란색 구성 요소입니다.|

### <a name="remarks"></a>설명

이 메서드는 속성 페이지의 현재 RGB 및 관련 HLS(색조, 가벼움 및 채도) 색상 값을 업데이트합니다. [CMFCColorDialog::SetPageTwo](../../mfc/reference/cmfccolordialog-class.md#setpagetwo) 메서드는 프레임워크가 색상 대화 상자를 초기화하거나 사용자가 왼쪽 마우스 단추를 누를 때 이 메서드를 호출합니다. 자세한 `CMFCColorDialog`내용은 [CMFCColorDialog 클래스를](../../mfc/reference/cmfccolordialog-class.md)참조하십시오.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC컬러디아로그 클래스](../../mfc/reference/cmfccolordialog-class.md)<br/>
[CMFCStandardColorsPropertyPage 클래스](../../mfc/reference/cmfcstandardcolorspropertypage-class.md)
