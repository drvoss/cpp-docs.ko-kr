---
title: CSmartDockingInfo 클래스
ms.date: 11/19/2018
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
ms.openlocfilehash: ebb5e75b5b298097cfce043bd83ec88ca0ab4030
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81751301"
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo 클래스

스마트 도킹 표식의 모양을 정의합니다.

## <a name="syntax"></a>구문

```
class CSmartDockingInfo : public CObject
```

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|속성|Description|
|----------|-----------------|
|`CSmartDockingInfo::CSmartDockingInfo`|기본 생성자입니다.|

### <a name="public-methods"></a>Public 메서드

|속성|Description|
|----------|-----------------|
|[CSmartDockingInfo::복사](#copyto)|현재 스마트 도킹 정보 매개 변수를 제공된 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 개체에 복사합니다.|

### <a name="data-members"></a>데이터 멤버

|속성|Description|
|----------|-----------------|
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|프레임워크에 스마트 도킹 마커가 표시될 때 현재 테마 색상을 사용할지 여부를 지정합니다.|
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|스마트 도킹 마커의 기본 배경 색을 지정합니다.|
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|스마트 도킹 마커 `m_clrToneSrc` 비트맵에서 대체하는 색상을 지정합니다.|
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|스마트 도킹 마커 비트맵의 색상을 지정합니다.|
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|스마트 도킹 마커 비트맵이 투명할 때 의 색상을 지정합니다.|
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|중앙 그룹 사각형의 경계에서 스마트 도킹 마커의 중앙 그룹의 오프셋을 지정합니다.|
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|그룹의 모든 스마트 도킹 마커의 총 크기를 지정합니다.|
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|프레임워크가 강조 표시되지 않은 스마트 도킹 마커에 사용하는 비트맵의 리소스 암호를 정의합니다.|
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|프레임워크가 강조 표시된 스마트 도킹 마커에 사용하는 비트맵의 리소스 암호를 정의합니다.|

## <a name="remarks"></a>설명

프레임워크는 스마트 도킹 마커를 내부적으로 처리합니다. 다음 그림에서는 표준 스마트 도킹 마커를 보여 주며, 다음 그림에서는 표준 스마트 도킹 마커를 보여 주며 다음과 같은 그림이 표시됩니다.

![스마트 도킹의 표준 마커](../../mfc/reference/media/nextsdmarkers.png "스마트 도킹의 표준 마커")

이 그림에서 왼쪽 이미지는 탭에 도킹이 활성화되어 있지 않은 중앙 그룹 스마트 도킹 마커를 보여 주며 있습니다. 가운데의 이미지는 오른쪽 가장자리 스마트 도킹 마커를 보여줍니다. 오른쪽 이미지는 탭에 도킹이 활성화된 중앙 그룹 스마트 도킹 마커를 보여 주며, 이 마커는 중앙 그룹 스마트 도킹 마커에는 기본 비트맵과 5개의 스마트 도킹 마커 비트맵이 있습니다.

스마트 도킹 마커의 다음 매개 변수를 사용자 지정할 수 있습니다.

- 색 예를 들어 그림에서 마커의 파란색을 사용자 정의 색상으로 바꿀 수 있습니다.

- 투명도 색상입니다.

- 경계 사각형의 테두리에서 중앙 그룹의 스마트 도킹 마커를 오프셋합니다.

- 중앙 그룹을 나타내는 기본 비트맵입니다.

- 일반 및 강조 표시된 스마트 도킹 마커를 나타내는 비트맵입니다.

다음 그림에서는 사용자 지정된 스마트 도킹 마커의 예를 보여 주며 있습니다.

![스마트 도킹의 사용자 지정 마커](../../mfc/reference/media/nextsdmarkerscustom.png "스마트 도킹의 사용자 지정 마커")

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CObject](../../mfc/reference/cobject-class.md)

[CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)

## <a name="requirements"></a>요구 사항

**헤더:** afxDockingManager.h

## <a name="csmartdockinginfocopyto"></a><a name="copyto"></a>CSmartDockingInfo::복사

현재 스마트 도킹 매개 변수를 제공된 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) 개체에 복사합니다.

```cpp
void CopyTo(CSmartDockingInfo& params);
```

### <a name="parameters"></a>매개 변수

*params*<br/>
【아웃】 현재 스마트 `CSmartDockingInfo` 도킹 매개 변수로 채워진 형식의 개체입니다.

## <a name="csmartdockinginfom_busethemecolorinshading"></a><a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading

프레임워크에 스마트 도킹 마커가 표시될 때 현재 테마 색상을 사용할지 여부를 지정합니다.

```
BOOL m_bUseThemeColorInShading;
```

### <a name="remarks"></a>설명

TRUE이면 현재 테마 색상을 사용하여 마커가 그려집니다. 그렇지 않으면 마커가 연한 파란색으로 그려집니다.

기본값은 FALSE입니다.

## <a name="csmartdockinginfom_clrbasebackground"></a><a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground

스마트 도킹 마커의 기본 배경 색을 지정합니다.

```
COLORREF m_clrBaseBackground;
```

## <a name="csmartdockinginfom_clrtonedest"></a><a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest

스마트 도킹 마커 비트맵에서 대체할 `m_clrToneSrc` 색상을 지정합니다.

```
COLORREF m_clrToneDest;
```

### <a name="remarks"></a>설명

이 값을 설정하여 마커 비트맵의 색상을 프로그래밍 방식으로 변경합니다. 예를 들어 프레임워크와 함께 제공되는 표준 마커의 색상을 변경하려면 이 값을 원하는 색상으로 설정합니다. 기본적으로 [CSmartDockingInfo:m_clrToneSrc](#m_clrtonesrc) RGB(61, 123, 241)(푸르스름색)로 설정됩니다.

사용자 지정 마커의 색상을 변경하려면 둘 `m_clrToneDest` `m_clrToneSrc`다와 을 모두 지정해야 합니다.

## <a name="csmartdockinginfom_clrtonesrc"></a><a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc

스마트 도킹 마커 비트맵의 색상을 지정합니다.

```
COLORREF m_clrToneSrc;
```

### <a name="remarks"></a>설명

사용자 지정 비트맵의 색상을 다른 색상으로 바꾸려는 경우에만 이 값을 설정합니다. 표준(프레임워크 제공) 마커의 색상을 변경하는 경우 이 값을 설정할 필요가 없습니다.

스마트 `(COLORREF)-1` 도킹 그룹의 구성원을 비워 두는 데 사용합니다.

## <a name="csmartdockinginfom_clrtransparent"></a><a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent

스마트 도킹 마커 비트맵이 투명할 때 의 색상을 지정합니다.

```
COLORREF m_clrTransparent;
```

### <a name="remarks"></a>설명

도킹 그룹에 사용자 지정 마커 및 사용자 지정 비트맵을 표시할 때 이 값을 설정해야 합니다.

## <a name="csmartdockinginfom_ncentralgroupoffset"></a><a name="m_ncentralgroupoffset"></a>CSmartDockingInfo::m_nCentralGroupOffset

스마트 도킹 마커의 중앙 그룹과 중앙 그룹 사각형의 경계 사이의 오프셋을 지정합니다.

```
int m_nCentralGroupOffset;
```

### <a name="remarks"></a>설명

사용자 지정 마커와 스마트 도킹 마커의 중앙 그룹의 경계 사이의 기본 오프셋을 변경하려는 경우 이 값을 지정합니다. 기본 오프셋은 5픽셀입니다.

## <a name="csmartdockinginfom_sizetotal"></a><a name="m_sizetotal"></a>CSmartDockingInfo::m_sizeTotal

중앙 그룹의 모든 스마트 도킹 마커를 둘러싸는 경계 사각형의 총 크기를 지정합니다.

```
CSize m_sizeTotal;
```

### <a name="remarks"></a>설명

중앙 `m_sizeTotal` 그룹 마커의 경계 사각형 크기로 설정합니다. 마커에 사용자 지정 비트맵을 사용하는 경우 이 값을 지정해야 합니다.

## <a name="csmartdockinginfom_uimarkerbmpresid"></a><a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID

강조 표시되지 않은 사용자 지정 스마트 도킹 마커에 사용되는 비트맵의 리소스 암호를 정의합니다.

```
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>설명

스마트 도킹 마커를 나타내는 비트맵의 리소스 아이디로 이 배열을 채웁니다. AFX_SD_MARKERS_NUM 현재 5로 정의됩니다. 다음과 같이 배열을 채웁니다.

```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```

## <a name="csmartdockinginfom_uimarkerlightbmpresid"></a><a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID

강조 표시된 사용자 지정 스마트 도킹 마커에 사용되는 비트맵의 리소스 암호를 정의합니다.

```
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];
```

### <a name="remarks"></a>설명

강조 표시된 스마트 도킹 마커를 나타내는 비트맵의 리소스 아이디로 이 배열을 채웁니다. AFX_SD_MARKERS_NUM 현재 5로 정의됩니다. 다음과 같이 배열을 채웁니다.

```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```

## <a name="see-also"></a>참조

[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[클래스](../../mfc/reference/mfc-classes.md)<br/>
[CObject 클래스](../../mfc/reference/cobject-class.md)
