---
title: CMFC리본메인패널 클래스
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: 0fd1cd2fec31f9da0c2bec36d08586780f4f95c3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753575"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFC리본메인패널 클래스

[CMFC리본응용단추를](../../mfc/reference/cmfcribbonapplicationbutton-class.md)클릭할 때 표시되는 리본 패널을 구현합니다.

## <a name="syntax"></a>구문

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|기본 생성자입니다.|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|소멸자|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CMFC리본메인패널::추가](#add)|응용 프로그램 단추 패널의 왼쪽 창에 리본 요소를 추가합니다. [(CMFC 리본 패널 재정의::추가](../../mfc/reference/cmfcribbonpanel-class.md#add).)|
|[CMFC리본메인패널::최근 파일목록 추가](#addrecentfileslist)|최근 파일 목록 메뉴에 텍스트 문자열을 추가합니다.|
|[CMFC리본메인패널::애추가바닥](#addtobottom)|리본 응용 프로그램 패널의 아래쪽 창에 리본 요소를 추가합니다.|
|[CMFC리본메인패널::애드토라이트](#addtoright)|응용 프로그램 단추 패널의 오른쪽 창에 리본 요소를 추가합니다.|
|`CMFCRibbonMainPanel::CreateObject`|프레임워크에서 이 클래스 형식의 동적 인스턴스를 만드는 데 사용합니다.|
|[CMFC리본메인패널::겟커맨드프레임](#getcommandsframe)|리본 주 패널의 영역을 나타내는 사각형을 반환합니다.|
|`CMFCRibbonMainPanel::GetThisClass`|이 클래스 형식과 연결된 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 개체에 대한 포인터를 얻기 위해 프레임워크에서 사용됩니다.|

## <a name="remarks"></a>설명

응용 프로그램 `CMFCRibbonMainPanel` 패널을 열 때 프레임워크가 표시됩니다. 여기에는 세 개의 창이 포함되어 있습니다.

- 왼쪽 창에는 **열기,** **저장,** **인쇄**및 **닫기**와 같은 파일과 연결된 명령이 포함되어 있습니다. 이 창에 명령을 추가하려면 [CMFCRibbonMainPanel::Add](#add)를 호출합니다.

- 오른쪽 창에는 왼쪽 창에서 클릭하는 명령을 수정하는 옵션이 포함되어 있습니다. 예를 들어 왼쪽 창에서 **As 저장을** 클릭하면 오른쪽 창에 사용 가능한 파일 형식이 표시될 수 있습니다. 이 창에 항목을 추가하려면 [CMFCRibbonMainPanel::AddToRight](#addtoright)를 호출합니다.

- 하단 창에는 응용 프로그램의 설정을 변경하고 프로그램을 종료할 수 있는 단추가 포함되어 있습니다. 이 창에 항목을 추가하려면 [CMFCRibbonMainPanel::AddToBottom](#addtobottom)를 호출합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afx리본메인패널.h

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a>CMFC리본메인패널::추가

응용 프로그램 단추 패널의 왼쪽 창에 리본 요소를 추가합니다.

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>매개 변수

*펠렘 (것)들*<br/>
【인, 아웃】 메인 패널에 추가할 리본 요소에 대한 포인터입니다.

### <a name="remarks"></a>설명

패널에 리본 요소를 추가합니다. 이 방법을 사용하여 추가된 요소는 주 패널의 왼쪽 열에 있습니다.

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a>CMFC리본메인패널::최근 파일목록 추가

최근 파일 목록 메뉴에 텍스트 문자열을 추가합니다.

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>매개 변수

*lpszLabel*<br/>
최근 파일 목록에 추가할 문자열을 지정합니다.

*nWidth*<br/>
최근 파일 목록 패널의 너비(픽셀)를 지정합니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a>CMFC리본메인패널::애추가바닥

리본 응용 프로그램 패널의 아래쪽 창에 리본 요소를 추가합니다.

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>매개 변수

*펠렘 (것)들*<br/>
【인, 아웃】 메인 패널의 맨 아래에 추가할 리본 요소에 대한 포인터입니다.

### <a name="remarks"></a>설명

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a>CMFC리본메인패널::애드토라이트

응용 프로그램 단추 패널의 오른쪽 창에 리본 요소를 추가합니다.

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>매개 변수

*펠렘 (것)들*<br/>
메인 패널의 오른쪽에 추가할 리본 요소에 대한 포인터입니다.

*nWidth*<br/>
오른쪽 패널의 너비(픽셀)를 지정합니다.

### <a name="remarks"></a>설명

이 함수를 사용하여 오른쪽 패널에 리본 요소를 추가합니다. 오른쪽 패널에는 일반적으로 최근 파일 목록이 표시되지만 여기에 다른 리본 요소를 추가할 수 있습니다.

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a>CMFC리본메인패널::겟커맨드프레임

리본 주 패널의 영역을 나타내는 사각형을 반환합니다.

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>Return Value

리본 주 패널의 영역을 나타내는 사각형입니다.

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CMFC리본패널 클래스](../../mfc/reference/cmfcribbonpanel-class.md)
