---
title: CMFC비활성화메뉴애니메이션 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation
- AFXPOPUPMENU/CMFCDisableMenuAnimation::Restore
helpviewer_keywords:
- CMFCDisableMenuAnimation [MFC], Restore
ms.assetid: c6eb07da-c382-43d6-8028-007f2320e50e
ms.openlocfilehash: c6d81f253016d3a292dd50b16c19f76a05e75e56
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752412"
---
# <a name="cmfcdisablemenuanimation-class"></a>CMFC비활성화메뉴애니메이션 클래스

팝업 메뉴 애니메이션을 사용하지 않도록 설정합니다.

## <a name="syntax"></a>구문

```
class CMFCDisableMenuAnimation
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|||
|-|-|
|속성|Description|
|`CMFCDisableMenuAnimation::CMFCDisableMenuAnimation`|`CMFCDisableMenuAnimation` 개체를 생성합니다.|
|`CMFCDisableMenuAnimation::~CMFCDisableMenuAnimation`|소멸자|

### <a name="public-methods"></a>Public 메서드

|||
|-|-|
|속성|Description|
|[CMFC비활성화메뉴애니메이션::복원](#restore)|프레임워크가 팝업 메뉴를 표시하는 데 사용한 이전 애니메이션을 복원합니다.|

### <a name="data-members"></a>데이터 멤버

|||
|-|-|
|속성|Description|
|`CMFCDisableMenuAnimation::m_animType`|이전 팝업 메뉴 애니메이션 유형을 저장합니다.|

### <a name="remarks"></a>설명

이 도우미 클래스를 사용하여 팝업 메뉴 애니메이션(예: 마우스 또는 키보드 명령을 처리하는 경우)을 일시적으로 사용하지 않도록 설정합니다.

개체는 `CMFCDisableMenuAnimation` 수명 동안 팝업 메뉴 애니메이션을 사용하지 않도록 설정합니다. 생성자는 현재 팝업 메뉴 애니메이션 유형을 `m_animType` 필드에 저장하고 현재 애니메이션 `CMFCPopupMenu::NO_ANIMATION`유형을 로 설정합니다. 소멸자는 이전 애니메이션 유형을 복원합니다.

스택에 개체를 `CMFCDisableMenuAnimation` 만들어 단일 함수 전체에서 팝업 메뉴 애니메이션을 사용하지 않도록 설정할 수 있습니다. 함수 간에 팝업 메뉴 애니메이션을 사용하지 않도록 `CMFCDisableMenuAnimation` 설정하려면 힙에 개체를 만든 다음 팝업 메뉴 애니메이션을 복원할 때 삭제합니다.

## <a name="example"></a>예제

다음 예제에서는 스택을 사용하여 메뉴 애니메이션을 일시적으로 사용하지 않도록 설정하는 방법을 보여 줍니다.

[!code-cpp[NVC_MFC_Misc#1](../../mfc/reference/codesnippet/cpp/cmfcdisablemenuanimation-class_1.h)]

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CMFC비활성화메뉴애니메이션](../../mfc/reference/cmfcdisablemenuanimation-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxpopupmenu.h

## <a name="cmfcdisablemenuanimationrestore"></a><a name="restore"></a>CMFC비활성화메뉴애니메이션::복원

프레임워크가 팝업 메뉴를 표시하는 데 사용한 이전 애니메이션을 복원합니다.

```cpp
void Restore ();
```

### <a name="remarks"></a>설명

이 메서드는 `CMFCDisableMenuAnimation` 소멸자에서 호출하여 프레임워크가 팝업 메뉴를 표시하는 데 사용한 이전 애니메이션을 복원합니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC팝메뉴 클래스](../../mfc/reference/cmfcpopupmenu-class.md)
